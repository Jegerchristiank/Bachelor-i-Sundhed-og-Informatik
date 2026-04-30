# Navigator

Dette er navigationsfilen for Overleaf-mappen til bachelorrapporten om Træningsmester. Brug den som første stop, når rapporten skal skrives, struktureres eller vedligeholdes.

## Kort Formål

Repoet indeholder:

- en KU LaTeX-template,
- en ryddet `main.tex` som blankt rapport-canvas på A4-format,
- en kurateret materialepakke for Træningsmester pr. 2026-04-28,
- agentinstruktioner for fremtidigt rapportarbejde.

## Læserute

Start med disse filer i rækkefølge:

1. `AGENTS.md`
2. `NAVIGATOR.md`
3. `Materiale/traeningsmester-2026-04-28/README.md`
4. `Materiale/traeningsmester-2026-04-28/NAVIGATOR.md`
5. `Materiale/traeningsmester-2026-04-28/01_rapportgrundlag/problemformulering/problemformulering_autoritativ.md`
6. `Materiale/traeningsmester-2026-04-28/01_rapportgrundlag/rapportstruktur/rapportafsnit_mapping.md`
7. `Materiale/traeningsmester-2026-04-28/06_verifikation/quality_gate_review.md`

## Kritiske Pointers

- Hovedrapport: `main.tex`
- Kapitelinput: `problemformulering_og_afgraensning.tex` for afsnittet Problemformulering og afgrænsning, `teoretisk_og_faglig_ramme.tex` for afsnittet Teoretisk og faglig ramme, `metode.tex` for afsnittet Metode, `krav_og_use_cases.tex` for afsnittet Krav og use cases, `systemarkitektur.tex` for afsnittet Systemarkitektur, `interaktionsdesign.tex` for afsnittet Interaktionsdesign, `data_sikkerhed_og_interoperabilitet.tex` for afsnittet Data, sikkerhed og interoperabilitet, `implementering.tex` for afsnittet Implementering, `test_og_verifikation.tex` for afsnittet Test og verifikation, `evaluering_og_brugerindsigt.tex` for afsnittet Evaluering og brugerindsigt og `diskussion.tex` for afsnittet Diskussion
- KU-style og forsidemakroer: `KUstyle.sty` (overstyrer den oprindelige matematik-template med SUND-header og styrbar headerbaggrundsbredde)
- KU-forsidebaggrund: `KU-logo.pdf` som original, `assets/ku-cover-background.png` som rød rasterbaggrund og `assets/ku-cover-background-blue.png` som blå SUND-valgt rasterbaggrund
- Træningsmester-logo på forsiden: `assets/traeningsmester-logo-uden-baggrund.svg` og Overleaf-kompatibel `assets/traeningsmester-logo-uden-baggrund.pdf`
- Oprindelig template-grafik: `billede.png`
- Git-ignore: `.gitignore` holder lokale LaTeX build-artefakter ude af repoet.
- Git-attributter: `.gitattributes` markerer PDF-filer som binære, så kilde-PDF'er ikke tekst-diffes.
- Lokal template-vejledning: `README.md`
- Agentstyring: `AGENTS.md`
- Skrivematrix for hele rapporten: `skrivematrix.md` (internt arbejdsdokument, ikke rapportinput)
- Referencebibliotek: `referencer.bib`, `referencer.md` og lokale åbne PDF-kopier i `referencer/`; udvalgt kursusmateriale registreres med præcise slide-/sidetal uden at kopiere lukkede kursusfiler
- Kildesøgningsafsnit: `kildesoegning.tex`
- Billed- og materialebilag: `billedbilag.tex` med labels til aktuelle Træningsmester-screenshots, arkitekturdiagrammer, supplerende ER-udsnit og tabeller fra materialepakken
- Konverterede diagrammer til Overleaf: `assets/bilag/diagrammer/`
- Materialepakke: `Materiale/traeningsmester-2026-04-28/`
- Materialepakkens navigator: `Materiale/traeningsmester-2026-04-28/NAVIGATOR.md`
- Autoritativ problemformulering: `Materiale/traeningsmester-2026-04-28/01_rapportgrundlag/problemformulering/problemformulering_autoritativ.md`
- Kort problemresume: `Materiale/traeningsmester-2026-04-28/01_rapportgrundlag/problemformulering/problemformulering_resume.md`
- Rapportafsnit mapping: `Materiale/traeningsmester-2026-04-28/01_rapportgrundlag/rapportstruktur/rapportafsnit_mapping.md`
- Figurudvalg: `Materiale/traeningsmester-2026-04-28/01_rapportgrundlag/rapportstruktur/figurudvalg_udkast.md`
- Billedtekster: `Materiale/traeningsmester-2026-04-28/01_rapportgrundlag/rapportstruktur/billedtekster.md`
- Kursus- og metodekobling: `Materiale/traeningsmester-2026-04-28/03_kursus_og_metode/kursusmapping.md`
- Beta- og brugerindsigt: `Materiale/traeningsmester-2026-04-28/04_brugerindsigt_beta/`
- Arkitektur og design: `Materiale/traeningsmester-2026-04-28/05_arkitektur_data_sikkerhed/arkitektur/`
- Data og sikkerhed: `Materiale/traeningsmester-2026-04-28/05_arkitektur_data_sikkerhed/data_og_sikkerhed/`
- Verifikation og gaps: `Materiale/traeningsmester-2026-04-28/06_verifikation/`

