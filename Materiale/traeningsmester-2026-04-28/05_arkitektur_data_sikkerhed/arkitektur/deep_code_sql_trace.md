# Deep Code/SQL Trace

Dato: 2026-04-28  
Formål: rapportklar dybdesporing fra problemformulering til Swift-kode, Supabase SQL/RLS, Edge Functions, diagrammer og eksisterende testartefakter.  
Scope: centrale fleksibilitets-, integrations- og sikkerhedsflows i TræningsMester. Der er ikke kørt nye tests i denne audit.

## Problemspor

Den autoritative problemformulering spørger, hvordan en digital træningsapp kan understøtte programstruktur, progression og feedback, så brugeren kan håndtere afvigelser fra et planlagt træningsforløb uden øget demotivation eller frafald.

Det tekniske spor i repoet svarer på spørgsmålet ved at adskille:

- planlagt struktur: `plan`, `workout`, `plan_workouts`, `workout_exercises`
- faktisk udførelse: `trackerlog`, `workout_completion_events`
- runtime-beslutninger: `active_workout_session_state`, `training_cycle_runtime_state`
- adgangsgrænser: `profile_mode`, RLS, Edge Functions, StoreKit/entitlement state
- friktionsreduktion: tracker-off, watchOS, Live Activity og importflows

Kilde for problemformulering: `BachelorMateriale/2026-04-28-traeningsmester/01_rapportgrundlag/problemformulering/problemformulering_autoritativ.md`.

## Samlet Arkitekturtrace

| Lag | Hovedansvar | Centrale filer |
| --- | --- | --- |
| App bootstrap og state | Auth, session, settings, profile mode, navigation, completion state, cycle runtime | `Traeningsmester/App/AppState.swift`, `Traeningsmester/App/RootView.swift` |
| Feature UI | Home, tracker, premium, clients, settings, onboarding | `Traeningsmester/Features/Home/HomeView.swift`, `Traeningsmester/Features/Tracker/WorkoutTrackerView.swift`, `Traeningsmester/Features/Premium/PremiumView.swift`, `Traeningsmester/Features/Clients/ClientsView.swift`, `Traeningsmester/Features/Settings/SettingsView.swift`, `Traeningsmester/Features/Onboarding/TMOnboardingFlowView.swift` |
| Typed kontrakter | Modeller, payloads, routes og repository-protokoller | `Traeningsmester/Core/Domain/Models.swift`, `Traeningsmester/Core/Domain/Payloads.swift`, `Traeningsmester/Core/Navigation/AppRoute.swift`, `Traeningsmester/Core/Data/RepositoryProtocols.swift` |
| Supabase repositories | Typed dataadgang, RPC-kald, Edge Function HTTP-klienter | `Traeningsmester/Core/Data/SupabaseRepositories.swift`, `Traeningsmester/Core/Support/ProgramReviewService.swift`, `Traeningsmester/Core/Support/TrainerClientService.swift` |
| Integrationer | WatchConnectivity, ActivityKit, StoreKit, App Group snapshot | `Traeningsmester/Core/Support/WatchAppSyncBridge.swift`, `TraeningsmesterWatch/WatchWorkoutStore.swift`, `Traeningsmester/Core/LiveActivity/*`, `Traeningsmester/Core/Support/StoreKitSubscriptionService.swift` |
| SQL/backend | Schema, RLS, RPC, triggers, Edge Functions | `SUPABASE_MASTER_SETUP.sql`, `supabase/functions/*`, `supabase/migrations/*` |

## 1. Tracker-Off Completion

**Problemkobling:** Brugeren skal kunne gennemføre en træning uden at logge hvert sæt. Det reducerer friktion og understøtter afvigelser fra perfekt datadisciplin.

**Swift trace:**

