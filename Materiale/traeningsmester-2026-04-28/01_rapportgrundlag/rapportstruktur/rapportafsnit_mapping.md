# Rapportafsnit Mapping

Dato: 2026-04-28  
Formål: hurtig mapping fra bachelorens sandsynlige kapitler til konkrete bilag i denne materialepakke.

## Kapitelmapping

| Rapportafsnit | Primære bilag | Brug |
| --- | --- | --- |
| Problemfelt og motivation | `01_rapportgrundlag/problemformulering/problemformulering_resume.md`, `04_brugerindsigt_beta/messenger_dybdeanalyse.md` | Motiverer behovet for fleksibel træningsadherence, motivation og realistiske afvigelser fra plan. |
| Teoretisk/faglig ramme | `03_kursus_og_metode/kursusmapping.md`, `03_kursus_og_metode/kursusmapping.md`, `01_rapportgrundlag/problemformulering/problemformulering_autoritativ.md` | Binder projektet til softwareudvikling, projektledelse, interaktionsdesign, metode og sundhedsdata/interoperabilitet. |
| Metode | `04_brugerindsigt_beta/indsamlingsprotokol.md`, `04_brugerindsigt_beta/indsamlingsprotokol.md`, `04_brugerindsigt_beta/kildejournal.md`, `04_brugerindsigt_beta/mail_og_webmail_evidens.md` | Dokumenterer dataindsamling, beta-feedback, afgrænsning, mail/webmail-scope og anonymisering. |
| Krav og use cases | `05_arkitektur_data_sikkerhed/arkitektur/use_cases.md`, `05_arkitektur_data_sikkerhed/arkitektur/krav_traceability.md` | Oversætter problemformulering til funktionelle krav og sporbarhed. |
| Systemarkitektur | `05_arkitektur_data_sikkerhed/arkitektur/systembeskrivelse.md`, `02_figurer_og_screenshots/diagrammer/diagramkatalog.md` | Beskriver SwiftUI/Supabase/watch/Live Activity/Edge Function-arkitektur. |
| Interaktionsdesign | `05_arkitektur_data_sikkerhed/arkitektur/designrationale.md`, `02_figurer_og_screenshots/app_screenshots/screenshot_daekning.md`, `01_rapportgrundlag/rapportstruktur/billedtekster.md` | Viser valg om home, tracker, profiltilstande, sheets, accessibility og feedback loops. |
| Data og interoperabilitet | `05_arkitektur_data_sikkerhed/data_og_sikkerhed/dataflow.md`, `02_figurer_og_screenshots/diagrammer/renderede_svg/data_model_er.svg`, `05_arkitektur_data_sikkerhed/data_og_sikkerhed/rls_matrix.md` | Forklarer datamodellen, Supabase/RLS, DCR/BPMN-spor og platformintegrationer. |
| Sikkerhed og privacy | `05_arkitektur_data_sikkerhed/data_og_sikkerhed/sikkerhedsnotat.md`, `05_arkitektur_data_sikkerhed/data_og_sikkerhed/data_og_sikkerhed_rapportklar.md`, `06_verifikation/pii_redaction_audit.md` | Dokumenterer anon key, RLS, Edge Functions, redaktion og rest-risici. |
| Implementering | `05_arkitektur_data_sikkerhed/arkitektur/systembeskrivelse.md`, `05_arkitektur_data_sikkerhed/arkitektur/arkitekturfortaelling.md`, `05_arkitektur_data_sikkerhed/data_og_sikkerhed/edge_functions_overblik.md`, `05_arkitektur_data_sikkerhed/arkitektur/beslutningslog.md` | Forklarer de tekniske valg og tradeoffs, der understøtter appens features. |
| Test og verifikation | `06_verifikation/verifikationsrapport.md`, `06_verifikation/verifikationsrapport.md`, `06_verifikation/automation_capture_limitations.md` | Underbygger build/test-resultater, XcodeGen drift og kendte skips. |
| Evaluering og brugerindsigt | `04_brugerindsigt_beta/beta_tester_rapport.md`, `04_brugerindsigt_beta/messenger_dybdeanalyse.md`, `04_brugerindsigt_beta/feedbackkatalog.md`, `04_brugerindsigt_beta/beta_observationsmatrix.csv`, `04_brugerindsigt_beta/testflight_tidslinje.md` | Samler beta-feedback, rekruttering, Messenger-temaer og TestFlight-iterationer. |
| Diskussion | `01_rapportgrundlag/rapportstruktur/rapportklar_gap_lukning.md`, `06_verifikation/quality_gate_review.md` | Bruges til ærlig vurdering af styrker, svagheder og manglende evidens. |

## Særligt Stærke Argumenter

- Appen angriber frafald og demotivation ved at gøre afvigelser fra planen til en håndteret del af systemet, ikke en fejltilstand.
- Tracker-off completion, workout completion events og cyklusprogression adskiller træningsadherence fra perfekt sætlogning.
- Supabase RLS og Edge Functions gør privacy/sikkerhed til en arkitekturbeslutning fremfor kun UI-disciplin.
- Watch og Live Activity reducerer friktion under træning, hvor telefoninteraktion ofte er uhensigtsmæssig.

## Kendte Gap-Formuleringer Til Rapporten

- "Materialet dokumenterer watchOS og Live Activity gennem build, kode og tests, men runtime screenshots bør suppleres i en senere bilagsrunde."
- "Beta-indsigter er anonymiserede og tematisk kodet; rå screenshots er bevidst ikke lagt i repoet af privatlivshensyn."
- "Integrationstestene viser, at testharness virker, men fuld cross-user/admin-verifikation kræver dedikerede Supabase test credentials."