## Mappeansvar

| Mappe/fil | Ansvar | Primær brug |
| --- | --- | --- |
| `main.tex` | Bachelorrapportens LaTeX-hovedfil | Skrivning og struktur |
| `KUstyle.sty` | KU-forside og layoutmakroer | Forsidebaggrund, headertekst, headerfarve og headerbaggrundsbredde styres fra `main.tex` |
| `.gitignore` | Git ignore-regler | Ignorerer lokale LaTeX build-artefakter |
| `.gitattributes` | Git diff-/merge-attributter | Marker PDF-filer som binære |
| `assets/` | Rapportens egne billedaktiver | Logoer, figurer og konverterede Overleaf-aktiver |
| `README.md` | Template-vejledning | Overleaf-opsætning |
| `AGENTS.md` | Arbejdsregler for LLM-agenter | Skal læses ved opstart |
| `NAVIGATOR.md` | Dette strukturkort | Skal opdateres ved strukturændringer |
| `skrivematrix.md` | Intern skrivematrix | Låser rød tråd, kilder, kursusspor, bilag og faldgruber for hele rapporten fra Indledning til Konklusion |
| `problemformulering_og_afgraensning.tex` | Kapitelinput | Færdig rapporttekst for Problemformulering og afgrænsning, indlæst fra `main.tex` |
| `teoretisk_og_faglig_ramme.tex` | Kapitelinput | Færdig rapporttekst for Teoretisk og faglig ramme, indlæst fra `main.tex` |
| `metode.tex` | Kapitelinput | Færdig rapporttekst for Metode, indlæst fra `main.tex` |
| `krav_og_use_cases.tex` | Kapitelinput | Færdig rapporttekst for Krav og use cases, indlæst fra `main.tex` |
| `systemarkitektur.tex` | Kapitelinput | Færdig rapporttekst for Systemarkitektur, indlæst fra `main.tex` |
| `interaktionsdesign.tex` | Kapitelinput | Færdig rapporttekst for Interaktionsdesign, indlæst fra `main.tex` |
| `data_sikkerhed_og_interoperabilitet.tex` | Kapitelinput | Færdig rapporttekst for Data, sikkerhed og interoperabilitet, indlæst fra `main.tex` |
| `implementering.tex` | Kapitelinput | Færdig rapporttekst for Implementering, indlæst fra `main.tex` |
| `test_og_verifikation.tex` | Kapitelinput | Færdig rapporttekst for Test og verifikation, indlæst fra `main.tex` |
| `evaluering_og_brugerindsigt.tex` | Kapitelinput | Færdig rapporttekst for Evaluering og brugerindsigt, indlæst fra `main.tex` |
| `diskussion.tex` | Kapitelinput | Færdig rapporttekst for Diskussion, indlæst fra `main.tex` |
| `referencer.bib` | Referencebibliotek | BibTeX-nøgler til eksterne kilder og verificeret kursusmateriale |
| `referencer.md` | Referencevejledning | Skal læses før nye skrive-/redigeringsiterationer; binder kildevalg, slide-/sidetal og PDF-status sammen |
| `referencer/` | Lokale åbne PDF-kopier | Arbejdskopier af åbne kilder, navngivet efter BibTeX-stems; lukkede kursusfiler kopieres ikke hertil |
| `kildesoegning.tex` | Metodeafsnit om kildesøgning | Kan inputtes i rapportens metodekapitel |
| `billedbilag.tex` | Billed- og materialebilag | Bilag med aktuelle, kuraterede Træningsmester-billeder, diagrammer, materialetabeller og labels |
| `Materiale/traeningsmester-2026-04-28/` | Kurateret rapportmateriale | Kilder, bilag og argumentation |

