# RLS- Og Sikkerhedsmatrix

Kilde: `SUPABASE_MASTER_SETUP.sql`, repository-lag og integrationstest pr. 2026-04-28.

| Område | Primær sikkerhedsgrænse | Klientbeskyttelse | Server/SQL-beskyttelse | Test/evidens |
| --- | --- | --- | --- | --- |
| Auth/session | Supabase Auth + anon key | `AppEnvironment` afviser placeholders/service-role | Auth JWT og `auth.uid()` | Integration auth-tests skipped uden credentials; anon read passede |
| Egne programmer | RLS på `plan`, `workout`, `plan_workouts`, `workout_exercises` | Repositories kræver session og typed payloads | Owner policies og helper functions | Unit payload/progress tests |
| Delte programmer | RLS + share views | UI viser kun accessible resources | `tm_user_can_read_plan`, `tm_user_can_edit_plan` | SQL review |
| Trackerlog | RLS + immutable field trigger | `WorkoutTrackerView`/repositories sender brugerbundne writes | `tm_block_trackerlog_immutable_update`, unique `client_action_id` | `TrackerLogPayloadEncodingTests`, integration anon read |
| Completion events | RLS + idempotency | `WorkoutCompletionService` centraliserer writes | unique `(user_id, client_action_id)`, `reverted_at` | `HomeSnapshotTests`, AppState tests |
| Active session | RLS + forced RLS | App state og Live Activity snapshot | unique user/profile session, profile_mode constraint | Live Activity projection tests |
| Watch sync | App Group/local cache + anon session | Watch token payload model | RLS for all backend reads/writes | `WatchAuthSyncPayloadTests`, watch build |
| Live Activity intents | App Group snapshot + anon Supabase client | `TrackerLiveActivitySharedStore` | RLS + idempotent writes | Live Activity build, projection tests |
| Admin | Edge Function + SQL guard | UI only exposes admin flow after server-backed state | `tm_current_user_is_admin`, `tm_require_admin`, service-role only in function runtime | Admin unit tests; integration admin tests skipped without credentials |
| Trainer/client | Edge Function/RLS | `TrainerClientService` | `trainer-client-manage`, related-user policies | Unit/performance support tests |
| AI/import | Edge Functions | Client never calls OpenAI directly | Function runtime controls service role/OpenAI | Deno tests not run; Deno missing |

## Hovedkonklusion

Den afgørende sikkerhedsbeslutning er at holde appen på anon/publishable credentials og flytte privilegerede flows til SQL/RPC/Edge Functions. Klientguards bruges til UX og tidlig fejl, men må ikke være den eneste adgangskontrol.

