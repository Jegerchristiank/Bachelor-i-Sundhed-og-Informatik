# Interoperabilitet, DCR og BPMN - notat

Dato: 2026-04-28  
Scope: rapportklar forklaring af interoperabilitet, sundhedsdata-perspektiv, DCR-autorisation og BPMN-trackerflow.

## Formål

Dette notat samler tre perspektiver, som kan bruges i rapporten:

1. Interoperabilitet: hvordan Traeningsmester udveksler data mellem iOS, watchOS, Live Activity, Supabase, Edge Functions og Apple HealthKit.
2. DCR: hvordan adgangsregler og sikkerhedsbetingelser kan beskrives deklarativt.
3. BPMN: hvordan brugerens trackerflow kan beskrives som en sekventiel proces med alternative grene.

Notatet er baseret på de eksisterende diagramkilder:

- `02_figurer_og_screenshots/diagrammer/kilder/authorization_dcr.md`
- `02_figurer_og_screenshots/diagrammer/kilder/tracker_flow.bpmn`
- `02_figurer_og_screenshots/diagrammer/kilder/authorization_dcr.md`
- `02_figurer_og_screenshots/diagrammer/kilder/tracker_flow.bpmn`

## Interoperabilitet i systemet

Traeningsmester har flere lag af interoperabilitet. Det er ikke én stor integration, men en række kontrollerede grænseflader, hvor hvert lag har et tydeligt dataformat og en tydelig sikkerhedsgrænse.

| Lag | Dataformat / kontrakt | Eksempel | Sikkerhedskontrol |
| --- | --- | --- | --- |
| Swift UI til domæne | Swift domain models og payloads | `PlanPayload`, `WorkoutExercisePayload`, `TrackerLogPayload` | Typed payloads og repository-protokoller |
| Swift til Supabase | PostgREST, RPC og Storage via Supabase Swift client | `client.from("trackerlog").insert(...)`, `client.rpc(...)` | Auth session, anon key og RLS |
| iOS til watchOS | `WatchAuthSyncPayload` via WatchConnectivity | Supabase URL, anon key, profile mode, session tokens | Bruger-session, ikke service-role |
| iOS til Live Activity | App Group snapshot | `TrackerLiveActivitySessionSnapshot` | Lokalt snapshot plus authenticated anon session |
| App til Edge Functions | JSON over HTTPS | `program-review-analyze`, `training-import-manage`, `admin-control-center` | Bearer token valideres server-side |
| Edge Functions til eksterne API'er | Server-side HTTPS | OpenAI og Stripe | Secrets kun i function environment |
| App til Apple HealthKit | HealthKit types og metadata | body mass, heart rate, active energy, `HKWorkout` | iOS systemtilladelse og brugerhandling |
| Supabase SQL internt | Tables, views, RPC og RLS | `tm_user_can_read_plan`, `tm_progress_training_cycle_after_workout` | `auth.uid()`, constraints og security definer functions |

Det vigtigste arkitekturprincip er, at interoperabilitet ikke må forveksles med fri dataadgang. Hver integrationsflade er begrænset til et formål, og backend fastholder adgangskontrollen.

## Sundhedsdata-perspektiv

Appens sundhedsdatarelaterede funktionalitet er afgrænset til fitness- og træningskontekst:

- Kropsvægt kan læses fra Apple Sundhed og gemmes som `user_settings.bodyweight_kg`, hvis brugeren vælger det.
- Puls og aktiv energi kan læses fra HealthKit i forbindelse med færdiggørelse af en træning.
- En afsluttet styrketræning kan skrives tilbage til HealthKit som `HKWorkout`.
- Træningen mærkes med metadata, fx Traeningsmester workout-id, samlet antal reps, antal sæt, varighed, energikilde og pulskvalitet.

Dette er interoperabilitet med Apple HealthKit, ikke klinisk interoperabilitet med elektroniske patientjournaler. Der er ingen FHIR-implementering i de inspicerede filer, og appen bør derfor ikke beskrives som et behandlings- eller journalsystem. En præcis formulering i rapporten er:

> Traeningsmester behandler brugerens trænings- og fitnessdata og kan efter samtykke udveksle afgrænsede datapunkter med Apple Sundhed. Integrationen bruges til personlig træningskontekst og ikke til klinisk diagnosticering eller journalføring.

Dataminimeringen er væsentlig:

- Rå puls- og energisamples gemmes ikke i Supabase i den gennemgåede kode.
- Supabase gemmer kropsvægt som en profilindstilling, fordi den bruges til kropsvægtsøvelser og vægtberegning.
- HealthKit kræver systemtilladelse, og brugeren kan fortsætte uden sync.
- Onboarding og settings har særskilt håndtering, så lokal HealthKit-data ikke bruges, når en admin arbejder i bruger-visning.

