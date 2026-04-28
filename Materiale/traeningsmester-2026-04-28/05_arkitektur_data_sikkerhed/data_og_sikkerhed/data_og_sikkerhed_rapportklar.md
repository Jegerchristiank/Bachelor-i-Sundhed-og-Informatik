# Rapportklar data- og sikkerhedsforklaring

Dato: 2026-04-28  
Scope: Supabase schema, RLS, Edge Functions, client-safe keys, Swift repository-lag og sundhedsdatarelaterede integrationspunkter i Traeningsmester.

## Kildegrundlag

Forklaringen bygger på følgende repo-kilder:

- `SUPABASE_MASTER_SETUP.sql`
- `supabase/functions/*`
- `Traeningsmester/Core/Config/AppEnvironment.swift`
- `Traeningsmester/Core/Data/RepositoryProtocols.swift`
- `Traeningsmester/Core/Data/SupabaseRepositories.swift`
- `Traeningsmester/Core/Domain/Models.swift`
- `Traeningsmester/Core/Domain/Payloads.swift`
- `Traeningsmester/Core/Support/ProgramReviewService.swift`
- `Traeningsmester/Core/Support/TrainerClientService.swift`
- `Traeningsmester/Core/Support/HealthKitBodyWeightService.swift`
- `Traeningsmester/Core/LiveActivity/*`
- `Traeningsmester/Core/Support/WatchAuthSyncPayload.swift`
- eksisterende bilag i `BachelorMateriale/2026-04-28-traeningsmester/05_arkitektur_data_sikkerhed/data_og_sikkerhed/`

## Kort rapportafsnit

Traeningsmester er bygget som en native SwiftUI-klient med Supabase som backend. Den centrale sikkerhedsbeslutning er, at appen kun distribuerer client-safe Supabase credentials, dvs. anon/publishable key, mens alle privilegerede operationer er flyttet til Row Level Security, SQL/RPC eller Supabase Edge Functions. Klienten kan derfor ikke alene give adgang til andre brugeres data. Den skal altid præsentere en gyldig Supabase Auth-session, og backend-politikkerne bruger `auth.uid()` til at afgøre, om en række må læses eller ændres.

Datamodellen er opdelt efter domæne: øvelseskatalog, træningsprogrammer, workout-dage, trackerlog, completion-events, indstillinger, træner-klient relationer, social deling, admin/diagnostik og importjobs. Appens Swift-lag taler ikke direkte fra views til Supabase. I stedet går dataadgang gennem typed repository-protokoller og DTO'er. Det giver en tydelig kontrakt mellem UI, domænemodeller og database, samtidig med at backend forbliver den egentlige sikkerhedsgrænse.

Privilegerede flows som admin, træner-klient operationer, import, AI-analyse og billing håndteres via Edge Functions. Disse funktioner validerer først brugerens bearer token med en user-scoped anon-klient. Kun derefter bruger funktionen eventuelle serverhemmeligheder som `SUPABASE_SERVICE_ROLE_KEY`, `OPENAI_API_KEY` eller `STRIPE_SECRET_KEY` internt i function runtime. Service-role credentials ligger dermed ikke i appens binary, Info.plist, xcconfig eller logs.

## Datamodel og schemaansvar

`SUPABASE_MASTER_SETUP.sql` fungerer som master-setup for schema, views, RPC, RLS og storage. Det er rapportens vigtigste SQL-kilde, fordi filen viser både tabellerne og den adgangskontrol, der ligger direkte i databasen.

