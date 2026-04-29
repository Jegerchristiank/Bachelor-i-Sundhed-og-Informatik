# Navigator

Dette er navigationsfilen for den kuraterede Træningsmester-materialemappe. Brug den som første stop, når materialet skal indarbejdes i bacheloren eller vedligeholdes i Overleaf/GitHub-repoet.

## Kort Formål

Mappen indeholder rapportnært bachelormateriale for Træningsmester pr. 2026-04-28:

- problemformulering og rapportstruktur,
- aktuelle app-screenshots fra iOS 26.4,
- diagrammer og diagramkilder,
- kursus- og metodekobling fra Absalon,
- anonymiseret beta- og brugerindsigt,
- arkitektur, data og sikkerhed,
- verifikations- og quality-gate summaries.

Rå Messenger-, Facebook-, Gmail-, KU webmail-, Absalon- og Xcode-logdata er bevidst ikke inkluderet i denne kuraterede GitHub-pakke.

## Læserute

Start med disse filer i rækkefølge:

1. `README.md`
2. `01_rapportgrundlag/problemformulering/problemformulering_autoritativ.md`
3. `01_rapportgrundlag/rapportstruktur/rapportafsnit_mapping.md`
4. `01_rapportgrundlag/rapportstruktur/figurudvalg_udkast.md`
5. `06_verifikation/quality_gate_review.md`
6. `06_verifikation/final_publication_checklist.md`

## Mappeansvar

| Mappe | Ansvar | Primær brug |
| --- | --- | --- |
| `01_rapportgrundlag/` | Problemformulering, rapportstruktur, figurvalg og teststatus | Startpunkt for selve bachelorteksten |
| `02_figurer_og_screenshots/` | Aktuelle screenshots, diagrammer, renderede SVG'er og diagramkilder | Figurer og tekniske bilag |
| `03_kursus_og_metode/` | Absalon-kursusmapping, download-audit og filindeks | Faglig/metodisk forankring |
| `04_brugerindsigt_beta/` | Beta-tester rapport, feedbackkatalog, Messenger/Facebook/mail/TestFlight-evidens | Evaluering og brugerindsigt |
| `05_arkitektur_data_sikkerhed/` | Systembeskrivelse, use cases, krav, SQL/RLS, Edge Functions og sikkerhedsnotater | Implementering, arkitektur og data |
| `06_verifikation/` | Testsummary, screenshot-QA, PII-audit, quality gate og publiceringscheck | Verifikation og begrænsninger |

## Kritiske Filer

| Fil | Hvorfor den er vigtig |
| --- | --- |
| `README.md` | Kort læsevejledning og oversigt over bevidst fravalgte støjfiler |
| `01_rapportgrundlag/problemformulering/problemformulering_autoritativ.md` | Autoritativ problemformulering og underspørgsmål |
| `01_rapportgrundlag/rapportstruktur/rapportafsnit_mapping.md` | Kobler rapportafsnit til konkrete kilder i materialemappen |
| `01_rapportgrundlag/rapportstruktur/figurudvalg_udkast.md` | Foreslår de figurer, der bør bruges i rapporten |
| `02_figurer_og_screenshots/app_screenshots/screenshot_daekning.md` | Forklarer hvad de 13 aktuelle iOS 26.4 screenshots dækker og ikke dækker |
| `02_figurer_og_screenshots/app_screenshots/manifester/screenshot_approval_matrix.csv` | Registrerer screenshot-godkendelse; de 13 aktuelle iOS 26.4 screenshots er godkendt til bilagsbrug pr. 2026-04-29 |
| `02_figurer_og_screenshots/diagrammer/diagramkatalog.md` | Oversigt over diagramkilder og renderede diagrammer |
| `03_kursus_og_metode/kursusmapping.md` | Kobler Absalon-fagstof til bachelorens metode, design, arkitektur og dataafsnit |
| `04_brugerindsigt_beta/feedbackkatalog.md` | Tematisk katalog over brugerfeedback |
| `04_brugerindsigt_beta/traeningscenter_korrespondance.md` | Anonymiseret opsummering af center-outreach og videooptagelsesrationale |
| `05_arkitektur_data_sikkerhed/arkitektur/systembeskrivelse.md` | Teknisk systembeskrivelse af app, watchOS, Live Activity, Supabase og Edge Functions |
| `05_arkitektur_data_sikkerhed/data_og_sikkerhed/data_og_sikkerhed_rapportklar.md` | Rapportklar fortælling om data, RLS, privacy og sikkerhedsgrænser |
| `06_verifikation/verifikationsrapport.md` | Kort build/test-summary uden rå logs |
| `06_verifikation/quality_gate_review.md` | Ærlig vurdering af styrker og resterende gaps |

