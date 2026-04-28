# Beslutningslog: Arkitektur Og Software Design

Dato: 2026-04-28  
Scope: rapportklar beslutningslog for Traeningsmester iOS, watchOS companion, Live Activity extension og Supabase-backend.  
Kildegrundlag: `NAVIGATOR.md`, `05_arkitektur_data_sikkerhed/arkitektur/*`, `05_arkitektur_data_sikkerhed/data_og_sikkerhed/*`, centrale Swift-filer, Supabase Edge Functions og `SUPABASE_MASTER_SETUP.sql`.

## Formaal

Denne beslutningslog samler de arkitektur- og software designvalg, der er mest relevante for bachelorens problemfelt: hvordan en digital traeningsapp kan understotte motivation og fleksibel haandtering af afvigelser fra et planlagt traeningsforloeb uden at goere afvigelser til en fejltilstand.

Loggen kan bruges direkte i rapportens design- og implementeringsafsnit. Hver beslutning beskriver kontekst, valgt loesning, konsekvens, metodisk relevans og sporbarhed til use cases, krav og diagrammer.

## Beslutningsoverblik

| ID | Beslutning | Primaer begrundelse | Primaer evidens | Krav/use cases |
| --- | --- | --- | --- | --- |
| ADR-01 | Modulopdelt native SwiftUI-klient med typed repositories | Reducere runtime-fejl og holde views fri af backenddetaljer | `RepositoryProtocols.swift`, `SupabaseRepositories.swift`, `Models.swift`, `Payloads.swift` | F-02, F-03, F-04, F-06, NF-03, NF-06, UC-01 til UC-06 |
| ADR-02 | Central `AppState` som orchestration point | Samle auth, navigation, profile mode, tracker og runtimeflow | `AppState.swift`, `RootView.swift` | F-01, F-02, F-09, F-13, F-15, UC-01, UC-06, UC-08 |
| ADR-03 | Supabase RLS og anon key som sikkerhedsgraense | Undgaa privilegerede noegler i klienten | `AppEnvironment.swift`, `SUPABASE_MASTER_SETUP.sql`, Edge Functions | NF-01, NF-02, NF-08, UC-01, UC-09, UC-10, UC-11 |
| ADR-04 | `profile_mode` som eksplicit data- og UI-partition | Adskille personlig traening fra traenerarbejde | `AppProfileMode.swift`, repositories, RLS/views | F-03, F-16, F-18, UC-03, UC-09 |
| ADR-05 | Completion-events adskilt fra trackerlog | Traening skal kunne afsluttes uden detaljeret logging | `WorkoutCompletionService.swift`, `workout_completion_events`, `WorkoutTrackerView.swift` | F-08, F-09, F-10, UC-06, UC-07 |
| ADR-06 | Runtime-first traeningscyklus fremfor kun `plan.current_index` | Understotte makro/meso/deload og realistisk progression | `TrainingCycleRuntimeContext`, cycle RPC, Home/Tracker/Watch | F-13, F-08, F-14, UC-08 |
| ADR-07 | Dedikeret tracker-off flow | Tracker slukket maa ikke betyde, at workout completion mistes | `AppRoute.workoutTrackerWithoutLogging`, `HomeView`, `WorkoutTrackerView` | F-08, F-09, UC-06 |
| ADR-08 | Watch companion via session snapshot og samme repositories | Flytte traeningssituationen til uret uden separat backendmodel | `WatchAppSyncBridge`, `WatchWorkoutStore` | F-14, F-08, F-09, NF-07, UC-07 |
| ADR-09 | Live Activity via App Group snapshot og idempotente writes | Reducere friktion under traening uden at omgaa RLS | `TrackerLiveActivity*`, `client_action_id` | F-15, F-08, NF-07, UC-06 |
| ADR-10 | AI/import via Edge Functions | Beskytte secrets og goere bulk-import kontrollerbar | `ProgramReviewService.swift`, `training-import-manage`, import functions | F-11, F-12, NF-08, UC-02, UC-11 |
| ADR-11 | Admin og trainer-client som servervaliderede boundaries | Lokal UI-state maa ikke give privilegeret adgang | `TrainerClientService.swift`, `admin-control-center`, SQL guards | F-16, F-17, NF-01, NF-02, UC-09, UC-10 |
| ADR-12 | Diagramspor som metodeartefakt | Goere designbeslutninger efterproevbare i rapporten | `diagrams/src/*`, `diagramkatalog.md` | Alle centrale krav og use cases |

