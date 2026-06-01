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
| Approval matrix | De 13 aktuelle billeder er markeret `approved_for_report=true` og `approved_for_appendix` |

## Status Før Endelig Rapportbrug

- De 13 screenshots er visuelt gennemgået i afleveringsaudit.
- Billederne bruger testkonto-/fixturedata, ikke private rådata.
- Settings-billeder med fixturedata omtales som testkonto i billedbilaget.
- WatchOS, Live Activity, admin, onboarding og error/loading states er dokumenteret som kendte screenshot-gaps.
