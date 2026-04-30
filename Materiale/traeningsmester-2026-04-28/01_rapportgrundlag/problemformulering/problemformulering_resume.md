# Problemformulering - Resume Og Appkobling

Kilde: `problemformulering_ucph_math_redacted.pdf`, dateret 2026-01-26 med PDF-metadata opdateret 2026-02-03. Rå PDF er flyttet til privat råmappe, fordi den indeholdt mailadresse.

## Hovedspørgsmål

Bachelorens centrale spørgsmål er, hvordan en digital træningsapp kan designes, så programstrukturen både understøtter vedvarende motivation og muliggør fleksibel håndtering af afvigelser fra et planlagt træningsforløb uden at øge risikoen for demotivation og frafald.

## Problemfelt

Udgangspunktet er, at mange træningsapps behandler progression som et lineært forløb, hvor brugeren forventes at følge programmet kontinuerligt. Når brugeren misser træningspas eller holder uplanlagte pauser, kan appens struktur derfor komme til at markere afvigelsen som nederlag fremfor som en normal variation i træningsadfærd.

## TræningsMester Som Egenudviklet Designcase

I bachelorprojektet adresserer den udviklede TræningsMester-app problemfeltet gennem flere konkrete design- og arkitekturvalg:

- Aktiv cyklus-runtime kan overstyre normal planindeks-logik, så programmet kan styres af makro/meso/deload fremfor én lineær tæller.
- Completion-events gemmes separat fra trackerlog, så tracker-off træninger og afsluttede pas stadig kan tælle med i progression og motivation.
- Home viser én næste handling og kan fastholde brugeren i nuværende kontekst efter træning i stedet for at tvinge øjeblikkelig progression.
- Tracker understøtter resttimer, sidste-sæt-preview, AMRAP, isometriske sæt, kropsvægt-notation og superset-kontekst, så faktisk træning kan afvige fra standardplan uden at miste struktur.
- Watch og Live Activity udvider træningsflowet til situationer hvor mobilen ikke er hovedinterface.
- Onboarding og premium-import hjælper brugeren fra eksisterende træningsvaner ind i appen, i stedet for at kræve en fuldstændig ny start.

## Rapportafsnit Der Kan Bygge På Dette

- Problem og motivation: lineære træningsapps vs. realistisk adherence.
- Designanalyse: hvordan UI reducerer nederlagsfølelse og fremhæver næste sikre handling.
- Teknisk analyse: hvordan data- og runtime-modeller gør fleksibiliteten mulig.
- Evaluering: beta-feedback, screenshots og testlogs som evidens for implementeret adfærd.
