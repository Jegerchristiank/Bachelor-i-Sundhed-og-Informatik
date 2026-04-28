# Automation- Og Capture-Begrænsninger

Dato: 2026-04-28

## Runtime Capture Status

Der er taget en ny Xcode MCP screenshot-capture på `TM-iPhone-16` iOS 18.5, og appen er bygget/testet lokalt. Den øvrige brede screenshotdækning består af eksisterende audit-screenshots kopieret ind i public pakken med manifest.

## Automation Hooks

Appen har automation hooks i `AppState`, blandt andet:

- `TM_AUTOMATION_EMAIL`
- `TM_AUTOMATION_PASSWORD`
- `TM_AUTOMATION_SKIP_ONBOARDING`
- `TM_AUTOMATION_TAB`

I denne shell-session var automation/test credentials ikke tilgængelige som miljøvariabler. Derfor blev der ikke kørt en ny fuld authenticated screenshot-tour gennem alle appstates med live login.

## Konsekvens

Det betyder ikke, at flows mangler i appen. Det betyder, at denne evidence run ikke kan påstå en ny, komplet live-capture af alle authenticated states. Rapporten bør skelne mellem:

- funktionel verificering via build/tests,
- arkitektur- og kodeevidens,
- eksisterende audit-screenshots,
- ny Xcode MCP smoke-capture,
- kendte runtime screenshot-gaps.

## Næste Skridt Hvis Der Skal Suppleres

For en komplet ny screenshot-run skal der opsættes en dedikeret anonym testkonto og fixturedata, hvorefter automation hooks kan bruges til at åbne relevante tabs og states uden at eksponere private brugerdata. Det anbefales især for:

- onboarding reset,
- tracker completion,
- watchOS runtime,
- Live Activity/Dynamic Island,
- admin-center,
- loading/error states.

