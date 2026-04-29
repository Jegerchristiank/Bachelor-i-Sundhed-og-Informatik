# Navigator

Dette er navigationsfilen for Overleaf-mappen til bachelorrapporten om Træningsmester. Brug den som første stop, når rapporten skal skrives, struktureres eller vedligeholdes.

## Kort Formål

Repoet indeholder:

- en KU LaTeX-template,
- en ryddet `main.tex` som blankt rapport-canvas,
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
- KU-style og forsidemakroer: `KUstyle.sty` (overstyrer den oprindelige matematik-template med SUND-header)
- KU-forsidebaggrund: `KU-logo.pdf` som original og `assets/ku-cover-background.png` som Overleaf-brugt rasterbaggrund uden aktiv tekst fra matematiktemplaten
- Træningsmester-logo på forsiden: `assets/traeningsmester-logo-uden-baggrund.svg` og Overleaf-kompatibel `assets/traeningsmester-logo-uden-baggrund.pdf`
- Oprindelig template-grafik: `billede.png`
- Lokal template-vejledning: `README.md`
- Agentstyring: `AGENTS.md`
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
| `KUstyle.sty` | KU-forside og layoutmakroer | Skal sjældent ændres |
| `assets/` | Rapportens egne billedaktiver | Logoer, figurer og konverterede Overleaf-aktiver |
| `README.md` | Template-vejledning | Overleaf-opsætning |
| `AGENTS.md` | Arbejdsregler for LLM-agenter | Skal læses ved opstart |
| `NAVIGATOR.md` | Dette strukturkort | Skal opdateres ved strukturændringer |
| `Materiale/traeningsmester-2026-04-28/` | Kurateret rapportmateriale | Kilder, bilag og argumentation |

## Rapportens Nuværende Canvas

`main.tex` er ryddet for synlig skabelon- og fyldtekst. Det indeholder:

- udfyldt forfatter, projekttype, arbejdstitel, arbejdssubtitle og vejleder,
- `Afventer` for dato,
- udfyldt fakultet, institut og afdeling efter KU/IFSV-oplysninger,
- en kort emnebeskrivelse baseret på den autoritative problemformulering,
- kapiteloverskrifter baseret på rapportafsnit-mappingen,
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
├── AGENTS.md
├── KU-logo.pdf
├── KUstyle.sty
├── NAVIGATOR.md
├── README.md
├── assets
│   ├── traeningsmester-logo-uden-baggrund.pdf
│   ├── traeningsmester-logo-uden-baggrund.svg
│   └── ku-cover-background.png
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