| Fil | Rolle |
| --- | --- |
| `Traeningsmester/Core/Navigation/AppRoute.swift` | Definerer route `workoutTrackerWithoutLogging(workoutID:)`, så no-tracker flowet er en eksplicit navigationstilstand. |
| `Traeningsmester/Features/Home/HomeView.swift` | Sender brugeren til no-tracker workout, når trackerindstillingen er slået fra. |
| `Traeningsmester/Features/Tracker/WorkoutTrackerView.swift` | `finishTrackerOffWorkout()` afslutter workout uden sætlogs, men kalder samme completion-persistens som tracker-on flowet. |
| `Traeningsmester/App/AppState.swift` | `markWorkoutCompletedPersisted` samler completion, lokal tracker state og eventuel cycle progression. |
| `Traeningsmester/Core/Support/WorkoutCompletionService.swift` | Skriver completion state i settings og forsøger at skrive en idempotent completion-event med retry queue. |

**SQL trace:**

| SQL objekt | Rolle |
| --- | --- |
| `workout_completion_events` i `SUPABASE_MASTER_SETUP.sql` | Tabel for afsluttede workouts uafhængigt af `trackerlog`; indeholder `user_id`, `profile_mode`, `workout_id`, `completed_at`, `client_action_id`, `reverted_at`, `source`. |
| `uq_workout_completion_events_user_client_action` | Unikt indeks på `(user_id, client_action_id)` til idempotency. |
| RLS policies `tm_workout_completion_events_*` | Ejerbaseret select/insert/update via `auth.uid() = user_id`. |
| `user_settings.last_workout_completion_*` | Persistent pending next-day prompt, så appen kan genoptage flow efter relaunch. |

**Eksisterende testdækning:** `Tests/Unit/AppStateNextDayPromptTests.swift` dækker prompt, undo, tracker-off navigationblokering og runtime-preferred workout state. `Tests/Unit/HomeSnapshotTests.swift` dækker completion-events som datakilde til Home snapshot/mood. Integrationstestfilen `Tests/Integration/SupabaseIntegrationTests.swift` findes, men denne audit har ikke kørt den.

**Auditvurdering:** Claimet er stærkt dokumenteret. Completion er ikke en UI-undtagelse, men et selvstændigt datalag.

## 2. Cycle Runtime

**Problemkobling:** Progression skal kunne være mere adaptiv end `plan.current_index`, især ved mesocyklus, deload og valgpunkter efter afslutning.

**Swift trace:**

| Fil | Rolle |
| --- | --- |
| `Traeningsmester/Core/Domain/Models.swift` | Indeholder `TrainingCycle`, `TrainingCycleRuntimeState`, `TrainingCycleRuntimeContext`, deload planner, flow coordinator og target presentation. |
| `Traeningsmester/Core/Data/RepositoryProtocols.swift` | Definerer `TrainingCycleRepository` med create/update, runtime resolve, activation, progression, end action og target resolution. |
| `Traeningsmester/Core/Data/SupabaseRepositories.swift` | Kalder RPC'erne `tm_activate_training_cycle_next_training`, `tm_resolve_active_training_cycle_day`, `tm_progress_training_cycle_after_workout`, `tm_handle_training_cycle_end_action`, `tm_resolve_training_cycle_targets`. |
| `Traeningsmester/App/AppState.swift` | Progression efter completion sker via `progressActiveTrainingCycleAfterWorkoutCompletion`; aktiv runtime prioriteres i personlig profil. |
| `Traeningsmester/Features/Premium/TrainingCycleViews.swift` | Authoring/aktivering af avancerede træningscyklusser. |
| `Traeningsmester/Features/Home/HomeView.swift`, `Traeningsmester/Features/Tracker/WorkoutTrackerView.swift`, `TraeningsmesterWatch/WatchWorkoutStore.swift` | Bruger runtime context til dagens træning og cycle targets. |

**SQL trace:**

