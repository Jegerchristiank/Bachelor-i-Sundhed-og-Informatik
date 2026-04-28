# Screenshot-daekning

Dato: 2026-04-28

Denne kuraterede GitHub-pakke indeholder kun de aktuelle iOS 26.4 Xcode MCP screenshots fra `TM-iPhone-16-Pro-iOS26`. Historiske audit-screenshots fra aeldre appversioner er fravalgt, fordi de kan forvirre rapporten og ikke boer bruges som bevis for den aktuelle UI.

## Aktuel Dækning

| Område | Screenshot IDs | Vurdering |
| --- | --- | --- |
| Home/adherence | SS-053, SS-054, SS-063, SS-064, SS-065 | Stærk dækning af primær statusflade, næste træning, completion-delay, undo og efterfølgende progression. |
| Programmer | SS-055 | Dækker aktiv programliste og programstruktur. |
| Øvelser | SS-056 | Dækker øvelseskataloget i den aktuelle appversion. |
| Match | SS-057 | Dækker swipe-card flowet visuelt. |
| Indstillinger/konto | SS-058, SS-059 | Dækker settings og loginmetoder; brug kun efter manuel visuel PII-review. |
| Premium | SS-060 | Dækker abonnementsoverblik; import- og cyklusværktøjer dokumenteres primært via kode/diagrammer. |
| Historik | SS-061 | Dækker træningshistorik med logs. |
| Tracker | SS-062 | Dækker aktiv tracker-session. |

## Kendte Gaps

| Område | Status |
| --- | --- |
| Auth/login | Ikke med i den kuraterede pakke, fordi de tilgængelige billeder var historiske. |
| Onboarding | Ikke runtime-captured i denne pakke. Dokumenteres via kode, use cases og flowdiagrammer. |
| Admin | Ikke runtime-captured. Dokumenteres via Edge Function, sikkerhedsnotat og tests. |
| watchOS | Build-verificeret, men ikke screenshot-captured. |
| Live Activity/Dynamic Island | Build- og projection-test-verificeret, men ikke screenshot-captured. |
| Loading/error states | Ikke særskilt captured. |

## Anbefalet Rapportformulering

UI-dokumentationen består af en aktuel iOS 26.4 screenshotserie for centrale iOS-flows. Supplerende flows som watchOS, Live Activity, admin, onboarding og fejlstates dokumenteres via arkitektur, kode, test og kendte gaps, ikke med runtime-screenshots i denne pakke.
