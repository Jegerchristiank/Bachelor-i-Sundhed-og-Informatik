# Diagramkatalog

Dato: 2026-04-28

## Kilder

Diagramkilder ligger i `02_figurer_og_screenshots/diagrammer/kilder/`:

| Fil | Type | Formål |
| --- | --- | --- |
| `system_context.mmd` | Mermaid | Systemkontekst mellem bruger, app, Supabase og Apple services |
| `data_model_er.mmd` | Mermaid ERD | Centrale datamodeller og relationer |
| `container_architecture.puml` | PlantUML | Container-/komponentblik på iOS, watchOS, extensions og backend |
| `tracker_flow.bpmn` | BPMN XML | Tracker/completion-flow som procesmodel |
| `authorization_dcr.md` | DCR-style tekstmodel | Regler for auth, RLS, admin og cross-user adgang |
| `tracker_completion_summary.mmd` | Mermaid | Rapportnær opsummering af tracker-on/off, completion og cyklusprogression |
| `security_boundary_summary.mmd` | Mermaid | Rapportnær opsummering af anon client, RLS og Edge Function boundary |
| `watch_sync_sequence.mmd` | Mermaid sequence | iOS til watchOS auth/session sync og RLS-baseret dataadgang |
| `live_activity_idempotency_sequence.mmd` | Mermaid sequence | Live Activity intent-write med App Group snapshot og idempotent `trackerlog.client_action_id` |
| `import_ai_edge_boundary.mmd` | Mermaid flowchart | Import/AI boundary mellem klient, Edge Functions, OpenAI, storage og Supabase data |

## Rendering

Følgende diagrammer er renderet lokalt med Mermaid CLI via `npx @mermaid-js/mermaid-cli`:

| Kilde | Renderet fil | Status |
| --- | --- | --- |
| `system_context.mmd` | `02_figurer_og_screenshots/diagrammer/renderede_svg/system_context.svg` | Renderet 2026-04-28 |
| `data_model_er.mmd` | `02_figurer_og_screenshots/diagrammer/renderede_svg/data_model_er.svg` | Renderet 2026-04-28 |
| `tracker_completion_summary.mmd` | `02_figurer_og_screenshots/diagrammer/renderede_svg/tracker_completion_summary.svg` | Renderet 2026-04-28 |
| `security_boundary_summary.mmd` | `02_figurer_og_screenshots/diagrammer/renderede_svg/security_boundary_summary.svg` | Renderet 2026-04-28 |
| `watch_sync_sequence.mmd` | `02_figurer_og_screenshots/diagrammer/renderede_svg/watch_sync_sequence.svg` | Renderet 2026-04-28 |
| `live_activity_idempotency_sequence.mmd` | `02_figurer_og_screenshots/diagrammer/renderede_svg/live_activity_idempotency_sequence.svg` | Renderet 2026-04-28 |
| `import_ai_edge_boundary.mmd` | `02_figurer_og_screenshots/diagrammer/renderede_svg/import_ai_edge_boundary.svg` | Renderet 2026-04-28 |

PlantUML/BPMN/DCR-kilderne er stadig ikke renderet til billeder i denne pakke. De er gemt lokalt, så de kan renderes senere uden upload til online editors.

## Anbefalet Brug I Bacheloren

- Arkitekturafsnit: brug renderet system context og containerdiagram-kilden.
- Data-/sikkerhedsafsnit: brug renderet ERD og DCR-style authorization.
- Evaluering af træningsflow: brug BPMN for tracker/completion/cyklusprogression.

## Manglende Diagrammer Fundet Ved Deep Trace Audit

Følgende diagrammer bør genereres, hvis bachelorpakken skal have fuld visuel dækning af de dybe integrationsspor i `deep_code_sql_trace.md`:

| Foreslået kilde | Type | Formål | Status |
| --- | --- | --- | --- |
| `watch_sync_sequence.mmd` | Mermaid sequence | Vise iOS `WatchAppSyncBridge`, `WCSession`, watch payload-cache, repository bootstrap, token restore og RLS-baseret dataadgang | Kilde og SVG tilføjet |
| `live_activity_idempotency_sequence.mmd` | Mermaid sequence | Vise Live Activity intent, App Group snapshot, authenticated anon Supabase client, `client_action_id`, unik SQL-indeks og projection refresh | Kilde og SVG tilføjet |
| `import_ai_edge_boundary.mmd` | Mermaid flow/sequence | Vise klient, import/AI Edge Functions, OpenAI/storage/service-role boundary, job preview og apply til `trackerlog`/programstruktur | Kilde og SVG tilføjet |