## ADR-01: Modulopdelt SwiftUI-Klient Med Typed Repositories

Status: Implementeret.

Kontekst: Appen er migreret fra en FlutterFlow-adfaerd til native SwiftUI. En direkte Supabase-kobling fra views ville give hurtig fremdrift, men den ville ogsaa sprede querylogik, schemaantagelser og adgangskontroludtryk ind i UI-laget.

Beslutning: Dataadgang samles bag repository-protokoller og typed domain-/payloadmodeller. Views arbejder gennem `RepositoryContainer`, feature view models og `AppState`, ikke direkte mod Supabase.

Konsekvens: Loesningen giver flere protokoller og en stor Supabase-implementeringsfil, men den goer schema-kontrakter testbare. Den understotter ogsaa parallel videreudvikling, fordi featureviews kan aendres uden at omskrive backendadgang.

Metodisk relevans: Valget kobler software design til bachelorens krav om fleksibilitet. Naar workout, historik, cyklus og profiltilstand er typed, kan afvigelser fra plan modelleres som gyldige tilstande fremfor som UI-specialtilfaelde.

Sporbarhed:

- Kode: `Traeningsmester/Core/Data/RepositoryProtocols.swift`, `Traeningsmester/Core/Data/SupabaseRepositories.swift`, `Traeningsmester/Core/Domain/Models.swift`, `Traeningsmester/Core/Domain/Payloads.swift`.
- Krav/use cases: F-02 til F-06, NF-03, NF-06, UC-01 til UC-06.
- Diagrammer: containerdiagrammet viser relationen mellem SwiftUI features, AppState, repository protocols og Supabase repositories.

## ADR-02: Central AppState Som Orchestration Point

Status: Implementeret med bevidst tradeoff.

Kontekst: Traeningsmester har globale flows, der krydser tabbar, pushed routes, onboarding, auth, StoreKit, watch sync, Live Activity og traeningscyklus. Hvis hver feature selv ejede denne koordinering, ville "naeste handling" blive inkonsistent.

Beslutning: `AppState` er applikationens centrale orchestration point for bootstrap, auth-session, settings, profiltilstand, navigation, aktiv plan, tracker runtime, pending completion, aktiv traeningscyklus, adminperspektiv og watch/Live Activity snapshots.

Konsekvens: `AppState` har bredt ansvar. Risikoen er teknisk kompleksitet i en central fil. Modvaegten er, at specialiserede services som `WorkoutCompletionPersistenceService`, `ProgramReviewService`, `TrainerClientService` og repository-kontrakter flytter afgraensede opgaver ud af views.

Metodisk relevans: Bachelorens problem handler ikke kun om at gemme data, men om at styre brugerens mentale model efter pauser, afvigelser og gennemfoerte pas. Et samlet state-lag goer det muligt at vise samme beslutning paa Home, Tracker, watch og Live Activity.

Sporbarhed:

- Kode: `Traeningsmester/App/AppState.swift`, `Traeningsmester/App/RootView.swift`, `Traeningsmester/Core/Support/WorkoutCompletionService.swift`.
- Krav/use cases: F-01, F-02, F-09, F-13, F-15, UC-01, UC-06, UC-08.
- Diagrammer: tracker BPMN og dataflow-sekvensen viser, at completion, cycle progression og Live Activity opdatering sker efter samme afslutningshandling.

## ADR-03: Supabase RLS Og Anon Key Som Primaer Sikkerhedsgraense

Status: Implementeret.

Kontekst: Appen distribueres til brugere og maa derfor ikke indeholde privilegerede backendnoegler. Samtidig har appen brugerdata, traener-klientrelationer, historik, adminfunktioner og importjobs.

Beslutning: Klienten bruger kun Supabase anon/publishable key. `AppEnvironment` afviser placeholder keys og JWT-role `service_role`. RLS, security definer RPC og Edge Functions udgoer sikkerhedsgraensen for dataadgang og privilegerede operationer.