| Domæne | Centrale tabeller/views | Formål i systemet |
| --- | --- | --- |
| Øvelser | `exercises`, `workout_exercise_user_weights`, `workout_exercises_with_user_weight` | Officielt og privat øvelseskatalog, medier og bruger-specifik vægt |
| Programmer | `plan`, `workout`, `plan_workouts`, `workout_exercises` | Programstruktur, træningsdage og øvelsesrækker |
| Deling og social | `plan_share_codes`, `plan_shared_users`, `plan_share_invites`, `user_friend_codes`, `friend_requests`, `friendships`, `friend_aliases` | Deling af programmer, venneflow og buddy-relationer |
| Træner/klient | `trainer_clients`, `trainer_client_plan_links` | Relationer mellem træner og klient samt tildelte programmer |
| Tracker og historik | `trackerlog`, `workout_completion_events`, `active_workout_session_state`, `user_trackerlog_exercises` | Sætlogs, træningsafslutninger, aktiv session og historikvisning |
| Indstillinger og drift | `user_settings`, `app_activity_events`, `app_feedback`, `app_version_history`, `app_error_reports` | Profiltilstand, subscription, adminflag, feedback, audit og diagnostics |
| Cykler/import | `training_cycles`, `training_cycle_*`, `training_import_jobs`, `training_cycle_runtime_states_view` | Makro/meso/deload, runtime progression og importjobs |

Schemaet er ikke blot CRUD. Det afspejler appens kerneproblem: brugeren skal kunne planlægge, afvige fra planen og stadig få en sammenhængende historik. Derfor er planstruktur (`plan`, `workout`, `workout_exercises`) adskilt fra faktisk træningshistorik (`trackerlog`), completion uden tracker (`workout_completion_events`) og runtime-baseret træningscyklus (`training_cycle_runtime_state`).

Særligt rapportrelevante felter:

| Felt | Placering | Betydning |
| --- | --- | --- |
| `user_id` / `"userID"` | Næsten alle brugerbundne tabeller | Kobler rækker til Supabase Auth-bruger og bruges i RLS |
| `profile_mode` | `plan`, `workout`, `match`, completion/session/cycle flows | Skelner personlig profil fra træner-/coach-kontekst |
| `client_action_id` | `trackerlog`, `workout_completion_events` | Idempotency for Live Activity, watch og retryede writes |
| `reverted_at` | `workout_completion_events` | Gør det muligt at fortryde en completion uden at slette historik |
| `superset_group_id`, `superset_position` | `workout_exercises` | Giver superset-struktur i iOS og watch |
| `is_rest_override` | `workout_exercises` | Skelner standardpause fra brugerens eksplicitte pausevalg |
| `subscription_tier` | `user_settings` | Binder StoreKit/billing-status til appens featureadgang |
| `is_admin` | `user_settings` | Server-valideret adminflag, ikke lokal UI-state |

## RLS som primær sikkerhedsgrænse

Row Level Security er slået til og force'et på de centrale brugerbundne tabeller i `SUPABASE_MASTER_SETUP.sql`, bl.a. `plan`, `workout`, `workout_exercises`, `trackerlog`, `workout_completion_events`, `active_workout_session_state`, `user_settings`, `trainer_clients` og træningscyklus-tabellerne. "Force row level security" betyder, at politikkerne også gælder mere konsekvent for databaseejer-kontekster og reducerer risikoen for utilsigtet policy-bypass i almindelige query-paths.

RLS-politikkerne følger tre hovedmønstre:

1. Ejeradgang: brugeren må læse og skrive egne rækker, typisk med `auth.uid() = user_id`.
2. Relationel adgang: brugeren må læse eller ændre data, hvis en relation giver adgang, fx delt program, træner-klient relation eller venskabsrelation.
3. Servervalideret særadgang: admin, import og andre privilegerede operationer går via SQL helper functions eller Edge Functions, ikke via lokal UI-state.

Eksempler fra SQL:

