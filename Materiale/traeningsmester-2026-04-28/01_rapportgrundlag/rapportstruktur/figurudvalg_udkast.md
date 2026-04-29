# Endeligt Figurudvalg - Udkast

Dato: 2026-04-28  
Formål: foreslå et fokuseret figurudvalg til bacheloren, så hele screenshotmappen ikke skal afleveres ukritisk.

Note 2026-04-29: På eksplicit brugerønske er alle 13 aktuelle iOS 26.4-screenshots og de 7 renderede diagrammer indsat i rapportens `billedbilag.tex` med labels. Den anbefalede figurpakke her bør stadig bruges som prioritering for hovedteksten, så rapporten ikke bliver afhængig af alle bilagsfigurer.

## Anbefalet Figurpakke

| Figur | Kilde | Formål | Status |
| --- | --- | --- | --- |
| F1 | `02_figurer_og_screenshots/diagrammer/renderede_svg/system_context.svg` | Overordnet systemkontekst | Renderet |
| F2 | `02_figurer_og_screenshots/diagrammer/renderede_svg/data_model_er.svg` | Datamodel for plan/workout/tracker/completion/cyklus | Renderet |
| F3 | `02_figurer_og_screenshots/diagrammer/renderede_svg/tracker_completion_summary.svg` | Tracker-on/off og completion-flow | Renderet |
| F4 | `02_figurer_og_screenshots/diagrammer/renderede_svg/security_boundary_summary.svg` | Anon key, RLS og Edge Function boundary | Renderet |
| F5 | `02_figurer_og_screenshots/diagrammer/renderede_svg/watch_sync_sequence.svg` | iOS/watchOS auth-sync og RLS-baseret dataadgang | Renderet |
| F6 | `02_figurer_og_screenshots/diagrammer/renderede_svg/live_activity_idempotency_sequence.svg` | Live Activity write-flow og idempotent trackerlog | Renderet |
| F7 | `02_figurer_og_screenshots/diagrammer/renderede_svg/import_ai_edge_boundary.svg` | Import/AI boundary mellem klient, Edge Functions og OpenAI | Renderet |
| F8 | `02_figurer_og_screenshots/app_screenshots/aktuel_ios26/ios26-02-home-ready-testkonto-2026-04-28.jpg` | Aktuel Home-state og næste træningshandling | Kræver final visual review |
| F9 | `02_figurer_og_screenshots/app_screenshots/aktuel_ios26/ios26-10-tracker-active-testkonto-2026-04-28.jpg` | Tracker i aktiv session | Kræver final visual review |
| F10 | `02_figurer_og_screenshots/app_screenshots/aktuel_ios26/ios26-11-home-completion-delay-testkonto-2026-04-28.jpg` | Afslutning, undo-vindue og adherence progression | Kræver final visual review |
| F11 | `02_figurer_og_screenshots/app_screenshots/aktuel_ios26/ios26-03-programmer-testkonto-2026-04-28.jpg` | Programstruktur | Kræver final visual review |
| F12 | `02_figurer_og_screenshots/app_screenshots/aktuel_ios26/ios26-04-oevelser-testkonto-2026-04-28.jpg` | Øvelseskatalog og filterinteraktion | Kræver final visual review |
| F13 | `02_figurer_og_screenshots/app_screenshots/aktuel_ios26/ios26-06-indstillinger-testkonto-2026-04-28.jpg` | Settings/profiltilstande | Kræver final visual review; testkonto-email og telefon-placeholder skal omtales som fixturedata eller fravælges |
| F14 | `04_brugerindsigt_beta/testflight_tidslinje.md` | Iterativ beta-distribution | Tekstfigur/tabel |

## Fravalg

- Brug ikke hele screenshotmappen som direkte bilag uden kuratering.
- Brug ikke social/mail screenshots i public rapport uden redaktion.
- Historiske app-screenshots er fravalgt fra den kuraterede GitHub-pakke og bør ikke bruges som bevis for den aktuelle UI-version.
- Brug ikke watchOS/Live Activity som billedbevist runtimeflow, før screenshots er suppleret; brug build/test/arkitektur som evidens.