| SQL objekt | Rolle |
| --- | --- |
| `training_cycles`, `training_cycle_mesocycles`, `training_cycle_weeks`, `training_cycle_day_slots` | Authoringstruktur for makro/meso/uge/dag. |
| `training_cycle_exercise_rules`, `training_cycle_exercise_week_overrides`, `training_cycle_week_metric_defaults` | Per-øvelse/per-uge target-regler. |
| `training_cycle_runtime_state` | Runtime-tabel med aktiv uge, dag, workout, deloadstatus og pending end choice. |
| `uq_training_cycle_runtime_active_per_user_profile` | Sikrer højst én aktiv runtime per bruger/profil. |
| `tm_current_user_has_cycle_premium()` | Gate for premiumadgang til cycle runtime. |
| `tm_activate_training_cycle_next_training` | Aktiverer cyklus og gemmer tidligere aktiv plan. |
| `tm_resolve_active_training_cycle_day` | Finder aktiv runtime for `auth.uid()` i personlig profil. |
| `tm_progress_training_cycle_after_workout` | Flytter runtime efter gennemført workout. |
| `tm_handle_training_cycle_end_action` | Håndterer valg ved afslutning/genstart/næste cyklus. |
| `tm_resolve_training_cycle_targets` | Beregner mål for sæt/reps/vægt/RIR/RPE/deload. |

**Eksisterende testdækning:** `Tests/Unit/TrainingCycleFlowCoordinatorTests.swift` dækker flow states, deload presentation, end choice og authoring planner. `Tests/Unit/TrainingCycleDeloadPlannerTests.swift` dækker deload-forslag og runtime-deloadtekst.

**Auditvurdering:** Claimet er stærkt. Runtime er modelleret både i Swift og SQL, og server-RPC'er er den autoritative progression.

## 3. Watch Sync

**Problemkobling:** Træning foregår ofte væk fra telefonen. Watch reducerer friktion, men må stadig bruge samme session- og RLS-model.

**Swift/watch trace:**

| Fil | Rolle |
| --- | --- |
| `Traeningsmester/Core/Support/WatchAuthSyncPayload.swift` | Delt payload med schema version, Supabase URL, anon key, storage bucket, profile mode, exercise language preference, user/session tokens og completion state. |
| `Traeningsmester/Core/Support/WatchAppSyncBridge.swift` | iOS sender payload via `WCSession.updateApplicationContext` og fallback `transferUserInfo`; sync blokkerer ikke appens kerneflow. |
| `TraeningsmesterWatch/WatchAuthSyncBridge.swift` | watch modtager, gemmer og genindlæser payload lokalt. |
| `TraeningsmesterWatch/WatchWorkoutStore.swift` | Initialiserer repositories fra payload, forsøger session restore fra tokens og bruger samme repository/RLS-model som iOS. |
| `TraeningsmesterWatch/WatchRootView.swift` | Watch UI for dagens træning, logs og completion. |

**SQL/backend trace:** Watch får ikke service-role. Alle reads/writes går gennem Supabase anon key + brugerens bearer token, så RLS i `SUPABASE_MASTER_SETUP.sql` afgør adgang til workout, trackerlog, completion og cycle runtime.

**Eksisterende testdækning:** `Tests/Unit/WatchAuthSyncPayloadTests.swift` dækker payload roundtrip, versionafvisning, legacy felter og merge af completion state.

**Auditvurdering:** Claimet er stærkt for auth/session sync. Der mangler et dedikeret diagram, der viser iOS payload -> watch restore -> RLS read/write.

## 4. Live Activity

**Problemkobling:** Under træning skal feedback og set-completion kunne ske fra Lock Screen/Dynamic Island uden at åbne appen, men uden at skabe duplicate logs eller privilegeret klientadgang.

**Swift/extension trace:**