Konsekvens: Klienten kan ikke selv "rette" manglende adgang med hoejere privilegier. Det tvinger et klarere backenddesign, men kraever samtidig vedligeholdelse af SQL-politikker og integrationstest for kritiske flows.

Metodisk relevans: Sikkerhedsmodellen er en del af software designet, ikke en efterfoelgende driftsting. Det er vigtigt i rapporten, fordi appen haandterer personlige traeningsdata og relationer mellem brugere.

Sporbarhed:

- Kode/SQL: `Traeningsmester/Core/Config/AppEnvironment.swift`, `SUPABASE_MASTER_SETUP.sql`, `05_arkitektur_data_sikkerhed/data_og_sikkerhed/sikkerhedsnotat.md`.
- Krav/use cases: NF-01, NF-02, NF-08, UC-01, UC-09, UC-10, UC-11.
- Diagrammer: authorization DCR-modellen beskriver, at `UseServiceRoleInsideFunction` kun er gyldigt inde i Edge Function runtime.

## ADR-04: Profile Mode Som Eksplicit Partition

Status: Implementeret.

Kontekst: Samme app skal understotte personlig bruger, traener og klientrelaterede flows. Uden en eksplicit profiltilstand ville der vaere risiko for, at personlige programmer, traenerprogrammer og klientdata blev blandet i queries eller UI.

Beslutning: `AppProfileMode` modellerer `personal` og `coach`, og relevante tabeller, payloads, views og repositories bruger `profile_mode`. Watch afviser coach-profilen for workout-flowet og beder brugeren synkronisere personlig profil fra iPhone.

Konsekvens: Nogle repositories og payloads skal altid have profile mode med. Det er mere verbose, men datadeling bliver eksplicit og testbar.

Metodisk relevans: Valget viser, hvordan krav om flere aktørtyper omsættes til en systematisk data- og UI-afgraensning. Det styrker rapportens argument om kontrolleret kompleksitet.

Sporbarhed:

- Kode/SQL: `AppProfileMode.swift`, `AppState.swift`, `WatchWorkoutStore.swift`, `SUPABASE_MASTER_SETUP.sql`.
- Krav/use cases: F-03, F-16, F-18, UC-03, UC-07, UC-09.
- Diagrammer: ERD viser `profile_mode` paa centrale modeller, og system context viser forskellige aktører mod samme iOS-app.

## ADR-05: Completion-Events Adskilt Fra Trackerlog

Status: Implementeret.

Kontekst: En workout kan vaere reel og motivationsmaessigt vigtig, selv om brugeren ikke logger hvert sæt. Hvis historik og progression kun byggede paa `trackerlog`, ville tracker-off traeninger og ufuldstaendige logs blive usynlige.

Beslutning: Afsluttede traeninger gemmes i `workout_completion_events`, separat fra `trackerlog`. `WorkoutCompletionPersistenceService` skriver completion-state til settings, recorder idempotent completion-event med `client_action_id` og kan markere completion som reverted.

Konsekvens: Historik og Home kan skelne mellem detaljerede sætlogs og "jeg gennemfoerte passet". Det giver et ekstra datalag og retry-haandtering, men loeser et centralt motivationsproblem.

Metodisk relevans: Dette er en noeglebeslutning i bacheloren. Den tekniske model anerkender afvigelser og ufuldstaendig registrering som gyldige brugerhandlinger.

Sporbarhed:

- Kode/SQL: `WorkoutCompletionService.swift`, `WorkoutTrackerView.swift`, `workout_completion_events`, `user_settings.last_workout_completion_*`, `admin_user_workout_mood_counts`.
- Krav/use cases: F-08, F-09, F-10, UC-06, UC-07.
- Diagrammer: tracker BPMN viser, at baade tracker og no-tracker flow ender i `WorkoutCompletionService`.

## ADR-06: Runtime-First Traeningscyklus Fremfor Kun Planindeks

Status: Implementeret.

Kontekst: Klassisk `plan.current_index` kan pege paa naeste traeningsdag, men den kan ikke i sig selv modellere mesocyklus, deload, blokke, pending end choice eller ugeoverrides.

