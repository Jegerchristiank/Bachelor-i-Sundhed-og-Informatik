# AGENTS.md

Denne fil er styringsprompten for fremtidige LLM-agenter i denne Overleaf-mappe.
Læs den ved opstart og hold den opdateret, når rapportstruktur, materialekilder eller formalia ændrer sig.

## Kort Status

- Repoet er en Overleaf/LaTeX-mappe til bachelorrapporten om Træningsmester.
- Hovedfilen er `main.tex`; layoutet styres af `KUstyle.sty`.
- Dokumentet skal compiles med XeLaTeX eller LuaLaTeX, fordi templaten bruger `fontspec`.
- `main.tex` indlæser `kildesoegning.tex` som bilag og bruger `referencer.bib` til referenceafsnittet.
- Forsidens KU-header, fakultetstekst, headerfarve og coverbaggrund styres fra `main.tex` via KUstyle-makroer.
- `Materiale/traeningsmester-2026-04-28/` er den kuraterede materialepakke til rapportarbejdet.
- `referencer.bib`, `referencer.md` og `referencer/` er referencebiblioteket med BibTeX-nøgler, kildebeskrivelser og lokale åbne PDF-kopier.
- Rå Messenger-, Facebook-, Gmail-, KU webmail-, Absalon- og Xcode-logdata er bevidst ikke inkluderet i den kuraterede mappe.
- `NAVIGATOR.md` er repoets autoritative strukturkort og skal læses før større ændringer.

## Obligatorisk Navigering

- Læs `NAVIGATOR.md` først for at forstå repoets struktur og læserute.
- Læs `Materiale/traeningsmester-2026-04-28/NAVIGATOR.md`, når du bruger materialepakken.
- Brug `Materiale/traeningsmester-2026-04-28/01_rapportgrundlag/problemformulering/problemformulering_autoritativ.md` som primær kilde til problemformulering.
- Brug `Materiale/traeningsmester-2026-04-28/01_rapportgrundlag/rapportstruktur/rapportafsnit_mapping.md` som primær kilde til rapportens kapitelstruktur.
- Læs `referencer.md` inden nye skrive- eller redigeringsiterationer, så rapportens kildevalg, BibTeX-nøgler og lokale PDF'er holdes konsistente.
- Hvis mapper, filer, rapportafsnit eller kildeansvar ændrer sig, skal `NAVIGATOR.md` opdateres i samme omgang.
- Hvis rapportens problemformulering, titel, vejleder, dato eller andre formalia ændrer sig, skal `main.tex` og denne fil vurderes for opdatering.

## Kendte Metadata

- Forfatter: Christian Kristensen, TDH522.
- Projekt/case: Træningsmester.
- Projekttype: Bachelorprojekt.
- Uddannelse: Bachelor i Sundhed og Informatik.
- Fakultet: Det Sundhedsvidenskabelige Fakultet.
- Institut: Institut for Folkesundhedsvidenskab.
- Afdeling: Afdeling for Sundhedstjenesteforskning.
- Vejleder: Karsten Vrangbæk.
- Arbejdstitel i LaTeX: `Træningsmester`.
- Arbejdssubtitle i LaTeX: `Design og implementering af en digital træningsapp til fleksibel progression og motivation`.
- Afleveringsdato: afventer.
- Forsidens KU-header skal pege på Det Sundhedsvidenskabelige Fakultet, ikke den oprindelige matematik-template.

## Rapportens Autoritative Spor

Bachelorens centrale spørgsmål er, hvordan en digital træningsapp kan designes og implementeres, så programstruktur, progression og feedback understøtter vedvarende motivation og fleksibel håndtering af afvigelser fra et planlagt træningsforløb uden at øge risikoen for demotivation og frafald.

Træningsmester skal behandles som design- og implementeringscase. SwiftUI, Supabase, watchOS, Live Activity og træner-/adminfunktioner er tekniske midler til at undersøge problemformuleringen, ikke konkurrerende hovedproblemer.

## Arbejdsregler

- Opfind ikke datoer, institutionsnavne, censoroplysninger eller vejlederdetaljer. Marker usikre felter som `Afventer`.
- Fjern synlig template- og fyldtekst fra rapporten. Brug kun skjulte LaTeX-kommentarer til arbejdsnoter.
- Skriv rapporttekst på dansk, medmindre brugeren beder om andet.
- Hold rapporten problemstyret. Undgå at gøre den til en produktpitch eller featureliste.
- Brug materialepakkens kuraterede summaries før private rådata.
- Brug `referencer.bib` og `referencer.md` som primære eksterne kildeindeks; tilføj nye kilder begge steder og gem kun PDF'er, når de er åbent tilgængelige.
- Kopier ikke lange passager fra kursusmateriale, mails, Messenger, Facebook eller andre lukkede kilder.
- Anonymiser beta- og brugerindsigt, og undgå personhenførbare detaljer i `main.tex`.
- Nedton claims, hvor `Materiale/traeningsmester-2026-04-28/06_verifikation/quality_gate_review.md` markerer åbne gaps.
- Brug kun screenshots efter manuel godkendelse i screenshot-approval-materialet.
- Bevar LaTeX-kompatibilitet med Overleaf. Undgå lokale absolute paths i `main.tex`.
- Revertér aldrig brugerens ændringer uden eksplicit instruktion.
- Efter hver afsluttet ændring skal ændringen committes og pushes til `main`, medmindre brugeren eksplicit beder om noget andet.

## Centrale Filer

- `main.tex`: rapportens hovedfil og nuværende blanke canvas.
- `KUstyle.sty`: KU-forside- og layoutmakroer.
- `README.md`: kort template-vejledning.
- `NAVIGATOR.md`: repoets strukturkort.
- `referencer.bib`: BibTeX-bibliotek for eksterne artikler, standarder, tekniske docs og juridiske kilder.
- `referencer.md`: læsevejledning, kildeforklaring og link mellem BibTeX-nøgler, DOI/webkilder og lokale PDF'er.
- `referencer/`: lokale åbne PDF-kopier navngivet efter BibTeX-kilderne.
- `kildesoegning.tex`: metodeklart LaTeX-afsnit, der redegør for kildesøgning og referenceudvælgelse.
- `Materiale/traeningsmester-2026-04-28/README.md`: kort vejledning til materialepakken.
- `Materiale/traeningsmester-2026-04-28/NAVIGATOR.md`: detaljeret strukturkort for materialepakken.

## Verifikation

- Efter ændringer i `main.tex` skal der helst køres en LaTeX compile med XeLaTeX eller LuaLaTeX.
- Hvis lokal compile ikke er mulig, skal finalen nævne det tydeligt.
- Efter ændringer i struktur eller agentinstruktioner skal `git status --short` kontrolleres, så ændringsomfanget er klart.