## Rapportens Nuværende Canvas

`main.tex` er ryddet for synlig skabelon- og fyldtekst. Det indeholder:

- A4-opsætning med XeLaTeX/LuaLaTeX-kompatibel fontopsætning,
- udfyldt forfatter, projekttype, arbejdstitel, arbejdssubtitle og vejleder,
- `Afventer` for dato,
- udfyldt fakultet, institut og afdeling efter KU/IFSV-oplysninger,
- en kort emnebeskrivelse baseret på den autoritative problemformulering,
- kapiteloverskrifter baseret på rapportafsnit-mappingen,
- færdig tekst for Problemformulering og afgrænsning via `\input{problemformulering_og_afgraensning}`,
- færdig tekst for Teoretisk og faglig ramme via `\input{teoretisk_og_faglig_ramme}`,
- færdig tekst for Metode via `\input{metode}`,
- færdig tekst for Krav og use cases via `\input{krav_og_use_cases}`,
- færdig tekst for Systemarkitektur via `\input{systemarkitektur}`,
- færdig tekst for Interaktionsdesign via `\input{interaktionsdesign}`,
- færdig tekst for Data, sikkerhed og interoperabilitet via `\input{data_sikkerhed_og_interoperabilitet}`,
- færdig tekst for Implementering via `\input{implementering}`,
- færdig tekst for Test og verifikation via `\input{test_og_verifikation}`,
- færdig tekst for Evaluering og brugerindsigt via `\input{evaluering_og_brugerindsigt}`,
- færdig tekst for Diskussion via `\input{diskussion}`,
- en separat intern skrivematrix i `skrivematrix.md` for hele rapporten fra Indledning til Konklusion,
- BibTeX-referenceafsnit baseret på `referencer.bib`,
- bilag efter referenceafsnittet med kildesøgning via `\input{kildesoegning}`,
- billed- og materialebilag efter referenceafsnittet med aktuelle Træningsmester-screenshots, arkitekturdiagrammer og supplerende tabeller via `\input{billedbilag}`,
- skjulte TODO-kommentarer som skrivehjælp.

## Vedligeholdelsesregler

- Opdater denne fil, hver gang en mappe, central fil eller rapportstruktur tilføjes, fjernes eller flyttes.
- Hold læseruten i sync med materialepakkens egne `README.md` og `NAVIGATOR.md`.
- Hvis `main.tex` får nye centrale afsnit, skal afsnitslisten her vurderes.
- Hvis materialepakken opdateres med en ny datostemplet mappe, skal denne fil pege på den nyeste autoritative mappe.
- Rå private data skal blive udenfor den kuraterede rapportmappe, medmindre brugeren udtrykkeligt beder om en ny redigeret bilagspakke.
- Bevar usikre formalia som `Afventer`, indtil de er eksplicit bekræftet.

## Repo Tree

```text
.
├── .gitattributes
├── .gitignore
├── AGENTS.md
├── KU-logo.pdf
├── KUstyle.sty
├── NAVIGATOR.md
├── README.md
├── billedbilag.tex
├── kildesoegning.tex
├── problemformulering_og_afgraensning.tex
├── teoretisk_og_faglig_ramme.tex
├── metode.tex
├── krav_og_use_cases.tex
├── systemarkitektur.tex
├── interaktionsdesign.tex
├── data_sikkerhed_og_interoperabilitet.tex
├── implementering.tex
├── test_og_verifikation.tex
├── evaluering_og_brugerindsigt.tex
├── diskussion.tex
├── skrivematrix.md
├── referencer.bib
├── referencer.md
├── referencer
│   └── åbne PDF-kopier af kilder
├── assets
│   ├── bilag
│   │   └── diagrammer
│   │       └── Overleaf-kompatible PDF-renderinger af Mermaid-diagrammer
│   ├── traeningsmester-logo-uden-baggrund.pdf
│   ├── traeningsmester-logo-uden-baggrund.svg
│   ├── ku-cover-background.png
│   └── ku-cover-background-blue.png
├── billede.png
├── main.tex
└── Materiale
    └── traeningsmester-2026-04-28
        ├── README.md
        ├── NAVIGATOR.md
        ├── 01_rapportgrundlag
        ├── 02_figurer_og_screenshots
        ├── 03_kursus_og_metode
        ├── 04_brugerindsigt_beta
        ├── 05_arkitektur_data_sikkerhed
        └── 06_verifikation
```