Beslutning: Naar en aktiv traeningscyklus findes, prioriterer appen `TrainingCycleRuntimeContext` og runtime-valgt workout over normal aktiv planlogik. Backend-RPC styrer aktivering, resolution, progression efter workout, end action og resolved exercise targets.

Konsekvens: Programstrukturen bliver mere fleksibel uden at fjerne de eksisterende plan/workout-tabeller. Ulempen er, at Home, Tracker og Watch skal respektere runtime-status og laase nogle manuelle valg, mens cyklussen er aktiv.

Metodisk relevans: Valget viser en konkret softwareloesning paa afvigelser fra lineær progression. Appen kan bevare en "naeste rigtige handling" selv naar programmet styres af blokke og deload fremfor en simpel dagtaeller.

Sporbarhed:

- Kode/SQL: `TrainingCycleRuntimeContext`, `TrainingCycleRepository`, `AppState.refreshTrainingCycleRuntimeStateIfPossible`, `tm_activate_training_cycle_next_training`, `tm_progress_training_cycle_after_workout`, `tm_resolve_training_cycle_targets`.
- Krav/use cases: F-13, F-08, F-14, UC-08.
- Diagrammer: ERD viser cycle/runtime-tabeller, og BPMN viser progression efter completion.

## ADR-07: Dedikeret Tracker-Off Flow

Status: Implementeret.

Kontekst: Indstillingen "tracker fra" skulle ikke sende brugeren til en editor eller give en tom oplevelse. Brugeren har stadig brug for dagens traening, afslutningshandling og progression.

Beslutning: `AppRoute.workoutTrackerWithoutLogging` aabner en dedikeret no-tracker traeningsvisning. Home sender til normal tracker eller no-tracker route ud fra settings. No-tracker afslutning kalder samme completion-persistens som trackerflowet, men uden at skrive sætlogs.

Konsekvens: Appen bevarer dagstruktur og completion, selv naar detaljeret logging er slukket. HealthKit-/completion-flow kan fortsat bruge sessionstart/sluttid, mens historiske sætdata ikke foregives at eksistere.

Metodisk relevans: Beslutningen er direkte koblet til motivation: lavere registreringsfriktion maa ikke straffe brugeren i progressionslogikken.

Sporbarhed:

- Kode: `AppRoute.swift`, `HomeView.startWorkout`, `WorkoutTrackerView.finishTrackerOffWorkout`.
- Krav/use cases: F-08, F-09, UC-06.
- Diagrammer: tracker BPMN har gatewayen `Tracker enabled?` med separate paths til `OpenTracker` og `OpenNoTracker`, der samles ved completion.

## ADR-08: Watch Companion Via Session Snapshot Og Samme Backendkontrakter

Status: Implementeret.

Kontekst: I en traeningssituation kan telefonen vaere upraktisk. Watch skal derfor kunne vise dagens workout, logge, markere ovelser og afslutte traening uden at introducere en parallelt inkonsistent datamodel.

Beslutning: iOS synkroniserer auth/session/settings/completion snapshot via WatchConnectivity. Watch appen bruger `WatchWorkoutStore`, genopretter session ved behov, henter samme plan- og cycle runtime-data og skriver via de samme repositorykontrakter.

Konsekvens: Watch er ikke et isoleret offlineprodukt. Den er en companion, der prioriterer konsistens med iOS og Supabase. Det reducerer duplikation, men goer session sync til et kritisk integrationspunkt.

Metodisk relevans: Valget viser, hvordan loesningen flytter motivationsstoette ind i konteksten, hvor brugeren faktisk traener, uden at svaekke sikkerhedsmodellen.

Sporbarhed:

- Kode: `WatchAppSyncBridge.swift`, `WatchAuthSyncPayload.swift`, `TraeningsmesterWatch/WatchWorkoutStore.swift`, `WatchRootView.swift`.
- Krav/use cases: F-14, F-08, F-09, NF-07, UC-07.
- Diagrammer: watch sync-sekvensdiagrammet beskriver snapshot fra iOS til watch og authenticated anon reads/writes.

## ADR-09: Live Activity Med App Group Snapshot Og Idempotente Writes

Status: Implementeret.

Kontekst: Under workout er det hoej friktion at aabne appen for at se naeste sæt, pausetimer eller gemme simple justeringer. Samtidig maa en extension ikke faa service-role adgang.