| Fil | Rolle |
| --- | --- |
| `Traeningsmester/Core/LiveActivity/TrackerLiveActivityModels.swift` | Activity attributes, content state og `TrackerLiveActivitySessionSnapshot` med Supabase/session/workout/rest/cycle target data. |
| `Traeningsmester/Core/LiveActivity/TrackerLiveActivitySharedStore.swift` | Gemmer session snapshot i App Group `group.com.traeningsmester.ios`. |
| `Traeningsmester/Core/LiveActivity/TrackerLiveActivityProjection.swift` | Beregner næste sæt, rest state, isometrisk timer og displaytekst. |
| `Traeningsmester/Core/LiveActivity/TrackerLiveActivityCenter.swift` | Starter/opdaterer/afslutter ActivityKit activity. |
| `Traeningsmester/Core/LiveActivity/TrackerLiveActivityIntents.swift` | Interaktive intents for reps/vægt/timer/complete/cancel. Skriver `trackerlog` med `client_action_id`. |
| `TraeningsmesterLiveActivities/TrackerLiveActivityWidget.swift` | Lock Screen/Dynamic Island UI. |

**SQL trace:**

| SQL objekt | Rolle |
| --- | --- |
| `trackerlog.client_action_id` | Idempotency key for intent-writes. |
| `uq_trackerlog_user_client_action` | Unikt indeks på `("userID", client_action_id)` når `client_action_id` ikke er null. |
| `tm_block_trackerlog_immutable_update` | Trigger blokerer ændring af immutable trackerlog-felter. |
| `workout_exercises_with_user_weight` | Live Activity henter workout exercise rows med brugerens vægtdata. |

**Eksisterende testdækning:** `Tests/Unit/TrackerLiveActivityProjectionTests.swift` dækker projection, rest timer, isometrisk completion og deep links. `Tests/Unit/TrackerLogPayloadEncodingTests.swift` dækker `client_action_id` encoding. `Tests/Unit/SupabaseDeduplicationHelpersTests.swift` dækker dedupe helpers.

**Auditvurdering:** Claimet er stærkt for idempotent trackerlog. Der bør genereres et sekvensdiagram for Live Activity intent -> App Group snapshot -> authenticated anon Supabase -> idempotent trackerlog.

## 5. Exercise Search/Catalog Governance

**Problemkobling:** Øvelsessøgning og katalogstyring skal være stabil på tværs af sprog, æ/ø/å, udstyr, træningsform og import. Ellers bliver brugerens programstruktur inkonsistent.

**Swift trace:**

| Fil | Rolle |
| --- | --- |
| `Traeningsmester/Core/Support/ExerciseFormCatalog.swift` | Central normalisering, equipment tokens, training form tokens, søgesynonymer, displaynavne og category collapse. |
| `Traeningsmester/Core/Data/SupabaseRepositories.swift` | Henter/deduplicerer øvelseskatalog og bruger typed payloads. |
| `Traeningsmester/Features/Exercises/ExercisesView.swift` | Bruger katalog- og filterlogik i øvelseslisten. |
| `Traeningsmester/Features/Match/MatchView.swift` | Bruger samme domænemodeller i swipe/match-flowet. |
| `Traeningsmester/Core/Support/ProgramReviewService.swift` | Import/AI resolver øvelser mod katalog via `ImportExerciseCatalogMatcher` og kan oprette private øvelser, når katalogmatch mangler. |

**SQL trace:**

| SQL objekt | Rolle |
| --- | --- |
| `tm_normalize_exercise_catalog_text` | Database-normalisering af tekst inkl. æ/ø/å og non-alphanumeric separators. |
| `exercises.training_form_raw`, `training_form_tokens`, `primary_muscle_group`, `secondary_muscle_group`, `tertiary_muscle_group`, `muscle_specialization_tokens` | Strukturerede katalogfelter. |
| `tm_exercise_catalog_canonical_key` | Canonical key for dedupe med EN-first semantics. |
| `tm_normalize_training_form_tokens` og `tm_normalize_equipment_tokens` | Governance for filterbare tokenfelter. |
| `exercise_catalog_v3_stage` og `tm_merge_exercise_catalog_v3_from_stage` | Service-role styret katalogimport/merge fra staging. |
| `tm_exercise_catalog_v3_healthcheck`, `tm_restore_exercise_catalog_v3_snapshot` | Driftssikring og rollbackspor for katalog. |

