# Use Cases

Dato: 2026-04-28  
Aktører er anonymiserede. Use cases er baseret på appens routes, repositories, domain models, support services og Supabase schema.

## UC-01: Opret konto og log ind

Primær aktør: Personlig bruger  
Sekundære aktører: Supabase Auth, Apple/Google identity provider ved social login

Forudsætninger:

- Appen har gyldig Supabase URL og anon key.
- `AppEnvironment` har accepteret miljøkonfigurationen.

Main success scenario:

1. Brugeren åbner appen.
2. `TraeningsmesterApp` bootstrapper `AppState`.
3. `RootView` viser login, hvis brugeren ikke er autentificeret.
4. Brugeren logger ind eller opretter konto via `AuthRepository`.
5. Supabase returnerer session.
6. `AppState` henter bruger, settings og onboarding state.
7. Appen viser onboarding eller app-shell.

Alternativer:

- Password recovery åbnes via auth callback og globalt recovery-sheet.
- Social login/linking fejler og vises som brugerforståelig fejl.

Sikkerhed:

- Klienten bruger anon key.
- Session valideres før brugerbundne queries.
- Service-role token afvises af `AppEnvironment`.

## UC-02: Gennemfør onboarding

Primær aktør: Personlig bruger  
Sekundære aktører: Supabase repositories, import Edge Functions ved importflow

Forudsætninger:

- Brugeren er autentificeret.
- Onboarding er ikke markeret som gennemført.

Main success scenario:

1. `RootView` hoster onboarding-flowet.
2. Brugeren vælger startvej, præferencer og eventuelt programimport.
3. Onboarding step graph bestemmer næste trin.
4. Appen opretter eller aktiverer relevant startprogram.
5. `AppState` markerer onboarding som gennemført.

Alternativer:

- Brugeren vælger hurtigt starterprogram.
- Brugeren vælger AI/import, som går via `ProgramReviewService` og Edge Functions.

## UC-03: Opret eller rediger træningsprogram

Primær aktør: Personlig bruger eller træner  
Sekundære aktører: Supabase Postgres/RLS

Forudsætninger:

- Brugeren er autentificeret.
- Profiltilstand er kendt.

Main success scenario:

1. Brugeren åbner Programmer-tab.
2. Appen henter planer via `PlanRepository`.
3. Brugeren opretter eller redigerer program.
4. Appen sender `PlanPayload` via repository.
5. Supabase gemmer data i `plan`.
6. Appen opdaterer UI og eventuelt aktiv plan.

Alternativer:

- Program deles via share code eller invite.
- Træner tildeler program via træner-klient flow.

Sikkerhed:

- RLS kræver ejerskab eller eksplicit delt adgang.
- `profile_mode` bruges til at adskille personlig og trænerkontekst.

## UC-04: Tilføj træningsdag og øvelser

Primær aktør: Personlig bruger eller træner  
Sekundære aktører: Øvelseskatalog, Supabase storage ved medie

Forudsætninger:

- Brugeren har adgang til program/workout.
- Øvelser findes i katalog eller oprettes af bruger.

Main success scenario:

1. Brugeren åbner programdetalje eller workout editor.
2. Appen henter workouts og `plan_workouts`.
3. Brugeren tilføjer træningsdag.
4. Brugeren tilføjer øvelser til dagen.
5. Appen gemmer `workout` og `workout_exercises`.
6. UI viser rækkefølge, sæt, reps, vægt, pause og supersetdata.

Alternativer:

- Brugeren opretter privat øvelse med medie.
- Video konverteres til GIF før upload.
- Superset metadata gemmes på `workout_exercises`.

## UC-05: Find og like øvelse

Primær aktør: Personlig bruger  
Sekundære aktører: Øvelseskatalog, match repository

Forudsætninger:

- Brugeren er autentificeret.
- Kataloget kan hentes.

Main success scenario:

1. Brugeren åbner Øvelser eller Match.
2. Appen søger med fælles normalisering i `ExerciseSearchCatalog`.
3. Brugeren swiper eller sætter like-state.
4. `MatchRepository` gemmer swipe i `match`.
5. Liked øvelser kan bruges i programmer og lister.

Sikkerhed:

- Officielle og egne/private øvelser filtreres gennem RLS og read guards.

## UC-06: Start workout med tracker