Beslutning: Tracker gemmer et `TrackerLiveActivitySessionSnapshot` i App Group storage. Live Activity extension bruger snapshot med anon key og brugerens session tokens, opretter authenticated Supabase client, verificerer row/workout relation og skriver trackerlog med `client_action_id`.

Konsekvens: Lock Screen/Dynamic Island kan vise og opdatere traeningsstate, mens RLS stadig gaelder. Idempotency reducerer risikoen for duplicate logs fra gentagne intents.

Metodisk relevans: Beslutningen forbinder interaktionsdesign med backenddesign. Lavere friktion opnaas uden at lave sikkerhedsomveje.

Sporbarhed:

- Kode/SQL: `TrackerLiveActivitySharedStore.swift`, `TrackerLiveActivityIntents.swift`, `TrackerLiveActivityProjection.swift`, `TraeningsmesterLiveActivities/TrackerLiveActivityWidget.swift`, unik indeks paa `trackerlog("userID", client_action_id)`.
- Krav/use cases: F-15, F-08, NF-07, UC-06.
- Diagrammer: system context viser ActivityKit, App Group og Live Activity extension som separate integrationer.

## ADR-10: AI- Og Importflows Via Edge Functions

Status: Implementeret.

Kontekst: Programanalyse, AI-plan, programimport og historikimport kan involvere eksterne services, OCR-lignende parsing, storage paths, bulk-normalisering og katalogmatching.

Beslutning: Klienten kalder server-side Supabase Edge Functions gennem `ProgramReviewService` og `training-import-manage`. OpenAI/service secrets og privileged joborchestration placeres ikke i appen.

Konsekvens: Import kan previewes og committes kontrolleret, og fejl kan mappes til brugerforstaaelige `TM-*` koder. Det giver flere backendkomponenter, men bevarer en sikker og auditbar importvej.

Metodisk relevans: Onboarding og import er ikke kun convenience. De reducerer overgangsomkostningen fra brugerens eksisterende traeningsvaner til appens struktur, hvilket er centralt for adoption og motivation.

Sporbarhed:

- Kode/functions: `ProgramReviewService.swift`, `PremiumView.swift`, `program-review-analyze`, `program-plan-questionnaire`, `program-import-normalize`, `history-import-normalize`, `training-import-manage`.
- Krav/use cases: F-11, F-12, NF-08, UC-02, UC-11.
- Diagrammer: containerdiagrammet viser Edge Functions som separat backendlag mellem klient og Supabase/eksterne services.

## ADR-11: Admin Og Trainer-Client Som Servervaliderede Boundaries

Status: Implementeret.

Kontekst: Træner- og adminflows involverer tværbrugerdata. Lokal UI-state er utilstraekkelig som autorisationsgrundlag.

Beslutning: Trainer-client handlinger gaar via `trainer-client-manage`, og adminhandlinger via `admin-control-center`. Adminvalidering sker server-side med `tm_current_user_is_admin` og fallback check mod `user_settings.is_admin`. SQL-politikker afgraenser trainer/client relationer, og activity events bruges som auditspor.

Konsekvens: Klienten kan vise eller skjule indgange, men backend afgør reelt, om handlinger er tilladt. Det betyder mere serverkode, men mindre risiko for cross-user adgang.

Metodisk relevans: Beslutningen viser, hvordan aktøranalyse omsættes til softwaregrænser. Den er vigtig i rapporten, fordi systemets fleksibilitet ikke maa ske paa bekostning af dataminimering eller adgangskontrol.

Sporbarhed:

- Kode/functions/SQL: `TrainerClientService.swift`, `trainer-client-manage/index.ts`, `admin-control-center/index.ts`, `tm_current_user_is_admin`, RLS paa `trainer_clients` og `trainer_client_plan_links`.
- Krav/use cases: F-16, F-17, NF-01, NF-02, UC-09, UC-10.
- Diagrammer: authorization DCR-modellen viser, at admin operationer kraever `ValidateAdminServerSide`.

## ADR-12: Diagramspor Som Metodeartefakt

Status: Implementeret som kildefiler.

