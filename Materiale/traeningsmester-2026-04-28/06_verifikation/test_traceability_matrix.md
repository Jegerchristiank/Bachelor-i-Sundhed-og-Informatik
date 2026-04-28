# Test Traceability Matrix

Dato: 2026-04-28

| Påstand i rapporten | Evidens i pakken | Status | Begrænsning |
| --- | --- | --- | --- |
| Appen kan bygges som iOS-klient | `06_verifikation/verifikationsrapport.md` | Bestået | Dirty worktree, ikke clean checkout proof. |
| Central forretningslogik er unit-testet | `01_rapportgrundlag/rapportstruktur/test_status.md` | Bestået | Dækker unit-lag, ikke alle live backendscenarier. |
| Supabase anon read path fungerer | `06_verifikation/verifikationsrapport.md` | Delvist bestået | Admin/non-admin credential-tests var skipped. |
| watchOS targetet kan bygges | `06_verifikation/verifikationsrapport.md` | Bestået | Runtime screenshots mangler. |
| Live Activity targetet kan bygges | `06_verifikation/verifikationsrapport.md` | Bestået | Dynamic Island runtime screenshots mangler. |
| Aktuel iOS UI er dokumenteret visuelt | `02_figurer_og_screenshots/app_screenshots/aktuel_ios26/` | Bestået | 13 screenshots kræver manuel visuel godkendelse før endelig rapportbrug. |
| Data-/sikkerhedsmodellen er dokumenteret | `05_arkitektur_data_sikkerhed/data_og_sikkerhed/` | Stærk dokumentation | Fuld security proof kræver flere integrationstests. |
