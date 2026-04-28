# SQL-Schemaoverblik

Kilde: `SUPABASE_MASTER_SETUP.sql` og repoets typed Swift-modeller pr. 2026-04-28.

## Centrale Tabeller

| Domæne | Tabeller | Formål |
| --- | --- | --- |
| Øvelseskatalog | `exercises`, `workout_exercise_user_weights` | Officielle/private øvelser, søgning, medier og bruger-specifik vægt |
| Programmer | `plan`, `workout`, `plan_workouts`, `workout_exercises` | Programstruktur, træningsdage og øvelsesrækker |
| Deling/social | `plan_share_codes`, `plan_shared_users`, `plan_share_invites`, `user_friend_codes`, `friend_requests`, `friendships`, `friend_aliases` | Programdeling, invites og venne-/buddy-relationer |
| Træner/klient | `trainer_clients`, `trainer_client_plan_links` | Klientrelationer og planadgang |
| Match | `match`, `liked_parred`/views | Like-/swipe-state for øvelser |
| Tracker/historik | `trackerlog`, `workout_completion_events`, `active_workout_session_state` | Sætlogs, completion uden trackerlog og aktiv session |
| Settings/admin | `user_settings`, `app_activity_events`, `app_feedback`, `app_version_history`, `app_error_reports` | Profiltilstand, subscription, admin, feedback og diagnostics |
| Cykler/import | `training_cycles`, `training_cycle_*`, `training_import_jobs` | Makro/meso/deload, runtime progression og importjobs |

## Særligt Rapportrelevante Felter

| Felt | Hvor | Hvorfor det er vigtigt |
| --- | --- | --- |
| `profile_mode` | `user_settings`, completion/session/cycle flows | Skelner personlig bruger fra træner-/klientkontekst |
| `client_action_id` | `trackerlog`, `workout_completion_events` | Idempotency for Live Activity/watch/tracker writes |
| `reverted_at` | `workout_completion_events` | Gør det muligt at fortryde completion uden at slette historik |
| `superset_group_id`, `superset_position` | `workout_exercises` | Understøtter superset-struktur i tracker og watch |
| `is_rest_override` | `workout_exercises` | Skelner standardpause fra bevidst override |
| `subscription_tier` | `user_settings` | Binder StoreKit 2 køb til appens featureadgang |
| `is_admin` | `user_settings` | Server-valideret adminadgang, ikke kun lokal UI-state |

## Views Og RPC

Vigtige views/RPC'er i master-setup:

- `accessible_plans_view`, `accessible_workouts_view`, `combined_workout_plan_view`
- `workout_exercises_with_user_weight`, `matched_exercises`, `liked_exercises_view`
- `training_cycle_runtime_states_view`, `training_days_with_exercises`
- `get_liked_exercises`, `tm_delete_workouts_batch`
- `tm_resolve_active_training_cycle_day`, `tm_progress_training_cycle_after_workout`
- `tm_handle_training_cycle_end_action`, `tm_resolve_training_cycle_targets`
- `tm_current_user_is_admin`, `tm_require_admin`

## Rapportvinkel

Datamodellen er ikke kun CRUD. Den afspejler bachelorens centrale problem: hvordan en app kan håndtere afvigelser fra plan uden at gøre brugeren forkert. Det ses især i adskillelsen mellem planstruktur, faktisk trackerlog, completion-events, cyklus-runtime og historik.