**Eksisterende testdækning:** `Tests/Unit/ExerciseFormCatalogTests.swift` dækker normalisering, synonymer, category collapse, equipment/training form tokens og CSV/katalogforventninger. `Tests/Unit/SupabaseDeduplicationHelpersTests.swift` dækker dedupe behavior.

**Auditvurdering:** Claimet er stærkt. Governance findes både client-side og SQL-side. Katalogets server-side import/merge bør omtales som et driftsspor, ikke som almindelig klientfunktion.

## 6. Admin/Trainer Boundary

**Problemkobling:** Fleksible samarbejdsflows må ikke åbne for cross-user adgang. Træner/klient og admin skal være servervaliderede boundaries, ikke kun UI-tilstande.

**Swift trace:**

| Fil | Rolle |
| --- | --- |
| `Traeningsmester/Core/Support/TrainerClientService.swift` | `TrainerClientEdgeFunctionRepository` og `AdminControlCenterEdgeFunctionRepository` kalder Edge Functions med anon key + bearer token. |
| `Traeningsmester/Features/Clients/ClientsView.swift` | Trænerens klientliste, detalje, plan assignment og klientaktivitet. |
| `Traeningsmester/Features/Settings/SettingsView.swift` | Trainer request inbox og admin-center UI. |
| `Traeningsmester/Core/Data/RepositoryProtocols.swift` | `AdminControlCenterRepository` typed contract for bruger-CRUD, activity feed og exercise submissions. |

**Edge Function trace:**

| Function | Rolle |
| --- | --- |
| `supabase/functions/trainer-client-manage/index.ts` | Validerer session, håndterer klientrelationer, friend-code linking, planlinks og klientdetaljer. Bruger relation-checks før klientdata returneres. |
| `supabase/functions/admin-control-center/index.ts` | Validerer session og kræver admin via `tm_current_user_is_admin`/`user_settings.is_admin` før bruger-CRUD, activity feed og exercise review. |

**SQL trace:**

| SQL objekt | Rolle |
| --- | --- |
| `user_settings.is_admin` | Serverlæst adminflag. |
| `tm_current_user_is_admin()` | SQL helper, security definer, returnerer adminstatus for `auth.uid()`. |
| `trainer_clients`, `trainer_client_plan_links` | Relation og planassignment mellem træner og klient. |
| `tm_list_trainer_clients` | User-scoped RPC til klientoverblik. |
| RLS policies på `trainer_clients`/planlinks | Relationel adgang i databasen. |
| `app_activity_events` | Auditspor for admin-/driftsbegivenheder. |

**Eksisterende testdækning:** `Tests/Unit/AdminControlCenterModelsTests.swift` dækker admin DTO decoding. `Tests/Unit/AdminActivityViewModelSupportTests.swift` dækker admin activity view-model support. `Tests/Unit/TrainerClientRepositoryPerformanceTests.swift` dækker Edge Function repository cache/performance-kontrakt.

**Auditvurdering:** Claimet er stærkt for servervalideret boundary. Den vigtigste rapportpointe er, at service-role kun findes inde i Edge Function runtime, mens klienten kun sender brugerens access token.

## 7. StoreKit/Premium

**Problemkobling:** Premiumfunktioner skal låses op uden at gøre klienten til autoritativ sikkerhedsgrænse for avancerede features som cycle runtime.

**Swift trace:**

| Fil | Rolle |
| --- | --- |
| `Traeningsmester/Core/Domain/Models.swift` | `TMSubscriptionTierID`, `TMSubscriptionTier`, `TMSubscriptionCatalog` og App Store produkt-id mapping. |
| `Traeningsmester/Core/Support/StoreKitSubscriptionService.swift` | StoreKit 2 purchase, transaction updates, restore og verification handling. |
| `Traeningsmester/Features/Premium/PremiumView.swift` | UI-flow for køb, gendannelse og persistering af tier efter verificeret StoreKit outcome. |
| `Traeningsmester/Core/Data/SupabaseRepositories.swift` | `updateSubscriptionTier` kalder RPC `tm_update_subscription_tier`. |
| `Traeningsmester/Core/Domain/Payloads.swift` | Subscription payload DTO'er til settings/RPC. |