| Område | RLS-mønster | Rapportbetydning |
| --- | --- | --- |
| Programmer | `tm_user_can_read_plan` og `tm_user_can_edit_plan` afgør adgang til `plan` og afledte workout-rækker | Programdeling kan tillade læsning eller redigering uden at ophæve ejerkontrol |
| Workout-øvelser | `workout_exercises` kræver adgang til workout-dagen og synlig/egen øvelse | En bruger kan ikke bare indsætte en øvelse i en anden brugers workout |
| Trackerlog | `trackerlog` kræver `auth.uid() = "userID"` og en tilgængelig `workoutexcerciseID` | Sætlogs er bundet til både bruger og træningsrække |
| Completion events | `workout_completion_events` kræver egen `user_id` og gyldig `profile_mode` | Tracker-off afslutninger tæller med uden at åbne for cross-user writes |
| Settings | `user_settings` er own-row only | Profil, kropsvægt, subscription tier og adminflag læses/skrives ikke frit på tværs |
| Træningscyklus | `training_cycles` og `training_cycle_*` er own-cycle only | Makro/meso/deload data holdes under samme brugergrænse |
| Importjobs | Bruger må kun selecte egne job; insert/update/delete er service-role | Bulk-import kan orkestreres server-side uden at give klienten jobmutationsrettigheder |
| Storage | `storage.objects` kræver bucket `workout_images` og første path-segment lig `auth.uid()` | Uploads ligger i brugerens egen mappe |

Et vigtigt princip er, at klientvalidering ikke betragtes som den primære sikkerhedsgrænse. Swift-repositories kalder fx `ensureUserMatches(_:)`, så appen tidligt kan afvise åbenlyst forkerte bruger-id'er. Men den egentlige beskyttelse er fortsat RLS, fordi en angriber ikke må kunne opnå adgang ved at omgå UI eller ændre en request.

## Client-safe keys og miljøvalidering

`AppEnvironment` loader `SUPABASE_URL`, `SUPABASE_ANON_KEY`, `SUPABASE_STORAGE_BUCKET` og miljønavn fra appens Info.plist/xcconfig. Ved opstart afvises:

- manglende config
- ugyldig Supabase URL
- placeholder-værdier som indeholder `CHANGE_ME`
- JWT keys med rollen `service_role`

Det betyder, at appen fejler lukket, hvis en release ved en fejl bygges med en privilegeret Supabase key. `SupabaseRepositoryProviderFactory` opretter derefter en `SupabaseClient` med anon key og auth redirect URL. Denne anon key identificerer klientprojektet, men giver ikke i sig selv adgang til brugerdata. Brugeradgang opstår først, når Supabase Auth-sessionen tilføjer et bearer token, som RLS kan omsætte til `auth.uid()`.

Edge Function-kald fra Swift følger samme princip. Klienten sender:

- `apikey: <anon key>`
- `Authorization: Bearer <brugerens access token>`
- JSON payload med typed requestdata

Serverfunktionen validerer access token med en user-scoped anon-klient (`auth.getUser()`). Først efter den validering må funktionen bruge eventuelle serverhemmeligheder internt.

## Repository-lag og typed payloads

Appens views arbejder mod protokoller i `RepositoryProtocols.swift`. Supabase-implementeringen ligger i `SupabaseRepositories.swift`. Denne lagdeling har tre sikkerheds- og kvalitetsfordele:

1. Views behøver ikke kende Supabase query-syntaks, tabelnavne eller edge endpoints.
2. Payloads i `Payloads.swift` styrer præcis, hvilke felter klienten kan sende.
3. Repository-metoder kan håndhæve sessionkrav og bruger-match før netværkskald.

Eksempler:

- `PlanPayload`, `WorkoutPayload` og `WorkoutExercisePayload` mapper Swift-navne til SQL-kolonner som `user_id`, `profile_mode`, `workout_day_id` og `exercise_id`.
- `TrackerLogPayload` bærer `client_action_id`, som gør writes idempotente.
- `WorkoutCompletionEventPayload` bruges til completion-events, så både tracker og tracker-off flows kan registrere afsluttede træninger.
- `SettingsPayload` centraliserer brugerindstillinger som `bodyweight_kg`, `weight_unit`, `TRACKER`, `FLOW` og sprogvalg.

Repository-laget er dermed en typed klientkontrakt, mens Supabase RLS er den autoritative backendkontrakt.

## Edge Functions som privilegeret backendlag

Edge Functions bruges, når en handling kræver server-side autorisation, hemmelige API-nøgler, service-role, audit eller orchestration.

