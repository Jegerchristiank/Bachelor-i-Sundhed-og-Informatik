# Arkitektur- og Designrationale

Dato: 2026-04-28  
Scope: rationale for eksisterende Traeningsmester-repo baseret på faktiske filer og ansvar.

## Arkitektonisk stil

Systemet er en modulopdelt native iOS/watchOS klient med Supabase som backend. Klienten bruger SwiftUI views, global applikationsstate, typed domain models og repository-protokoller. Backendansvar ligger i Supabase Postgres, RLS, RPC, storage og Edge Functions.

Den praktiske lagdeling er:

1. Presentation: `Features/*`, `RootView`, watch views og widgets.
2. Application state: `AppState`, watch store og runtime state helpers.
3. Domain: `Models.swift`, `Payloads.swift`, `AppProfileMode.swift`.
4. Data access: `RepositoryProtocols.swift` og `SupabaseRepositories.swift`.
5. Platform/integration: StoreKit, WatchConnectivity, ActivityKit, WidgetKit, HealthKit og Supabase Edge Functions.
6. Database/security: `SUPABASE_MASTER_SETUP.sql` og migrations.

## Rationale for repository pattern

Repository-kontrakterne samler alle dataoperationer bag typed Swift-protokoller:

- `AuthRepository`
- `ExerciseRepository`
- `PlanRepository`
- `WorkoutRepository`
- `TrainingCycleRepository`
- `MatchRepository`
- `TrackerRepository`
- `HistoryRepository`
- `WorkoutCompletionRepository`
- `SettingsRepository`
- `FriendRepository`
- `DiagnosticsRepository`
- `AdminControlCenterRepository`
- `QuoteRepository`

Fordele:

- Views behøver ikke kende Supabase query-syntaks.
- Datakontrakter bliver testbare gennem protokoller og mocks.
- Supabase-specifik kode isoleres i `SupabaseRepositories.swift`.
- Domain payloads og DTO mapping kan unit-testes uden UI.
- Profiltilstand (`personal`/`trainer`) kan håndteres konsekvent på repository-niveau.

Tradeoff:

- Repository-filen er stor, fordi mange Supabase-queries og featureområder samles samme sted. Det giver lavere kompleksitet i views, men kræver disciplin i vedligeholdelse og tests.

## Rationale for central AppState

`AppState` er systemets centrale orchestration point for:

- bootstrap og miljøloading
- auth-session
- selected tab og navigation path
- aktiv plan og dagsstatus
- tracker runtime
- profiltilstand
- StoreKit/subscription tier
- adminstatus
- onboarding state
- træningscyklus runtime
- app alerts og password recovery

Fordele:

- Root navigation og globale flows kan styres ét sted.
- Feature views får adgang til samme session- og profilkontekst.
- Watch/session sync og Live Activity state kan kobles på samme autoritative brugerstate.

Tradeoff:

- `AppState` har bredt ansvar. Risikoen håndteres delvist med support services (`WorkoutCompletionService`, `ProgramReviewService`, `TrainerClientService`) og typed repositories.

## Rationale for Supabase/RLS som sikkerhedsgrænse

Repoet behandler RLS som primær sikkerhedsgrænse. Klienten må kun bruge anon key. `AppEnvironment` afviser service-role tokens ved startup via JWT role decoding.

Valget betyder:

- Klienten kan distribueres uden privilegerede nøgler.
- Cross-user adgang håndhæves tæt på data.
- Server-side flows kan bruge Edge Functions, hvor privilegier holdes i runtime og ikke i app binary.
- Adminadgang valideres server-side gennem `user_settings.is_admin` og admin-guard functions.

Tradeoff:

- RLS- og RPC-politikker skal holdes i sync med appens featureflows.
- Integration tests og SQL-dokumentation er kritiske for regressioner.

## Rationale for Edge Functions

Edge Functions bruges til operationer, der enten kræver server-side autorisation, service-role adgang, ekstern API-adgang eller orchestration:

- `admin-control-center`
- `trainer-client-manage`
- `program-review-analyze`
- `program-plan-questionnaire`
- `program-import-normalize`
- `history-import-normalize`
- `training-import-manage`
- billing-relaterede checkout functions

Fordele:

- OpenAI/service-role flows sker ikke direkte fra klienten.
- Importjobs kan normaliseres og persisteres kontrolleret.
- Admin- og trænerflows kan audit-logges og server-valideres.

## Rationale for native SwiftUI designsystem

Designsystemet ligger i `Traeningsmester/DesignSystem`:

- `TMTheme.swift`: farver, typografi og spacing tokens.
- `TMComponents.swift`: genbrugelige skærmcontainere, cards, knapper, logo, status og close bar.
- `TMMotionPrimitives.swift`: motion primitives.

`design.md` er den autoritative UI/UX-kontrakt. Det understøtter parity med FlutterFlow på funktionsniveau uden at kopiere UI én til én.

Fordele:

- Konsistent modal-, sheet- og close-bar-adfærd.
- Mindre duplikering i feature views.
- Bedre mulighed for native iOS ergonomi.

## Rationale for profile mode

`AppProfileMode` adskiller personlig brugeradgang fra trænerkontekst. Flere repositories accepterer `profileMode`, og centrale tabeller har `profile_mode`.

Formålet er at undgå implicit datadeling og gøre tværbrugeradgang eksplicit. Det er vigtigt, fordi systemet både understøtter personlige programmer, træner-klient relationer, programdeling og adminperspektiv.

## Rationale for watchOS og Live Activity

Watch appen har eget entrypoint og `WatchWorkoutStore`, men genbruger domain models, repositories og session payloads. iOS sender auth snapshot via WatchConnectivity, og watch appen forsøger lokal session før token-restore.

Live Activity bruger separat extension og shared store:

- `TrackerLiveActivityCenter`
- `TrackerLiveActivitySharedStore`
- `TrackerLiveActivityIntents`
- `TrackerLiveActivityProjection`
- `TraeningsmesterLiveActivities/TrackerLiveActivityWidget.swift`

Rationalet er at gøre træning og pausetimer tilgængelig uden at åbne hovedappen, mens writes stadig sker med authenticated anon-session og RLS.

## Rationale for træningscyklus-runtime

Træningscyklus er modellering af makro/meso/deload med runtime state. Runtime prioriteres over klassisk `plan.current_index`, når aktiv cyklus findes.

Fordele:

- Avanceret progression kan styres uden at omskrive planstrukturen.
- iOS og watch kan dele samme resolution via repository/RPC.
- Progression efter workout kan ske atomisk via backend RPC.

## Kvalitet og testbarhed

Teststrukturen viser fokus på:

- domain- og payload-encoding
- JWT role decoding og config-sikkerhed
- plan progress og onboarding step graph
- tracker log encoding og Live Activity projection
- watch auth payload
- admin/support models
- performance baseline for tunge paths

Der blev efterfølgende kørt build/test-verifikation som del af samme bachelor-run. Se `06_verifikation/verifikationsrapport.md` og `01_rapportgrundlag/rapportstruktur/test_status.md` for fulde resultater.

Kort status:

- iOS Debug build: bestået.
- Unit tests: 556 tests, 0 failures.
- Integration tests: 5 tests, 0 failures, 4 skipped pga. manglende Supabase test credentials.
- watchOS build: bestået.
- Live Activity build: bestået.
- Edge Function helper tests: ikke kørt, fordi Deno manglede.