**SQL/backend trace:**

| SQL objekt | Rolle |
| --- | --- |
| `user_settings.subscription_tier` | Persisted tier med constraint på `fitness_free`, `pro`, `trainer`, `buddy`. |
| `tm_update_subscription_tier(p_tier text)` | Security definer RPC, kræver `auth.uid()`, validerer tier og buddy eligibility. |
| `tm_current_user_has_cycle_premium()` | Server-side premium gate for cycle RPC'er. |
| `supabase/functions/billing-create-checkout-session/index.ts`, `supabase/functions/billing-confirm-checkout-session/index.ts` | Stripe/checkout-relaterede legacy/server helpers findes, men aktiv premium UI bruger StoreKit 2. |

**Eksisterende testdækning:** `Tests/Unit/SettingsPayloadTests.swift` dækker subscription tier payloads og `TMSubscriptionCatalog`.

**Auditvurdering:** Claimet er moderat-stærkt. StoreKit purchase/restore er implementeret i klienten, mens SQL stadig validerer tierform og premium gates. En egentlig App Store server notification-kæde ses ikke som primært spor i denne audit.

## 8. Import/AI Edge Functions

**Problemkobling:** Brugeren skal kunne tage eksisterende programmer/historik med ind i appen, så migration ikke starter med tom historik. AI og OCR må dog ikke køre direkte fra klienten med hemmelige nøgler.

**Swift trace:**

| Fil | Rolle |
| --- | --- |
| `Traeningsmester/Core/Support/ProgramReviewService.swift` | Edge Function repositories for program review, questionnaire, program import, history import og training import job orchestration. Indeholder også draft validation, catalog matching og appliers. |
| `Traeningsmester/Features/Premium/PremiumView.swift` | Programreview, planbuilder, programimport og historikimport UI; historikimport preview/apply. |
| `Traeningsmester/Features/Onboarding/TMOnboardingFlowView.swift` | Onboarding bruger program/historikimport og AI-planbygger som startvej. |
| `Traeningsmester/App/OnboardingModels.swift` | Onboarding step graph og state. |

**Edge Function trace:**

| Function | Rolle |
| --- | --- |
| `supabase/functions/program-review-analyze/index.ts` | OpenAI-baseret programanalyse og foreslået draft med JSON schema. |
| `supabase/functions/program-plan-questionnaire/index.ts` | AI-genereret spørgeskema/planinput. |
| `supabase/functions/program-import-normalize/index.ts` | Normaliserer gamle programkilder fra tekst/billeder. |
| `supabase/functions/history-import-normalize/index.ts` | OCR/AI-normalisering af gamle logs; bruger OpenAI Responses API med `store: false` og fallback på rå tekst. |
| `supabase/functions/training-import-manage/index.ts` | Orkestrerer importjobs: start/status/cancel/retry/apply_history, signed URLs, private øvelser og bulk insert i `trackerlog`. |
| `supabase/functions/training-import-manage/program_import_helper.ts` | Deterministisk katalogmatching og review response for programimport. |

**SQL trace:**

| SQL objekt | Rolle |
| --- | --- |
| `training_import_jobs` | Jobtabel med kind, status, progress, payload, result og expiry. |
| RLS på `training_import_jobs` | Bruger kan læse egne jobs; mutation styres service-role i function runtime. |
| `trackerlog` | Historikimport commit skriver valgte manual logs hertil via service client. |
| `exercises` | Import kan oprette private øvelser, når katalogmatch ikke findes. |
| Storage `workout_images` | Importbilleder signeres kun efter path ownership check. |