| Function | Ansvar | Sikkerhedsmæssig begrundelse |
| --- | --- | --- |
| `admin-control-center` | Admin bruger-CRUD, aktivitetsfeed, øvelsesreview og kontooperationer | Bruger service-role internt, men kræver først server-valideret admin via `tm_current_user_is_admin`/settings |
| `trainer-client-manage` | Træner-klient relationer, klientoprettelse, planlinks og klientaktivitet | Håndterer tværbrugerrelationer og bruger service-role uden at eksponere den til appen |
| `program-review-analyze` | AI-analyse af træningsprogram | OpenAI key ligger i function environment, ikke i klient |
| `program-plan-questionnaire` | AI-genereret spørgeskema/plan-input | Samme secret-isolering og authvalidering |
| `program-import-normalize` | Normalisering af programtekst/billeder | Input kan valideres server-side før appen viser forslag |
| `history-import-normalize` | Normalisering af gamle træningslogs | Reducerer risiko ved bulk-import af historik |
| `training-import-manage` | Importjob start/status/cancel/retry/apply | Jobmutationsrettigheder er service-role only; brugerens adgang kontrolleres via `user_id` |
| `billing-create-checkout-session` | Checkout-session helper | Stripe secret key holdes server-side |
| `billing-confirm-checkout-session` | Checkout-bekræftelse | Betalingsstatus valideres server-side før app-state opdateres |

Mønsteret i funktionerne er ens: preflight håndteres, kun `POST` accepteres for muterende endpoints, `Authorization`-header kræves, brugerens session valideres, og derefter udføres handlingen. Det giver et klart skel mellem client-safe adgang og privilegerede serverhandlinger.

## Tracker, Live Activity og idempotency

Tracker-flowet er sikkerhedskritisk, fordi det kan skrive mange små logs, også fra watchOS eller Live Activity.

Kontrollerne er:

- `trackerlog` har RLS på `"userID"`.
- `trackerlog` kræver en tilgængelig `workoutexcerciseID`.
- SQL-triggeren `tm_block_trackerlog_immutable_update` blokerer ændring af immutable felter som `"userID"`, `"workoutexcerciseID"` og `client_action_id`.
- Unique index på `("userID", client_action_id)` gør retryede writes idempotente.
- Live Activity gemmer kun et session snapshot i App Group storage og opretter en authenticated anon-klient med brugerens session tokens.
- Live Activity tjekker eksisterende `client_action_id`, før den forsøger insert, og forsøger igen at hente eksisterende log efter insert-fejl.

Det gør flowet robust mod dobbelttryk, netværksretry og race conditions mellem hovedapp, watch og Live Activity.

## Watch sync

Watch sync bruger `WatchAuthSyncPayload`, som indeholder schema version, Supabase URL, anon key, storage bucket, profile mode, exercise language preference, user ID og session tokens. Det er stadig client-safe i den forstand, at watch kun modtager anon key og brugerens egne auth tokens. Når watch appen skriver eller læser backenddata, sker det gennem samme Supabase/RLS-model som iOS.

Sikkerhedspointen er, at watch ikke får service-role adgang. Den får en bruger-session, og den session kan kun gøre det, RLS tillader for `auth.uid()`.

## Storage og medieupload

Storage-konfigurationen opretter bucket `workout_images`. SQL-politikker på `storage.objects` kræver, at første mappe i object path matcher `auth.uid()`. Klienten normaliserer også uploadstier i `SupabaseExerciseRepository`:

- stien skal være ikke-tom
- første segment skal være session-brugerens UUID
- andet segment skal være en godkendt mediemappe, fx `exercises`, `programs`, `plans`, `workouts`, `mesoprograms` eller `history`

Dette er et eksempel på forsvar i flere lag: klienten afviser ugyldige paths tidligt, men storage RLS er stadig den egentlige adgangskontrol.

## Sundhedsdata og dataminimering

Traeningsmester har et begrænset Apple HealthKit-perspektiv. Appen er ikke en journal- eller behandlingsintegration, og repoet viser ikke en FHIR- eller national sundhedsdataudveksling. Interoperabiliteten er i stedet platformnær:

