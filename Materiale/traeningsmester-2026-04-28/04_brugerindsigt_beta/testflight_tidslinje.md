# TestFlight-Tidslinje

Kilde: scoped Gmail-søgning efter "TestFlight", "Traeningsmester" og "Traeningsmester 2.0" den 2026-04-28. Der er kun brugt emne, dato, platform og korte systemmetadata. Rå mailtekst, testeradresser, TestFlight-linkparametre og Apple-identifikatorer er ikke kopieret ind i public materiale.

## Observeret Distribution

| Dato | Version/build | Platform | Evidens | Rapportbrug |
|---|---:|---|---|---|
| 2026-03-25 22:20 UTC | Invitation | iOS | TestFlight invitation til Traeningsmester med appbeskrivelse om programmer, øvelser, tracker og historik | Start på iOS-beta og formel rekruttering |
| 2026-03-26 16:29 UTC | 1.0 (5) | iOS + watchOS | TestFlight-mail: klar til test på iOS og watchOS | Første observerede build efter invitation |
| 2026-03-27 13:02 UTC | 1.0 (6) | iOS + watchOS | TestFlight-mail | Iteration samme uge som betaåbning |
| 2026-03-27 13:17 UTC | 1.0 (8) | iOS + watchOS | TestFlight-mail | Hurtig efterfølgende build |
| 2026-03-29 23:29 UTC | 2.0 (1) | iOS + watchOS | TestFlight-mail | Overgang til 2.0-sporet |
| 2026-03-30 23:07 UTC | 2.0 (2) | iOS + watchOS | TestFlight-mail | Build omkring Messenger-observeret link-/opdateringsfriktion |
| 2026-03-31 00:09 UTC | 2.0 (3) | iOS + watchOS | TestFlight-mail | Natlig iteration op til større releasebesked |
| 2026-03-31 10:58 UTC | 2.0 (4) | iOS + watchOS | TestFlight-mail | Samme dag som katalog-/søgning-/releasefeedback |
| 2026-03-31 19:24 UTC | 2.0 (5) | iOS + watchOS | TestFlight-mail | Iterativ build efter feedback samme dag |
| 2026-04-01 18:19 UTC | 2.0 (6) | iOS + watchOS | TestFlight-mail | Fortsat testdistribution efter martsfeedback |
| 2026-04-15 00:40 UTC | 2.0 (7) | iOS + watchOS | TestFlight-mail | Ny beta efter april-iteration |
| 2026-04-15 01:02 UTC | 2.0 (8) | iOS + watchOS | TestFlight-mail | Hurtig efterfølgende iteration |
| 2026-04-20 00:57 UTC | 2.0 (9) | iOS + watchOS | TestFlight-mail | Pre-audit/releasekandidat |
| 2026-04-23 15:19 UTC | 2.0 (10) | iOS + watchOS | TestFlight-mail | Sen beta med fortsat polish |
| 2026-04-23 23:37 UTC | 2.0 (11) | iOS + watchOS | TestFlight-mail | Samme døgn som build 10, viser kort release-cyklus |
| 2026-04-25 21:01 UTC | 2.0 (12) | iOS + watchOS | TestFlight-mail | Seneste observerede beta-build i Gmail-scope |

## Supplerende Teknisk Mail-Evidens

| Dato | Kilde | Observation | Rapportbrug |
| --- | --- | --- | --- |
| 2026-04-20 | Xcode Cloud | CI-build for `main` lykkedes med commit-emne om admin center og hærdning af øvelseskatalog | Kan bruges som teknisk release-/projektledelsesspor |
| 2026-04-21 | Supabase security advisor | Security-advisor advarede om RLS/public access-problem i projektet | Bruges som begrundelse for sikkerheds- og RLS-afsnit, ikke som public råmail |

## Fortolkning

Tidslinjen viser et iterativt beta-forløb med korte feedback-/release-cyklusser fra invitationen den 2026-03-25 til mindst build 12 den 2026-04-25. Sammenholdt med Messenger-dybdeanalysen er den særligt stærk til at dokumentere, at feedback om installation, søgning, øvelseskatalog, kg/lbs og watch ikke opstod som isolerede ideer, men blev håndteret i et aktivt TestFlight-forløb.

## Begrænsning

Denne tidslinje dokumenterer distribution, ikke testeradfærd eller feedbackkvalitet. Testerfeedback skal kobles fra Messenger/Facebook/app feedback efter anonymisering. TestFlight-mails oplyser også om crash-/brugsdata knyttet til testeridentitet; den type persondata er ikke kopieret til repoet.