Hvis projektet senere skal udveksle sundhedsdata med kliniske systemer, vil det kræve en særskilt interoperabilitetsmodel, fx FHIR-ressourcer, samtykkemodel, databehandleraftaler og et stærkere formålsgrundlag. Det ligger uden for den nuværende implementering.

## DCR-fortolkning af autorisation

DCR-modellen i `authorization_dcr.md` beskriver sikkerhedsregler som deklarative betingelser, responser og eksklusioner. Det passer godt til autorisation, fordi sikkerhed ikke kun er en lineær proces. Den samme regel skal gælde, uanset om handlingen kommer fra iOS, watchOS, Live Activity eller en Edge Function.

### Centrale events

| DCR-event | Implementering i repoet | Betydning |
| --- | --- | --- |
| `LoadAppEnvironment` | `AppEnvironment.load(...)` | Appen læser Supabase URL, anon key og bucket |
| `RejectInvalidEnvironment` | Placeholder- og `service_role`-afvisning | Appen må ikke starte med privilegerede keys |
| `CreateAnonSupabaseClient` | `SupabaseRepositoryProviderFactory.make(...)` | Klienten oprettes med anon key |
| `AuthenticateUser` / `ResolveSession` | `AuthRepository`, `AppState` og Supabase Auth | Brugerens session giver `auth.uid()` |
| `ReadOwnData` / `WriteOwnData` | Repositories og Supabase RLS | Ejeradgang til brugerbundne rækker |
| `ReadSharedPlan` | `tm_user_can_read_plan` | Delt program kan læses af inviteret bruger |
| `WriteSharedPlanIfCanEdit` | `tm_user_can_edit_plan` | Delt program kan kun redigeres med edit-adgang |
| `CallTrainerClientFunction` | `trainer-client-manage` | Tværbrugerrelationer håndteres server-side |
| `CallAdminFunction` | `admin-control-center` | Adminhandlinger går via Edge Function |
| `ValidateAdminServerSide` | `tm_current_user_is_admin` og function guard | Admin UI-state er ikke nok |
| `CallImportFunction` | `training-import-manage` og normalize functions | Import orkestreres med serverkontrol |
| `UseServiceRoleInsideFunction` | Service-role client i udvalgte Edge Functions | Privilegier findes kun i runtime, ikke i klient |
| `WriteTrackerLog` | `trackerlog` insert via repository | Sætlog skrives under RLS |
| `WriteLiveActivityTrackerLog` | `TrackerLiveActivityIntents` | Lock Screen/Dynamic Island kan skrive med bruger-session |
| `DeduplicateClientAction` | `client_action_id` og unique index | Retry eller dobbelttryk giver ikke dobbelt log |
| `DenyCrossUserAccess` | RLS, constraints og repository guards | Cross-user requests skal afvises |

### Conditions

DCR-betingelserne kan omskrives til rapporttekst sådan:

- En Supabase-klient må først oprettes, når miljøet er indlæst og valideret.
- En brugerbundet læse- eller skrivehandling kræver en resolved auth-session.
- Delte programmer kræver ikke ejerskab, men kræver en eksplicit delingsrelation.
- Adminhandlinger kræver både session og server-side adminvalidering.
- Service-role må kun bruges efter et function-kald og kun inde i function runtime.
- Live Activity writes kræver session snapshot og idempotency via `client_action_id`.

### Responses

DCR-responserne beskriver, hvad systemet skylder at gøre efter bestemte events:

- Efter et admin function-kald skal serveren validere adminadgang.
- Efter en privilegeret mutation bør der skrives audit-event.
- Hvis RLS- eller relationstjek fejler, skal handlingen nægtes.
- Hvis Live Activity skriver et sæt, bør `client_action_id` deduplikeres før eller omkring persistensen.

### Exclusions

DCR-eksklusionerne er rapportens stærkeste sikkerhedsargument:

- `RejectInvalidEnvironment` udelukker `CreateAnonSupabaseClient`. Appen skal ikke køre videre med usikker config.
- `RejectAdminOperation` udelukker privilegeret adminmutation. Lokal UI-state kan ikke overtrumfe backend.
- `DenyCrossUserAccess` udelukker den ønskede read/write-operation. Brugeren må ikke få delvis adgang, hvis relationen ikke findes.

## BPMN-fortolkning af trackerflowet

BPMN-filen `tracker_flow.bpmn` beskriver brugerens træningsflow som en proces. Hvor DCR beskriver regler, beskriver BPMN rækkefølge.

Hovedflowet er:

