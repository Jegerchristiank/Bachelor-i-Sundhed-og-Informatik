# Systembeskrivelse: Traeningsmester

Dato: 2026-04-28  
Kildegrundlag: repoets SwiftUI-, watchOS-, Live Activity-, Supabase- og testfiler. Dokumentet bruger kun anonymiserede aktører.

## Formål

Traeningsmester er en native SwiftUI-applikation til planlægning, udførelse og historikføring af styrketræning. Systemet understøtter personlige brugere, trænere med klientrelationer, programdeling, øvelseskatalog, workout-tracker, watchOS companion app, iOS Live Activity og premium-funktioner til træningscyklusser og import/analyse af gamle programmer eller historik.

Målet i den aktuelle fase er funktionel parity med en eksisterende FlutterFlow-adfærd, men med native SwiftUI UI og typed Swift/Supabase dataadgang.

## Primære aktører

- Personlig bruger: opretter programmer, starter træning, logger sæt og ser historik.
- Træner: administrerer klientrelationer og kan arbejde med klientprogrammer via trænerflow.
- Klient: kan indgå i relation til træner og modtage program-/aktivitetsflow.
- Admin: kan tilgå server-valideret admin-center og aktivitetsfeed.
- Watch-bruger: bruger watchOS app til dagens træning, logning og afslutning.
- Supabase backend: leverer auth, Postgres-data, RLS, storage, RPC og Edge Functions.
- Apple platform services: StoreKit 2, WatchConnectivity, ActivityKit/WidgetKit og HealthKit-relaterede integrationspunkter.

## Systemafgrænsning

Systemets klientdel ligger primært under:

- `Traeningsmester/App`: app entrypoint, root navigation og global state.
- `Traeningsmester/Core`: konfiguration, domain models, payloads, navigation, repositories, support services og Live Activity state.
- `Traeningsmester/Features`: feature-specifikke SwiftUI views.
- `Traeningsmester/DesignSystem`: genbrugelige UI-komponenter, theme tokens og motion primitives.
- `TraeningsmesterWatch`: watchOS companion app og workout store.
- `TraeningsmesterWatchWidgets`: watch complication/widget shortcut.
- `TraeningsmesterLiveActivities`: iOS Live Activity widget.
- `supabase/functions`: Edge Functions til admin, trainer-client, import, programanalyse og billing.
- `SUPABASE_MASTER_SETUP.sql`: manuel master-setup for schema, views, RLS, storage og RPC.

## Overordnet runtime-flow

1. `TraeningsmesterApp` opretter `AppState` som global `@StateObject`.
2. `AppContentView` injicerer `AppState`, starter StoreKit transaction listener og kalder `bootstrapIfNeeded()`.
3. `AppState` loader `AppEnvironment` fra Info.plist/xcconfig og afviser placeholder- og service-role tokens.
4. `SupabaseRepositoryProviderFactory` opretter typed repository-container med anon Supabase-klient.
5. `AppState` henter auth-session og brugerindstillinger, herunder profiltilstand, subscription tier, adminstatus og tracker-/flow-præferencer.
6. `RootView` vælger login, onboarding eller app-shell baseret på auth/bootstrap/onboarding state.
7. Feature views kalder repository-protokoller og skriver ikke direkte mod Supabase.
8. Supabase håndhæver RLS og server-side guards; klientguards bruges som ekstra UX-/fejlbeskyttelse.
9. iOS synkroniserer session snapshot til watchOS via `WatchAppSyncBridge`, og watch appen initialiserer repositories ud fra lokal eller synkroniseret session.
10. Tracker og Live Activity deler snapshot gennem App Group storage, så Live Activity intents kan lave idempotente tracker writes med authenticated anon-klient.

## Centrale brugerflader

App-tabs defineres i `AppRoute.swift`:

- Træning (`hjem`)
- Programmer (`traeningsprogram`)
- Øvelser (`oevelser`)
- Match (`match`)
- Historik (`historik`)
- Indstillinger (`indstillinger`)

Pushed routes omfatter blandt andet klienter, programdetalje, premium flows, træningscyklus, øvelsesinfo, admin-center, workout tracker, read-only tracker og workout day editor.

## Centrale domæner

- Auth og session: login, signup, social login, password recovery og session restore.
- Programmer og workouts: `plan`, `workout`, `plan_workouts`, `workout_exercises`.
- Øvelser: katalog, brugerøvelser, private/officielle øvelser, medie-upload og admin-review.
- Match: swipe/like-state for øvelser.
- Tracker: logging af reps/vægt/varighed, pause- og sæt-timere, completion events og historik.
- Træningscyklus: makro/meso/deload, runtime state, progression og målprojektion.
- Træner-klient: klientrelationer, aktivitetsoversigt og programlinks.
- Premium/import: programanalyse, spørgeskema, programimport og historikimport via Edge Functions.
- Admin: server-valideret bruger-CRUD, aktivitetsfeed og review af indsendte øvelser.
- Watch/Live Activity: companion UI, complication shortcut og lock screen/Dynamic Island tracker status.

## Data og sikkerhed

Klienten må kun bruge Supabase anon key. `AppEnvironment` validerer nøgler ved opstart og afviser `service_role`. Alle brugerbundne tabeller i master-setup har RLS slået til. Kritiske tværbruger- eller adminoperationer håndteres via RLS, RPC eller Edge Functions med server-side validering.

Eksempler på sikkerhedsmekanismer:

- `auth.uid()` bruges i RLS-politikker til ejerkontrol.
- `tm_current_user_is_admin()` og `tm_require_admin()` er `security definer`-funktioner til server-valideret adminadgang.
- Træner-klient- og adminflows går via Edge Functions.
- Live Activity writes bruger authenticated anon-session og `client_action_id` til idempotency.
- Importjobs er service-role styrede i backend, mens brugeren kun ser egne job via RLS.

## Ikke-funktionelle hensyn

- Native SwiftUI UI med fælles designsystem og `design.md` som UI/UX-kontrakt.
- Typed domain models, payloads og repository-kontrakter for at mindske runtime schema-fejl.
- Testlag for unit og integration, især DTO mapping, progress logic, auth, tracker, settings, Live Activity projection og watch payload.
- Parity-sporing i `Docs/ParityMatrix.md`.
- Design debt/release-gate i `Docs/DesignDebtScorecard.md`.
- Watch target og Live Activity target skal buildes særskilt ved relevante ændringer.