## Repo Tree

```text
Materiale/traeningsmester-2026-04-28
├── README.md
├── NAVIGATOR.md
├── 01_rapportgrundlag
│   ├── problemformulering
│   │   ├── problemformulering_autoritativ.md
│   │   ├── problemformulering_redigeret.pdf
│   │   └── problemformulering_resume.md
│   └── rapportstruktur
│       ├── billedtekster.md
│       ├── figurudvalg_udkast.md
│       ├── rapportafsnit_mapping.md
│       ├── rapportklar_gap_lukning.md
│       └── test_status.md
├── 02_figurer_og_screenshots
│   ├── app_screenshots
│   │   ├── aktuel_ios26
│   │   │   └── 13 aktuelle iOS 26.4 screenshots
│   │   ├── manifester
│   │   │   ├── screenshot_approval_matrix.csv
│   │   │   ├── screenshot_manifest.csv
│   │   │   └── screenshot_manifest.json
│   │   ├── screenshot_daekning.md
│   │   └── screenshot_kontaktark.md
│   └── diagrammer
│       ├── diagramkatalog.md
│       ├── figurindeks.md
│       ├── kilder
│       │   └── Mermaid, PlantUML, BPMN og DCR-kilder
│       └── renderede_svg
│           └── 7 renderede SVG-diagrammer
├── 03_kursus_og_metode
│   ├── absalon_download_audit.md
│   ├── absalon_filindeks.md
│   ├── kursusmapping.md
│   └── kursusmateriale_audit.md
├── 04_brugerindsigt_beta
│   ├── beta_observationsmatrix.csv
│   ├── beta_tester_rapport.md
│   ├── facebook_rekruttering_audit.md
│   ├── feedbackkatalog.md
│   ├── indsamlingsprotokol.md
│   ├── kildejournal.md
│   ├── mail_og_webmail_evidens.md
│   ├── messenger_dybdeanalyse.md
│   ├── private_messenger_followup_audit.md
│   ├── traeningscenter_korrespondance.md
│   └── testflight_tidslinje.md
├── 05_arkitektur_data_sikkerhed
│   ├── arkitektur
│   │   ├── arkitekturfortaelling.md
│   │   ├── beslutningslog.md
│   │   ├── deep_code_sql_trace.md
│   │   ├── designrationale.md
│   │   ├── krav_traceability.md
│   │   ├── systembeskrivelse.md
│   │   └── use_cases.md
│   └── data_og_sikkerhed
│       ├── data_og_sikkerhed_rapportklar.md
│       ├── dataflow.md
│       ├── edge_functions_overblik.md
│       ├── interoperabilitet_dcr_bpmn_notat.md
│       ├── rls_matrix.md
│       ├── sikkerhedsnotat.md
│       ├── sql_inventory_report.md
│       └── sql_schema_overblik.md
└── 06_verifikation
    ├── automation_capture_limitations.md
    ├── final_publication_checklist.md
    ├── pii_redaction_audit.md
    ├── quality_gate_review.md
    ├── screenshot_qa.md
    ├── test_traceability_matrix.md
    └── verifikationsrapport.md
```

## Vedligeholdelsesregler

- Opdater denne fil, hvis mapper eller centrale filer flyttes, tilføjes eller fjernes.
- Hold `README.md` som kort læsevejledning og denne fil som detaljeret strukturkort.
- Behold rådata udenfor GitHub-pakken, medmindre der senere laves særskilt redaktion og samtykkevurdering.
- Brug kun screenshots efter manuel visuel godkendelse i `screenshot_approval_matrix.csv`.
- Nedton sikkerheds- og evalueringclaims, hvor `06_verifikation/quality_gate_review.md` markerer åbne gaps.