**Eksisterende testdækning:** `Tests/Unit/ProgramReviewServiceTests.swift` dækker draft validation, catalog matching og applierlogik. `supabase/functions/training-import-manage/program_import_helper_test.ts` findes for helperen, men `06_verifikation/verifikationsrapport.md` angiver, at Edge Function helper tests ikke blev kørt, fordi Deno manglede.

**Auditvurdering:** Claimet er stærkt for secret-isolering og joborchestration. Teststatus bør beskrives ærligt: Swift-side unit coverage findes; Deno helper-test var ikke kørt i den dokumenterede bachelor-run.

## Testspor Fundet I Repoet

Denne audit har ikke kørt tests. Følgende eksisterende testfiler understøtter claims:

| Claim | Testfiler |
| --- | --- |
| Tracker-off/completion/next-day | `Tests/Unit/AppStateNextDayPromptTests.swift`, `Tests/Unit/HomeSnapshotTests.swift` |
| Cycle runtime | `Tests/Unit/TrainingCycleFlowCoordinatorTests.swift`, `Tests/Unit/TrainingCycleDeloadPlannerTests.swift` |
| Watch sync | `Tests/Unit/WatchAuthSyncPayloadTests.swift` |
| Live Activity | `Tests/Unit/TrackerLiveActivityProjectionTests.swift`, `Tests/Unit/TrackerLogPayloadEncodingTests.swift`, `Tests/Unit/SupabaseDeduplicationHelpersTests.swift` |
| Exercise catalog/search | `Tests/Unit/ExerciseFormCatalogTests.swift`, `Tests/Unit/SupabaseDeduplicationHelpersTests.swift` |
| Admin/trainer | `Tests/Unit/AdminControlCenterModelsTests.swift`, `Tests/Unit/AdminActivityViewModelSupportTests.swift`, `Tests/Unit/TrainerClientRepositoryPerformanceTests.swift` |
| StoreKit/premium settings | `Tests/Unit/SettingsPayloadTests.swift` |
| Import/AI client logic | `Tests/Unit/ProgramReviewServiceTests.swift`, `supabase/functions/training-import-manage/program_import_helper_test.ts` |
| Supabase integration | `Tests/Integration/SupabaseIntegrationTests.swift` |

Bachelorens eksisterende verifikationsrapport kan bruges som teststatuskilde: `BachelorMateriale/2026-04-28-traeningsmester/06_verifikation/verifikationsrapport.md`.

## Diagramaudit

Eksisterende diagrammer dækker system context, ERD, container view, tracker BPMN, authorization DCR, tracker completion summary og security boundary summary.

Auditten finder tre manglende diagrammer, som bør genereres for at gøre bachelorpakken mere forklarende:

| Foreslået diagram | Type | Hvorfor |
| --- | --- | --- |
| `watch_sync_sequence.mmd` | Mermaid sequence | Viser iOS session snapshot, WCSession application context/userInfo, watch repository bootstrap, token restore og RLS-baseret dataadgang. |
| `live_activity_idempotency_sequence.mmd` | Mermaid sequence | Viser Live Activity intent, App Group snapshot, authenticated anon Supabase client, `client_action_id`, unique index og projection refresh. |
| `import_ai_edge_boundary.mmd` | Mermaid flow/sequence | Viser klient -> Edge Function -> OpenAI/storage/service-role -> preview/apply, så secret boundary og importjob-orchestration fremgår visuelt. |

Diagramkataloget er opdateret med disse forslag som "manglende/anbefalede diagrammer".

## Rapportkonklusion

TræningsMester realiserer problemformuleringens fleksibilitet gennem et tydeligt runtime- og datamodelskel: planlagt træning ligger i programtabellerne, faktisk træning i tracker/completion-tabellerne, og progression i AppState plus server-side runtime-RPC'er. Watch og Live Activity reducerer friktion i selve træningssituationen, mens RLS, typed repositories og Edge Functions holder adgangsgrænserne eksplicitte. De mest centrale claims har eksisterende testfiler, men denne audit har kun dokumenteret dækningen og ikke genkørt testene.
