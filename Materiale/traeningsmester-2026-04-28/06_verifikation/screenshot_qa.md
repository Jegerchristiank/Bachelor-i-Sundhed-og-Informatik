# Screenshot-QA

Dato: 2026-04-28

## Manifest

- CSV: `02_figurer_og_screenshots/app_screenshots/manifester/screenshot_manifest.csv`
- JSON: `02_figurer_og_screenshots/app_screenshots/manifester/screenshot_manifest.json`
- Approval matrix: `02_figurer_og_screenshots/app_screenshots/manifester/screenshot_approval_matrix.csv`
- Kontaktark: `02_figurer_og_screenshots/app_screenshots/screenshot_kontaktark.md`
- Feature coverage: `02_figurer_og_screenshots/app_screenshots/screenshot_daekning.md`

## Status

| Kontrol | Resultat |
| --- | --- |
| Public app screenshots fundet | 13 aktuelle iOS 26.4 screenshots |
| Hver fil har manifest-række | Ja |
| Dimensioner/filstørrelse registreret | Ja |
| Xcode MCP screenshot inkluderet | Ja, `TM-iPhone-16-Pro-iOS26` |
| Historiske screenshots | Fravalgt fra den kuraterede GitHub-pakke |
| Messenger/Facebook/mail raw screenshots i public folder | Nej |
| Approval matrix | Alle billeder markeret `needs_final_visual_review` |

## Mangler Før Endelig Rapportbrug

- Gennemgå de 13 screenshots visuelt en sidste gang.
- Udfyld `approved_for_report`, reviewer og anonymiseringshandling for de billeder, der faktisk bruges i rapporten.
- Settings-billeder med fixturedata bør enten fravælges eller omtales tydeligt som testkonto-/placeholderdata.
- WatchOS, Live Activity, admin, onboarding og error/loading states er dokumenteret som kendte screenshot-gaps.