1. Brugeren starter en workout.
2. `AppState` validerer auth og profile mode.
3. Systemet vælger mellem tracker-on og tracker-off.
4. Tracker-on åbner `workoutTracker`, henter træningsrækker og historik og starter Live Activity snapshot.
5. Brugeren logger sæt i et loop.
6. Hvert sæt persisteres til `trackerlog` med anon session og RLS.
7. Projection for næste sæt/pause opdateres.
8. Når sættene er færdige, gemmer `WorkoutCompletionService` en completion event.
9. Hvis der er aktiv træningscyklus, kaldes progression RPC.
10. Historik og Home opdateres ud fra completion/trackerlog data.

Tracker-off grenen er vigtig i rapporten, fordi den viser, at appen understøtter brugerens adfærd uden at tvinge detaljeret logging. Hvis tracker er slået fra, åbner appen `workoutTrackerWithoutLogging` og springer sæt-loopet over, men gemmer stadig en completion event. Det giver funktionel historik uden detaljerede sætdata.

## DCR og BPMN sammen

DCR og BPMN supplerer hinanden:

| BPMN-step | Relevant DCR-regel | Sikkerhedsfortolkning |
| --- | --- | --- |
| `ResolveSession` | `AuthenticateUser` før `ReadOwnData`/`WriteOwnData` | Processen må ikke hente træningsdata uden session |
| `FetchRows` | `ReadOwnData` eller `ReadSharedPlan` | Workout-rækker kommer gennem RLS og shared-plan checks |
| `StartLiveActivity` | `WriteLiveActivityTrackerLog` kræver session snapshot | Live Activity får ikke service-role, kun bruger-session |
| `PersistSet` | `WriteTrackerLog` og `DeduplicateClientAction` | Sætlog er own-user og idempotent |
| `CompleteWorkout` | `WriteOwnData` | Completion event er bundet til `user_id` og `profile_mode` |
| `ProgressCycle` | RPC kræver resolved session | Træningscyklus progression sker server-side |
| Admin/trainer/import uden for trackerflow | `CallAdminFunction`, `CallTrainerClientFunction`, `CallImportFunction` | Tværbruger og privileged flows holdes ude af almindelig klientwrite |

Det giver en klar rapportpointe: BPMN viser, hvornår handlinger sker, mens DCR viser, hvilke handlinger der overhovedet må ske.

## Interoperabilitet i trackerflowet

Trackerflowet er også et godt eksempel på praktisk interoperabilitet:

- iOS appen styrer hovedsessionen.
- watchOS kan modtage session/auth payload og skrive logs under samme RLS-regler.
- Live Activity kan skrive et sæt fra Lock Screen/Dynamic Island med session snapshot.
- Supabase samler logs, completion-events og aktiv session.
- HealthKit kan efter træningen modtage en afsluttet styrketræning som `HKWorkout`.

Det afgørende er, at flere klientflader kan deltage i samme brugerflow uden at dele privilegerede credentials. De deler derimod en brugeridentitet og en backendkontrakt.

## Rapportklar diagramtekst

Forslag til billedtekst for DCR-diagram:

> DCR-modellen beskriver Traeningsmesters autorisationsregler. Appen må kun oprette en anon Supabase-klient efter miljøvalidering, brugerdata kræver resolved session, adminhandlinger kræver server-side validering, og service-role må kun bruges inde i Edge Functions. Modellen viser derfor sikkerhedsreglerne på tværs af iOS, watchOS, Live Activity og backend.

Forslag til billedtekst for BPMN-diagram:

> BPMN-modellen beskriver trackerflowet fra workout-start til historikopdatering. Flowet har en tracker-on gren med sætlogning og Live Activity samt en tracker-off gren, hvor træningen kan afsluttes uden detaljerede logs. Begge grene ender i completion event og eventuel træningscyklus-progression.

## Afgrænsning

Interoperabilitet i den nuværende løsning handler om kontrolleret dataudveksling mellem app, watch, Live Activity, Supabase, Edge Functions og Apple HealthKit. Løsningen implementerer ikke klinisk datadeling, FHIR, EHR-integration eller national sundhedsdataudveksling. Det bør nævnes eksplicit i rapporten, så sundhedsdata-perspektivet ikke overdrives.

## Konklusion

Traeningsmester demonstrerer interoperabilitet på et realistisk bachelorprojektniveau: flere klientflader og backendkomponenter arbejder sammen om samme træningsdata, men uden at bryde least privilege. DCR-modellen dokumenterer adgangsreglerne, BPMN-modellen dokumenterer brugerflowet, og HealthKit-integrationen viser et afgrænset sundhedsdata-perspektiv baseret på samtykke og dataminimering.
