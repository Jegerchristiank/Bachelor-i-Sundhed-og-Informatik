# Krav og Traceability

Dato: 2026-04-28  
Formål: koble funktionelle og ikke-funktionelle krav til faktiske repoartefakter. Tabellen bruger anonymiserede aktører og beskriver ikke persondata.

## Funktionelle krav

| ID | Krav | Kilde/implementation | Verifikation i repo |
| --- | --- | --- | --- |
| F-01 | Systemet skal understøtte email-login, signup, social login-hooks, logout, password recovery og session restore. | `AuthRepository`, `SupabaseAuthRepository`, `LoginView`, `AppState`, `RootView` | `Tests/Integration/SupabaseIntegrationTests.swift`, auth callback logic i `AppState` |
| F-02 | Appen skal bootstrappe miljø, repositories, session og settings før app-shell. | `TraeningsmesterApp`, `AppState.bootstrapIfNeeded`, `AppEnvironment`, `SupabaseRepositoryProviderFactory` | `AppEnvironment.swift`, `JWTClaimsDecoderTests.swift` |
| F-03 | Brugere skal kunne oprette, hente, opdatere, aktivere og dele træningsprogrammer. | `PlanRepository`, `SupabasePlanRepository`, `TrainingProgramView`, `AddProgramView` | `PlanProgressCalculatorTests.swift`, `PlanProgressDecodingTests.swift`, integration tests |
| F-04 | Brugere skal kunne oprette og redigere workouts/træningsdage og knytte dem til programmer. | `WorkoutRepository`, `PlanWorkoutPayload`, `TrainingProgramView`, `AddProgramView` | `WorkoutExercisePayloadEncodingTests.swift`, `WorkoutExerciseDecodingTests.swift` |
| F-05 | Brugere skal kunne tilføje øvelser med sæt, reps, vægt, pause, AMRAP/effort og supersetmetadata. | `WorkoutExercise`, `WorkoutExercisePayload`, `WorkoutTrackerView`, `workout_exercises` | `TMSetDomainModelTests.swift`, `WorkoutExercisePayloadEncodingTests.swift` |
| F-06 | Øvelsessøgning skal bruge fælles normalisering og synonymer. | `ExerciseSearchCatalog`, `ExerciseRepository`, `ExercisesView`, `MatchView` | `ExerciseFormCatalogTests.swift`, `SupabaseDeduplicationHelpersTests.swift` |
| F-07 | Brugere skal kunne like/swipe øvelser og hente liked/parrede øvelser. | `MatchRepository`, `MatchPayload`, `MatchView`, `match` | `MatchCandidateFilterTests.swift` |
| F-08 | Tracker skal kunne logge sæt, hente historik, redigere/slette logs og håndtere pause-/sæt-timere. | `TrackerRepository`, `WorkoutTrackerView`, `trackerlog`, `active_workout_session_state` | `TrackerLogPayloadEncodingTests.swift`, `WorkoutTrackerDefaultsRestSecondsTests.swift` |
| F-09 | Afsluttet workout skal persisteres uafhængigt af trackerlog. | `WorkoutCompletionService`, `WorkoutCompletionRepository`, `workout_completion_events` | `HomeSnapshotTests.swift`, `AppStateNextDayPromptTests.swift` |
| F-10 | Historik skal kunne læses ud fra trackerlog og completion data. | `HistoryRepository`, `HistoryView`, `user_trackerlog_exercises`, `trackerlog` | Integration tests og history feature |
| F-11 | Onboarding skal styres af step graph og kunne oprette/importere startprogram. | `OnboardingModels.swift`, `TMOnboardingFlowView`, `ProgramReviewService` | `OnboardingV3Tests.swift`, `ProgramReviewServiceTests.swift` |
| F-12 | Premiumbrugere skal kunne bruge programreview, planbuilder, programimport og historikimport. | `PremiumView`, `ProgramReviewService`, Supabase functions `program-review-analyze`, `program-plan-questionnaire`, `program-import-normalize`, `history-import-normalize`, `training-import-manage` | `ProgramReviewServiceTests.swift`, function helper tests |
| F-13 | Premiumbrugere skal kunne oprette og aktivere træningscyklus med runtime progression. | `TrainingCycleRepository`, `TrainingCycleViews`, cycle models/RPC | `TrainingCycleDeloadPlannerTests.swift`, `TrainingCycleFlowCoordinatorTests.swift` |
| F-14 | Watch appen skal kunne vise dagens træning, logge og afslutte workout. | `TraeningsmesterWatchApp`, `WatchWorkoutStore`, `WatchRootView`, `WatchAuthSyncBridge` | `WatchAuthSyncPayloadTests.swift` |
| F-15 | iOS Live Activity skal vise trackerstatus og understøtte idempotente intent-writes. | `TrackerLiveActivityCenter`, `TrackerLiveActivityProjection`, `TrackerLiveActivityIntents`, `TraeningsmesterLiveActivities` | `TrackerLiveActivityProjectionTests.swift`, `TrackerLogPayloadEncodingTests.swift` |
| F-16 | Træner skal kunne administrere klientrelationer og klientaktivitet. | `ClientsView`, `TrainerClientService`, `trainer-client-manage`, `trainer_clients` | `TrainerClientRepositoryPerformanceTests.swift` |
| F-17 | Admin skal kunne åbne server-valideret admin-center. | `SettingsView`, `AdminControlCenterRepository`, `admin-control-center`, `user_settings.is_admin` | `AdminControlCenterModelsTests.swift`, `AdminActivityViewModelSupportTests.swift` |
| F-18 | Bruger skal kunne ændre indstillinger for tracker, flow, theme, vægtenhed, telefon og subscription tier. | `SettingsRepository`, `SettingsView`, `UserSettings`, `StoreKitSubscriptionService` | `SettingsPayloadTests.swift`, `AppIconAppearanceTests.swift` |

