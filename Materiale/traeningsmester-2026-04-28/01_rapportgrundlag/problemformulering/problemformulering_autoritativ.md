# Autoritativ Problemformulering Og Caseafgrænsning

Dato: 2026-04-28  
Formål: samle de to problemformuleringsspor i pakken, så rapporten ikke får konkurrerende hovedspørgsmål.

## Autoritativt Hovedspørgsmål

Hvordan kan en digital træningsapp designes og implementeres, så programstruktur, progression og feedback understøtter vedvarende motivation og fleksibel håndtering af afvigelser fra et planlagt træningsforløb uden at øge risikoen for demotivation og frafald?

## Case: Træningsmester Som Egenudviklet Native SwiftUI-App

Træningsmester er bachelorprojektets egenudviklede design- og implementeringscase. Case betyder her den app, der er designet, implementeret og undersøgt i projektet, ikke et eksternt eksempel. SwiftUI-migrationen, Supabase-arkitekturen, watchOS companion appen, Live Activity og træner-/adminfunktioner er ikke et separat hovedproblem. De er tekniske og organisatoriske midler i appen til at undersøge hovedspørgsmålet.

Den brede formulering om native SwiftUI, parity, sikker arkitektur og træner-klient-samarbejde bør derfor placeres som caseafgrænsning eller underspørgsmål:

Hvordan kan Træningsmester som native SwiftUI-løsning realisere denne fleksible træningsmodel gennem testbar arkitektur, sikker dataadgang, tydelige profiltilstande og dokumenterbare brugerflows?

## Underspørgsmål

1. Hvordan kan plan, workout, trackerlog, completion-events og cycle runtime modelleres, så faktisk træningsadfærd kan afvige fra den lineære plan uden datatab?
2. Hvordan kan UI og interaktionsdesign reducere friktion under træning, herunder tracker-off flow, watchOS og Live Activity?
3. Hvordan kan Supabase, RLS, typed repositories og Edge Functions understøtte fleksible brugerflows uden at eksponere privilegerede credentials?
4. Hvordan kan beta-feedback, screenshots, buildlogs, tests og diagrammer bruges som evidens for designvalg og implementering?

## Håndtering Af Eksisterende Filer

- `problemformulering_resume.md` matcher hovedspørgsmålet og bør bruges som primær problemformulering.
- `problemformuleringsresume.md` bør læses som case-/implementeringsafgrænsning, ikke som konkurrerende hovedproblem.
- Den redigerede PDF i `problemformulering_ucph_math_redacted.pdf` er den oprindelige kilde og bør nævnes som problemformuleringsgrundlag.