Primær aktør: Personlig bruger  
Sekundære aktører: ActivityKit, Supabase trackerlog, watchOS

Forudsætninger:

- Brugeren har aktiv eller tilgængelig træningsdag.
- Tracker er slået til i settings.

Main success scenario:

1. Brugeren starter workout fra Home eller program.
2. Appen åbner `workoutTracker`.
3. Tracker henter `workout_exercises` og tidligere logs.
4. Brugeren logger sæt med reps, vægt og eventuel varighed.
5. `TrackerRepository` skriver til `trackerlog`.
6. Appen styrer pause-/sæt-timer og opdaterer Live Activity snapshot.
7. Ved afslutning gemmes completion event.
8. Historik og Home-humør kan bruge completion og trackerlog data.

Alternativer:

- Tracker-off route bruges til træning uden logning.
- Read-only route bruges ved begrænset adgang.
- Live Activity intent skriver idempotent via `client_action_id`.

## UC-07: Brug watchOS companion til dagens træning

Primær aktør: Watch-bruger  
Sekundære aktører: iOS app, WatchConnectivity, Supabase

Forudsætninger:

- iOS app har synkroniseret auth snapshot.
- Watch app har netværk eller lokal session restore.

Main success scenario:

1. Brugeren åbner watch appen eller complication shortcut.
2. `WatchAuthSyncBridge` modtager/bruger session payload.
3. `WatchWorkoutStore` initialiserer repositories.
4. Watch appen viser dagens træning.
5. Brugeren kan se øvelser, logge sæt og afslutte workout.
6. Completion/progression gemmes via samme backendkontrakter som iOS.

## UC-08: Aktiv træningscyklus styrer næste træning

Primær aktør: Premium bruger  
Sekundære aktører: Supabase RPC, watchOS

Forudsætninger:

- Brugeren har premium tier med cyklusadgang.
- Der findes en aktiv runtime state.

Main success scenario:

1. Appen resolver aktiv runtime via `TrainingCycleRepository`.
2. Runtime-valgt workout prioriteres over `plan.current_index`.
3. Tracker eller watch viser mål for workout via resolved targets.
4. Efter workout kaldes progression-RPC.
5. Runtime opdaterer næste uge/dag/mesocyklus eller kræver end action.

## UC-09: Træner administrerer klient

Primær aktør: Træner  
Sekundære aktører: Klient, trainer-client Edge Function

Forudsætninger:

- Træner er autentificeret og i relevant profiltilstand.

Main success scenario:

1. Træner åbner Klienter.
2. Appen kalder `TrainerClientService`/repository.
3. Edge Function validerer relation og operation.
4. Træner ser klientoversigt, aktivitet og programlinks.
5. Ændringer logges og gemmes server-side.

Sikkerhed:

- Træner-klient adgang er relationelt afgrænset.
- Service-role bruges kun i function runtime, ikke i klient.

## UC-10: Admin håndterer bruger eller aktivitetsfeed

Primær aktør: Admin  
Sekundære aktører: Admin Edge Function, Supabase Auth/Admin APIs

Forudsætninger:

- Brugeren er autentificeret.
- Server-side `is_admin` guard accepterer brugeren.

Main success scenario:

1. Admin aktiverer admin-center.
2. Appen kalder `AdminControlCenterRepository`.
3. Edge Function validerer adminrettighed.
4. Admin ser anonymiseret/administrativ brugeroversigt og aktivitet.
5. Admin udfører CRUD- eller reviewhandling.
6. Backend skriver audit-/activity event.

Sikkerhed:

- Lokal UI-state er ikke autoritativ.
- Adminadgang afgøres server-side.

## UC-11: Importer gammelt program eller historik

Primær aktør: Premium bruger  
Sekundære aktører: Supabase Edge Functions, OpenAI via server-side function

Forudsætninger:

- Brugeren har adgang til relevant premium/importflow.

Main success scenario:

1. Brugeren vælger programimport eller historikimport.
2. Appen opretter importjob via `training-import-manage`.
3. Normaliseringsfunction analyserer tekst/billeder.
4. Backend matcher øvelser deterministisk mod katalog.
5. Brugeren previewer resultat.
6. Valgte data gemmes som nyt program eller historikkladder.

Sikkerhed:

- OpenAI-kald sker ikke direkte fra klient.
- Importjob er brugerbundet og service-role styret på backend.