Kontekst: Bacheloren skal ikke kun paastaa en arkitektur, men kunne vise hvordan beslutninger, krav og implementering haenger sammen.

Beslutning: Diagramkilder gemmes lokalt i tekstbaserede formater: Mermaid for system context og ERD, PlantUML for containerarkitektur, BPMN for tracker/completion-flow og DCR-style tekst for autorisation.

Konsekvens: Diagrammer kan versioneres og reviewes sammen med kode. Der blev ikke renderet PNG/SVG i denne run, fordi lokale renderere ikke var tilgaengelige, men kilderne er reproducerbare.

Metodisk relevans: Diagramsporet giver triangulering mellem krav, designbeslutninger, datamodel og tests. Det styrker rapportens efterproevbarhed.

Sporbarhed:

- Filer: `02_figurer_og_screenshots/diagrammer/kilder/system_context.mmd`, `container_architecture.puml`, `data_model_er.mmd`, `tracker_flow.bpmn`, `authorization_dcr.md`.
- Krav/use cases: Alle centrale krav, saerligt F-08, F-09, F-13, F-14, F-15, F-16, F-17, NF-01 og NF-02.

## Kravkobling Til Designbeslutninger

| Krav | Relevant beslutning | Forklaring |
| --- | --- | --- |
| F-08 Tracker logging og timer | ADR-01, ADR-02, ADR-07, ADR-09 | Tracker er typed, centraliseret i state, har no-tracker variant og kan eksponeres i Live Activity. |
| F-09 Afsluttet workout uafhaengigt af trackerlog | ADR-05, ADR-07, ADR-08 | Completion-events skrives fra iOS, no-tracker og watch uden krav om detaljerede logs. |
| F-13 Traeningscyklus runtime | ADR-02, ADR-06 | Aktiv runtime overstyrer planindeks og progressionslogik efter workout. |
| F-14 Watch companion | ADR-08 | Watch bruger samme session- og repositorykontrakter. |
| F-15 Live Activity | ADR-09 | Extension skriver idempotent med brugerens authenticated anon-session. |
| F-16 Trainer-client | ADR-04, ADR-11 | Profile mode og Edge Function afgraenser traenerrelationer. |
| F-17 Admin-center | ADR-03, ADR-11 | Adminadgang servervalideres og auditlogges. |
| NF-01 Ingen service-role i klient | ADR-03, ADR-09, ADR-10, ADR-11 | Privilegerede flows flyttes til Edge Functions eller RLS/RPC. |
| NF-02 RLS som primaer graense | ADR-03, ADR-04, ADR-11 | Cross-user adgang kontrolleres i backend. |
| NF-06 Typed datakontrakter | ADR-01 | Models/payloads og tests reducerer schemafejl. |

## Afvigelser Fra Oprindelig Lineaer Planmodel

| Oprindelig/naiv model | Implementeret model | Hvorfor det er relevant |
| --- | --- | --- |
| Naeste workout bestemmes kun af `plan.current_index`. | Aktiv cycle runtime kan vaelge workout og pause normal planaktivitet. | Understotter periodisering, deload og cyklusafslutning. |
| En gennemfoert traening findes kun, hvis brugeren logger sæt. | Completion-event findes uafhaengigt af trackerlog. | Tracker-off og ufuldstaendig logging taeller stadig som fremdrift. |
| Mobilappen er eneste traeningsinterface. | Watch og Live Activity bruger samme backendkontrakter. | Mindre friktion i traeningssituationen. |
| Admin/traener er UI-roller. | Admin/traener er servervaliderede boundaries. | Fleksibilitet maa ikke skabe uautoriseret datadeling. |
| AI/import kan kaldes direkte fra klient. | AI/import gaar via Edge Functions og jobmodel. | Secrets, bulk writes og katalogmatching kontrolleres server-side. |

## Brug I Rapport

Anbefalet brug:

- Brug ADR-05, ADR-06 og ADR-07 i afsnittet om motivation og afvigelser fra plan.
- Brug ADR-03 og ADR-11 i sikkerheds- og arkitekturafsnittet.
- Brug ADR-08 og ADR-09 i afsnittet om traeningssituationen som interaktionskontekst.
- Brug ADR-12 som metodeargument for sporbarhed mellem krav, diagrammer og implementering.

