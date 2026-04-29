# Traeningsmester Bachelormateriale

Dato: 2026-04-28  
Formål: kurateret materiale til bachelorrapporten. Denne mappe er ryddet op, så den kun indeholder rapportnære filer, aktuelle screenshots, diagrammer, brugerindsigt, arkitektur/data/sikkerhed og verifikationssummaries.

## Start Her

Læs disse filer først:

1. `01_rapportgrundlag/problemformulering/problemformulering_autoritativ.md`
2. `01_rapportgrundlag/rapportstruktur/rapportafsnit_mapping.md`
3. `01_rapportgrundlag/rapportstruktur/figurudvalg_udkast.md`
4. `06_verifikation/quality_gate_review.md`
5. `06_verifikation/final_publication_checklist.md`

Brug `NAVIGATOR.md` som detaljeret strukturkort, hvis du skal finde rundt i mapperne eller forklare materialets opbygning til en vejleder/censor.

## Mapper

| Mappe | Brug | Skal med i rapportarbejdet? |
| --- | --- | --- |
| `01_rapportgrundlag/` | Problemformulering, rapportstruktur, figurudvalg, billedtekster og teststatus | Ja, primær |
| `02_figurer_og_screenshots/` | Aktuelle iOS 26.4 screenshots og renderede diagrammer | Ja, figurer/bilag |
| `03_kursus_og_metode/` | Absalon-mapping, download-audit og filindeks | Ja, metode/faglig forankring |
| `04_brugerindsigt_beta/` | Beta-tester rapport, feedbackkatalog, Messenger/Facebook/mail/TestFlight-evidens | Ja, evaluering/metode |
| `05_arkitektur_data_sikkerhed/` | Systembeskrivelse, use cases, krav, SQL, RLS, Edge Functions og sikkerhed | Ja, implementering |
| `06_verifikation/` | Build/test-summaries, screenshot-QA, PII-audit og quality gate | Ja, evaluering og begrænsninger |

## Mest Relevante Filer At Inkludere

| Rapportafsnit | Brug disse filer |
| --- | --- |
| Problem og afgrænsning | `01_rapportgrundlag/problemformulering/problemformulering_autoritativ.md`, `problemformulering_resume.md`, `problemformulering_redigeret.pdf` |
| Rapportstruktur | `01_rapportgrundlag/rapportstruktur/rapportafsnit_mapping.md`, `figurudvalg_udkast.md`, `billedtekster.md` |
| Appens UI | `02_figurer_og_screenshots/app_screenshots/aktuel_ios26/`, `screenshot_daekning.md`, `screenshot_kontaktark.md` |
| Diagrammer | `02_figurer_og_screenshots/diagrammer/renderede_svg/`, `diagramkatalog.md`, `figurindeks.md` |
| Kursus- og metodekobling | `03_kursus_og_metode/kursusmapping.md`, `absalon_download_audit.md`, `absalon_filindeks.md` |
| Beta/evaluering | `04_brugerindsigt_beta/beta_tester_rapport.md`, `feedbackkatalog.md`, `beta_observationsmatrix.csv`, `messenger_dybdeanalyse.md`, `traeningscenter_korrespondance.md`, `testflight_tidslinje.md` |
| Arkitektur og design | `05_arkitektur_data_sikkerhed/arkitektur/systembeskrivelse.md`, `use_cases.md`, `krav_traceability.md`, `beslutningslog.md`, `arkitekturfortaelling.md` |
| Data og sikkerhed | `05_arkitektur_data_sikkerhed/data_og_sikkerhed/data_og_sikkerhed_rapportklar.md`, `sikkerhedsnotat.md`, `rls_matrix.md`, `sql_schema_overblik.md`, `edge_functions_overblik.md` |
| Test/verifikation | `06_verifikation/verifikationsrapport.md`, `test_traceability_matrix.md`, `screenshot_qa.md`, `quality_gate_review.md` |

## Bevidst Fravalgt Fra GitHub-Pakken

Følgende er ikke længere i den kuraterede pakke, fordi det primært var støj eller arbejdsbevis:

- rå Xcode buildlogs,
- tool-version dumps og `git status` snapshots,
- gamle/skabelonbaserede indeksfiler,
- historiske screenshots fra ældre appversioner,
- gamle iOS 18.5 sanity captures,
- store rå Absalon-filer,
- rå Messenger/Facebook/Gmail/KU webmail screenshots.

Det betyder ikke, at de aldrig fandtes. De er bare ikke egnede som direkte bachelorbilag. Rapporten bør bruge de kuraterede summaries og kun hente råmateriale frem privat, hvis en specifik påstand skal efterkontrolleres.

## Caveats

- De 13 iOS screenshots er registreret som godkendt til bilagsbrug i `02_figurer_og_screenshots/app_screenshots/manifester/screenshot_approval_matrix.csv` pr. 2026-04-29 efter eksplicit brugerønske; en afsluttende forfattergennemgang før aflevering anbefales stadig.
- watchOS, Live Activity, admin, onboarding og fejlstates er dokumenteret via kode/test/arkitektur, men ikke med runtime screenshots i denne mappe.
- Integrationstest med fulde Supabase credentials og Edge Function helper tests er dokumenteret som rest-gaps.