## Ikke-funktionelle krav

| ID | Krav | Kilde/implementation | Verifikation i repo |
| --- | --- | --- | --- |
| NF-01 | Klienten må aldrig indeholde service-role key. | `AppEnvironment` afviser JWT role `service_role`; Edge Functions håndterer privilegerede flows. | `JWTClaimsDecoderTests.swift`, manuel config review |
| NF-02 | RLS skal være primær sikkerhedsgrænse for brugerdata. | `SUPABASE_MASTER_SETUP.sql` aktiverer RLS og policies på centrale tabeller. | Integration tests, SQL review |
| NF-03 | Views må ikke tale direkte med Supabase. | `RepositoryProtocols.swift`, `SupabaseRepositories.swift`, feature views via repositories/app state. | Code review |
| NF-04 | Fejl skal være brugerforståelige og teknisk sporbare. | `AppError.swift`, app dialogs/status messages, diagnostics repositories. | `DiagnosticsPayloadTests.swift` |
| NF-05 | UI skal følge fælles designkontrakt. | `design.md`, `TMTheme`, `TMComponents`, `TMMotionPrimitives` | `Docs/DesignDebtScorecard.md` |
| NF-06 | Datakontrakter skal være typed og testbare. | `Models.swift`, `Payloads.swift`, repository protocols. | payload/model unit tests |
| NF-07 | Watch- og Live Activity-relaterede ændringer skal valideres særskilt. | Separate targets og files under `TraeningsmesterWatch*` og `TraeningsmesterLiveActivities` | Watch payload og Live Activity projection tests |
| NF-08 | Import og AI-relaterede flows må ikke kalde OpenAI direkte fra klient. | Supabase Edge Functions og `ProgramReviewService`. | Function/code review |
| NF-09 | Appen skal kunne adskille Debug, Staging og Release config. | `Config/*.xcconfig`, `Project.yml`, `AppEnvironment.environmentName` | Build config review |
| NF-10 | Kritiske hot paths skal have performance baseline. | `Tests/Unit/AppPerformanceBaselineTests.swift`, `Docs/PerformancePlaybook.md` | Unit/performance tests |

## Traceability til use cases

| Use case | Dækkede krav | Primære filer |
| --- | --- | --- |
| UC-01 Opret konto og log ind | F-01, F-02, NF-01, NF-02 | `LoginView.swift`, `AppState.swift`, `AppEnvironment.swift`, `SupabaseRepositories.swift` |
| UC-02 Gennemfør onboarding | F-02, F-11, F-12 | `OnboardingModels.swift`, `TMOnboardingFlowView.swift`, `ProgramReviewService.swift` |
| UC-03 Opret/rediger træningsprogram | F-03, F-04, NF-02, NF-03 | `TrainingProgramView.swift`, `AddProgramView.swift`, `PlanRepository` |
| UC-04 Tilføj træningsdag og øvelser | F-04, F-05, F-06 | `WorkoutRepository`, `TrackerRepository`, `WorkoutExercisePayload` |
| UC-05 Find og like øvelse | F-06, F-07 | `ExercisesView.swift`, `MatchView.swift`, `ExerciseFormCatalog.swift` |
| UC-06 Start workout med tracker | F-08, F-09, F-10, F-15 | `WorkoutTrackerView.swift`, `WorkoutCompletionService.swift`, `TrackerLiveActivity*` |
| UC-07 Brug watchOS companion | F-14, F-08, F-09, NF-07 | `WatchWorkoutStore.swift`, `WatchAuthSyncBridge.swift` |
| UC-08 Aktiv træningscyklus | F-13, F-08, F-14 | `TrainingCycleViews.swift`, `TrainingCycleRepository`, cycle RPC |
| UC-09 Træner administrerer klient | F-16, NF-02, NF-08 | `ClientsView.swift`, `TrainerClientService.swift`, `trainer-client-manage` |
| UC-10 Admin håndterer bruger | F-17, NF-01, NF-02 | `SettingsView.swift`, `admin-control-center`, admin SQL functions |
| UC-11 Importer program/historik | F-12, NF-08 | `PremiumView.swift`, `ProgramReviewService.swift`, import Edge Functions |

## Testafgrænsning for dette artefakt

Der blev efterfølgende kørt build/test-verifikation som del af samme bachelor-run. Se `06_verifikation/verifikationsrapport.md` for fulde logreferencer.

Kort status:

- iOS Debug build: bestået.
- Unit tests: 556 tests, 0 failures.
- Integration tests: 5 tests, 0 failures, 4 skipped pga. manglende Supabase test credentials.
- watchOS build: bestået.
- Live Activity build: bestået.
- Edge Function helper tests: ikke kørt, Deno manglede.