- appen kan læse seneste kropsvægt via `HKQuantityTypeIdentifier.bodyMass`
- appen kan læse puls og aktiv energi i forbindelse med træningssynkronisering
- appen kan skrive afsluttede styrketræninger som `HKWorkout`
- appen kan tilknytte metadata som workout-id, total reps, antal sæt, varighed, energikilde og pulskvalitet

HealthKit-adgang kræver brugerens systemtilladelse. Info.plist forklarer formålet: appen bruger Apple Sundhed til kropsvægt, puls-/energidata og til at gemme afsluttede styrketræninger, når brugeren aktivt vælger synkronisering.

Dataminimeringen er tydelig i de inspicerede filer:

- Supabase gemmer kropsvægt som `user_settings.bodyweight_kg`, hvis brugeren vælger eller indtaster den.
- Rå puls- og energisamples gemmes ikke i Supabase i den gennemgåede kode.
- Puls/energi bruges til at kvalificere HealthKit-workout og energiestimat, ikke som cloudbaseret trackinglog.
- Onboarding viser eksplicit, at Apple Sundhed er slået fra i bruger-visning, så en admins lokale sundhedsdata ikke gemmes på en anden brugers profil.

Sundhedsdata bør derfor beskrives som brugeraktiveret, platformskontrolleret fitnessdata, ikke som klinisk behandlingsdata.

## Admin og audit

Adminadgang er et særskilt sikkerhedsområde. Appens UI kan vise adminfunktioner, men autorisationen må ikke afgøres af UI-state alene. Edge Function `admin-control-center` validerer først brugerens session og kalder derefter admincheck. SQL-siden har `tm_current_user_is_admin()` og `tm_require_admin()`, hvor adminflaget kommer fra `user_settings.is_admin`.

Adminfunktionen skriver også aktivitetsdata til `app_activity_events` for relevante handlinger. Det giver et auditspor, som kan bruges i rapporten til at argumentere for sporbarhed ved privilegerede operationer.

## Risici og restkontroller

| Risiko | Kontrol i systemet | Rest-risiko |
| --- | --- | --- |
| Service-role key ender i appen | `AppEnvironment` afviser JWT med `service_role`; Edge Functions holder server secrets i runtime | Release-review af config er stadig nødvendigt |
| Cross-user adgang | Forced RLS, `auth.uid()`, helper functions og repository guards | Integrationstest med flere brugere kræver gyldige testcredentials |
| Admin UI bypass | Admin Edge Function og SQL admincheck | Adminflag og audit bør kontrolleres i deployment |
| Dobbelt trackerlog | `client_action_id`, unique index og retry-safe klientkode | Afhænger af stabil client action-id generation |
| Bulk-import skriver forkert data | Importjobs er service-role styret og bundet til `user_id`; preview/apply flow | Brugeren skal verificere preview før commit |
| HealthKit-data havner på forkert profil | HealthKit kræver tilladelse; admin/user-view guard; kun kropsvægt sync'es til Supabase | UI og rapport skal være tydelige om samtykke |
| Medieupload til andres mappe | Storage RLS på første path-segment og klient-path normalisering | Bucket/policy setup skal verificeres i Supabase |

## Rapportkonklusion

Traeningsmesters dataarkitektur er designet omkring princippet om mindst privilegium. Klienten bruger kun anon/publishable key og typed repositories. Brugeradgang håndhæves i Supabase via RLS, helper functions, constraints og triggers. Privilegerede flows er flyttet til Edge Functions, hvor brugerens session først valideres, og hvor service-role eller eksterne API secrets kun eksisterer i servermiljøet. Det giver en sikkerhedsmodel, hvor UI'et hjælper brugeren, men databasen og backendfunktionerne afgør adgangen.

Samtidig understøtter datamodellen appens produktbehov: plan, faktisk udførelse, historik, completion, træningscyklus og import er adskilte, men sammenkoblede. Det giver både fleksibilitet i træningsflowet og et klart spor for sikkerhed, test og rapportering.
