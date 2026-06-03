# Bacheloreksamen: TræningsMester præsentationsplan

Dato: 2026-06-02
Formål: tekstlig plan for et mundtligt bacheloroplæg om TræningsMester. Filen er en arbejdsplan til slides og speaker notes, ikke et færdigt slide deck.

## Mundtligt princip

Hovedmanusset under hvert slide skal kunne siges direkte ved eksamen. Det må ikke lyde som interne instruktioner, og det må ikke forklare, hvad der kan gøres, hvis der kommer spørgsmål. Den slags ligger kun i felterne med begreber, kilder og backup.

God tone i denne præsentation:

- naturligt første person: "I projektet undersøger jeg...", "Min vurdering er..."
- fagligt, men ikke stift: korte sætninger, konkret appbevis, tydelig afgrænsning
- ingen produktpitch: appen vises som case og artefakt, ikke som reklame
- ingen metasnak i manus: undgå sætninger om, hvad der kan gøres ved spørgsmål
- kilder og definitioner i noter: slides skal bære én påstand og et visuelt bevis

Den bærende fortælling er:

> TræningsMester viser, hvordan en digital træningsapp kan behandle afvigelser fra en træningsplan som en normal systemtilstand i stedet for som en fejl.

## Research- Og Formaliaafklaring

Formalia er kontrolleret i den aktuelle Browser-session og med repoets lokale materialer.

- KU-kursussiden for `SITA08010U Bachelorprojekt, sundhed og informatik` angiver 20 ECTS og beskriver bachelorprojektet som en selvstændig behandling, analyse og diskussion af en sundhedsinformatisk problemstilling. Læringsmålene fremhæver blandt andet problemdefinition, afgrænsning, metodeargumentation, analyse, diskussion, perspektivering og mundtlig akademisk fremstilling. Kilde: https://kurser.ku.dk/course/SITA08010U/2025-2026
- KU's censornormside angiver bachelorprojektet som projektopgave med efterfølgende mundtlig eksamen og en 30-minutters mundtlig ramme inklusiv bedømmelse. Kilde: https://sund.ku.dk/uddannelse/censor/censornormer-folkesundhed/
- CBS' vejledning om mundtligt forsvar bruges som generel akademisk eksamensramme: den mundtlige del bør ikke genfortælle rapporten, men udvælge de fagligt vigtigste pointer til diskussion. Kilde: https://teach.cbs.dk/resources/examination-formats/oral-exam-written-product/guidelines-for-oral-defense-of-theses-at-cbs/
- MIT Communication Lab understøtter en narrativ struktur med tydelig roadmap og høj signal-to-noise. Kilde: https://mitcommlab.mit.edu/be/2026/02/25/defense-season-wrapped-what-makes-a-thesis-defense-great/
- Harvard Catalyst, UCSD, Concordia og Monash understøtter korte assertion-evidence slides, stærke figurer, lav tekstmængde og speaker notes, der ikke overfylder selve sliden. Kilder: https://catalyst.harvard.edu/writing-communication-center/visualize-science/slides/, https://multimedia.ucsd.edu/best-practices/presentation-design.html, https://www.concordia.ca/students/success/learning-support/resources/oral-presentations/presentation-notes.html, https://www.monash.edu/it/current-students/resources-and-support/style-guide/giving-an-oral-presentation

## Tidsfordeling

Tidsmodellen bruger cirka 130 danske ord pr. minut. Den samlede anbefalede taletid skal ligge lige under 20 minutter, så der stadig er luft i en 30-minutters mundtlig eksamen.

| Del | Slides | Mål | Ratio | Funktion |
| --- | ---: | ---: | ---: | --- |
| Introduktion og problem | 1-3 | 3:42 | 19% | Gør problemet konkret og placerer appen som case, ikke produktpitch. |
| Metode og faglig ramme | 4-6 | 3:56 | 20% | Forklarer evidensniveau, teori og kravkobling. |
| Analyse og resultater | 7-12 | 8:12 | 41% | Viser datamodel, Home, tracker, progression, sikkerhed og støtteflader. |
| Diskussion og evidensgrænser | 13-14 | 2:38 | 13% | Viser teknisk verifikation, brugerindsigt, begrænsninger og næste trin. |
| Konklusion | 15 | 1:19 | 7% | Svarer direkte på problemformuleringen. |
| Samlet mål | 15 hovedslides | 19:47 | 100% | Cirka 20 minutter med naturlige pauser. |

## Beregnet Timing

Manustiden er beregnet ud fra `manus`-blokkene ved cirka 130 ord pr. minut. Ekstra pause er lagt ind til skift, korte vejrtrækninger og visuel forklaring af figurer.

| Slide | Ord i manus | Manus alene | Ekstra pause | Anbefalet slide-tid |
| ---: | ---: | ---: | ---: | ---: |
| 1 | 154 | 1:11 | 0:04 | 1:15 |
| 2 | 153 | 1:11 | 0:05 | 1:16 |
| 3 | 145 | 1:07 | 0:04 | 1:11 |
| 4 | 158 | 1:13 | 0:05 | 1:18 |
| 5 | 157 | 1:12 | 0:05 | 1:17 |
| 6 | 166 | 1:17 | 0:04 | 1:21 |
| 7 | 170 | 1:18 | 0:09 | 1:27 |
| 8 | 158 | 1:13 | 0:05 | 1:18 |
| 9 | 169 | 1:18 | 0:09 | 1:27 |
| 10 | 164 | 1:16 | 0:08 | 1:24 |
| 11 | 162 | 1:15 | 0:08 | 1:23 |
| 12 | 147 | 1:08 | 0:05 | 1:13 |
| 13 | 152 | 1:10 | 0:08 | 1:18 |
| 14 | 162 | 1:15 | 0:05 | 1:20 |
| 15 | 163 | 1:15 | 0:04 | 1:19 |
| Total | 2380 | 18:18 | 1:29 | 19:47 |

## Slide- Og Notestruktur

Hver hovedslide har samme struktur:

1. **Synligt på slide**: få ord, én påstand og et visuelt bevis.
2. **Visuel**: den figur, tabel eller screenshot der skal bære pointen.
3. **Ankre**: korte stikord øverst i notes, så blikket hurtigt kan finde tilbage.
4. **Manus**: ordret fallback-manus, skrevet som naturlig eksamenstale.
5. **Begreber**: definitioner til spørgsmål.
6. **Kilder og evidens**: hvad pointen hviler på.
7. **Backup**: hvilke backupslides der passer til spørgsmål.

## Hurtig Billedfinder

Figurlabels som `fig:tm-ios-home-ready` kommer fra `billedbilag.tex`. Det er rapportens LaTeX-labels, ikke filnavne. Til PowerPoint skal du bruge filstierne herunder.

Tip: Screenshots ligger som JPG og kan indsættes direkte. Diagrammer findes både som PDF i `assets/bilag/diagrammer/` og som SVG i materialepakken; brug SVG i PowerPoint, hvis du vil skalere skarpt og eventuelt redigere visuelt.

### Slide-For-Slide Visuel Finder

Denne tabel er den praktiske arbejdsliste, når du bygger PowerPointen.

| Slide | Hvad skal ind på sliden | Fil eller kilde |
| ---: | --- | --- |
| 1 | Home-screenshot med aktuel træningshandling | `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/app_screenshots/aktuel_ios26/ios26-02-home-ready-testkonto-2026-04-28.jpg` |
| 2 | Enkel model med fire felter: plan, faktisk træning, feedback, næste handling | Ingen billedfil. Byg som fire bokse direkte i PowerPoint. |
| 3 | Forenklet systemkontekst | Brug helst `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/system_context.svg`. Alternativ: `assets/bilag/diagrammer/system_context.pdf`. |
| 4 | Evidenstrekant med artefakter, beta-feedback og teknisk verifikation | Ingen billedfil. Byg som trekant/model direkte i PowerPoint. |
| 5 | 2x2-model med fire faglige spor | Ingen billedfil. Byg som 2x2-model direkte i PowerPoint. |
| 6 | Mini-traceability fra problem til krav og appbevis | Ingen billedfil. Genskab som kort PowerPoint-tabel ud fra `billedbilag.tex`, især `tab:tm-use-cases` og `tab:tm-krav-traceability`. |
| 7 | Tracker/completion-flow og eventuelt ER-udsnit | Brug helst `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/tracker_completion_summary.svg`. Alternativt/crop: `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/data_model_er.svg`. |
| 8 | Home før og efter completion | `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/app_screenshots/aktuel_ios26/ios26-02-home-ready-testkonto-2026-04-28.jpg` og `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/app_screenshots/aktuel_ios26/ios26-12-home-next-training-testkonto-2026-04-28.jpg` |
| 9 | Aktiv tracker + tracker/completion-flow | `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/app_screenshots/aktuel_ios26/ios26-10-tracker-active-testkonto-2026-04-28.jpg` og `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/tracker_completion_summary.svg` |
| 10 | Runtime-udsnit fra tracker/completion eller ER-diagram | Brug `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/tracker_completion_summary.svg`; crop til runtime/næste handling. Alternativt crop `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/data_model_er.svg` til højre del. |
| 11 | Sikkerhedsgrænse | Brug helst `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/security_boundary_summary.svg`. Alternativ: `assets/bilag/diagrammer/security_boundary_summary.pdf`. |
| 12 | Watch sync + Live Activity idempotens | `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/watch_sync_sequence.svg` og `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/live_activity_idempotency_sequence.svg` |
| 13 | Teststatus i grøn/gul struktur | Ingen billedfil. Genskab som kort PowerPoint-tabel ud fra `billedbilag.tex` og `Materiale/traeningsmester-2026-04-28/06_verifikation/test_traceability_matrix.md`. |
| 14 | Beta-feedbacktemaer | Ingen billedfil. Genskab som kort PowerPoint-tabel ud fra `billedbilag.tex`, `Materiale/traeningsmester-2026-04-28/04_brugerindsigt_beta/feedbackkatalog.md`, `Materiale/traeningsmester-2026-04-28/04_brugerindsigt_beta/beta_tester_rapport.md` og `Materiale/traeningsmester-2026-04-28/04_brugerindsigt_beta/testflight_tidslinje.md`. |
| 15 | Konklusions-roadmap med fire svarlinjer | Ingen billedfil. Byg som simpel roadmap/model direkte i PowerPoint. |

### Label-Til-Fil Opslag

Brug denne tabel, hvis du møder en `fig:...`-label længere nede i planen.

| Label i planen | Fil du skal finde | Brug i præsentationen |
| --- | --- | --- |
| `fig:tm-ios-home-ready` | `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/app_screenshots/aktuel_ios26/ios26-02-home-ready-testkonto-2026-04-28.jpg` | Slide 1 og 8: Home med aktuel træningshandling. |
| `fig:tm-ios-home-next-training` | `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/app_screenshots/aktuel_ios26/ios26-12-home-next-training-testkonto-2026-04-28.jpg` | Slide 8: Home efter completion, hvor næste træning er rykket frem. |
| `fig:tm-ios-tracker-active` | `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/app_screenshots/aktuel_ios26/ios26-10-tracker-active-testkonto-2026-04-28.jpg` | Slide 9: aktiv tracker-session. |
| `fig:tm-ios-home-stale-session` | `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/app_screenshots/aktuel_ios26/ios26-01-home-stale-session-testkonto-2026-04-28.jpg` | Backup 24: afbrudt eller gammel tracker-session. |
| `fig:tm-ios-home-completion-delay` | `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/app_screenshots/aktuel_ios26/ios26-11-home-completion-delay-testkonto-2026-04-28.jpg` | Backup 24: completion-feedback og fortrydelsesvindue. |
| `fig:tm-system-context` | `assets/bilag/diagrammer/system_context.pdf` eller `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/system_context.svg` | Slide 3: forenklet systemkontekst. |
| `fig:tm-tracker-completion-summary` | `assets/bilag/diagrammer/tracker_completion_summary.pdf` eller `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/tracker_completion_summary.svg` | Slide 7, 9 og 10: tracker-on/off, completion og næste handling. |
| `fig:tm-data-model-er-middle` | `assets/bilag/diagrammer/data_model_er.pdf` eller `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/data_model_er.svg` | Slide 7 og backup 21: crop til midterdelen med trackerlog og completion-events. |
| `fig:tm-data-model-er-right` | `assets/bilag/diagrammer/data_model_er.pdf` eller `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/data_model_er.svg` | Slide 10 og backup 21/23: crop til højre del med cycle runtime. |
| `fig:tm-security-boundary-summary` | `assets/bilag/diagrammer/security_boundary_summary.pdf` eller `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/security_boundary_summary.svg` | Slide 11 og backup 25: sikkerhedsgrænse, RLS og Edge Functions. |
| `fig:tm-watch-sync-sequence` | `assets/bilag/diagrammer/watch_sync_sequence.pdf` eller `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/watch_sync_sequence.svg` | Slide 12 og backup 26: watchOS sync. |
| `fig:tm-live-activity-idempotency-sequence` | `assets/bilag/diagrammer/live_activity_idempotency_sequence.pdf` eller `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/live_activity_idempotency_sequence.svg` | Slide 12 og backup 27: Live Activity og idempotens. |

Tabel-labels som `tab:tm-use-cases`, `tab:tm-krav-traceability`, `tab:tm-test-traceability`, `tab:tm-beta-feedback` og `tab:tm-testflight-timeline` er ikke separate billedfiler. De ligger som LaTeX-tabeller i `billedbilag.tex` og bør genskabes som korte PowerPoint-tabeller med 3-6 udvalgte rækker.

## Hovedslides

### Slide 1: Når træning ikke følger planen

**Tid:** manus 1:11, anbefalet slide-tid 1:15
**Synligt på slide:** "Når træning ikke følger planen" + TræningsMester-logo + Home-screenshot.
**Visuel:** `fig:tm-ios-home-ready`. Fil: `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/app_screenshots/aktuel_ios26/ios26-02-home-ready-testkonto-2026-04-28.jpg`. Brug den stort og rent med én callout: "Næste handling".

**Ankre:** hverdag, afvigelser, næste handling, case.

```manus
I min bachelor undersøger jeg ikke bare, om man kan bygge endnu en træningsapp. Jeg undersøger, hvad der sker, når en træningsplan møder en almindelig hverdag. Træning bliver ofte rykket, forkortet, afbrudt eller registreret mindre detaljeret end planlagt. Hvis en app kun fungerer, når brugeren følger planen perfekt, bliver den svag netop der, hvor støtten er vigtigst.

TræningsMester er min egenudviklede case til at undersøge det problem. Den centrale idé er, at appen skal bevare retning, progression og feedback, selv når faktisk træning afviger fra planen. Home-skærmen er et godt sted at starte, fordi den viser brugerens mest praktiske spørgsmål: hvad er næste relevante træningshandling lige nu?

Det er også derfor, præsentationen starter med brugerens situation og ikke med teknologistakken. SwiftUI, Supabase, watchOS og Live Activity er vigtige, men de er midler. Det faglige spørgsmål er, om teknologien kan gøre et træningsforløb mere robust, når brugeren ikke opfører sig som en idealiseret model.
```

**Begreber:**
Afvigelse: når faktisk træning ikke følger den planlagte rækkefølge, timing eller registreringsgrad.
Næste handling: den handling appen gør tydelig for brugeren som næste skridt i forløbet.

**Kilder og evidens:** `fig:tm-ios-home-ready`; Teixeira et al. om autonom motivation; Yardley et al. om effektivt engagement; Eysenbach om frafald i digitale sundhedsinterventioner.

**Backup:** 16, 24.

### Slide 2: Afvigelsen er en normaltilstand

**Tid:** manus 1:11, anbefalet slide-tid 1:16
**Synligt på slide:** Problemformuleringen omskrevet til én linje: "Kan appen bevare progression og feedback, når planen ændrer sig?"
**Visuel:** fire små felter: plan, faktisk træning, feedback, næste handling.

**Ankre:** problemformulering, motivation, frafald, designkrav.

```manus
Problemformuleringen spørger, hvordan en digital træningsapp kan designes og implementeres, så programstruktur, progression og feedback understøtter vedvarende motivation og fleksibel håndtering af afvigelser uden at øge risikoen for demotivation og frafald.

Den formulering kan virke bred, men i projektet bliver den meget konkret. Appen skal kunne skelne mellem det planlagte forløb, det brugeren faktisk gør, den feedback der gives bagefter, og den næste handling i programmet. Det er både et sundhedsfagligt spørgsmål om motivation og adherence og et informatikfagligt spørgsmål om data, tilstande og adgangsregler. Afvigelsen er derfor ikke en undtagelse, som designet helst skal slippe udenom. Den er en normaltilstand, som systemet skal kunne håndtere tydeligt.

Den skelnen er vigtig, fordi en bruger godt kan have gennemført en meningsfuld træning, selv om registreringen ikke er komplet. Hvis appen ikke kan rumme den forskel, kan den enten miste progressionen eller give feedback, der opleves som straf. Begge dele kan svække den fortsatte brug.
```

**Begreber:**
Adherence: vedvarende efterlevelse eller fortsættelse af et træningsforløb.
Programstruktur: organisering af programmer, workouts, øvelser, sæt og progression.
Designkrav: et krav der omsætter problemformuleringen til noget systemet skal kunne.

**Kilder og evidens:** Autoritativ problemformulering; `problemformulering_og_afgraensning.tex`; Teixeira et al.; Eysenbach; ACSM.

**Backup:** 16, 17.

### Slide 3: TræningsMester er artefaktet

**Tid:** manus 1:07, anbefalet slide-tid 1:11
**Synligt på slide:** "Caseartefakt: iOS, watchOS, Live Activity, Supabase" + roligt systemkort.
**Visuel:** forenklet `fig:tm-system-context`. Fil: `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/system_context.svg`. Brug kun de centrale platforme.

**Ankre:** egenudviklet app, artefakt, afgrænsning, ikke featureliste.

```manus
TræningsMester er ikke et eksternt eksempel, der bare illustrerer teorien. Det er artefaktet i projektet: den app, der er designet, implementeret og analyseret. Det giver en særlig styrke, fordi teori, krav, brugerflade, datamodel og tests kan læses som dele af samme case.

Samtidig kræver det en skarp afgrænsning. Appen indeholder mange spor, blandt andet SwiftUI, Supabase, watchOS, Live Activity, trænerfunktioner, import og senere App Store-perspektiv. I bacheloren er de ikke lige vigtige. De er relevante, når de belyser kerneproblemet: hvordan programstruktur, faktisk træning, progression, feedback og sikker dataadgang hænger sammen. Derfor behandles TræningsMester som en design- og implementeringscase, ikke som en produktdemonstration.

Den afgrænsning beskytter også analysen. Når appen er egenudviklet, kan det være fristende at vise mest muligt af produktet. Det ville gøre oplægget bredere, men ikke stærkere. Den faglige værdi ligger i de dele af appen, hvor teori og implementering faktisk mødes.
```

**Begreber:**
Artefakt: det konkrete produkt eller materiale, der analyseres.
Design- og implementeringscase: en case hvor designvalg og teknisk realisering udgør det centrale materiale.
Afgrænsning: præcisering af hvad projektet undersøger og ikke undersøger.

**Kilder og evidens:** `fig:tm-system-context`; `systembeskrivelse.md`; KU-kursussidens krav om selvstændig analyse og afgrænsning.

**Backup:** 17, 31.

### Slide 4: Metoden viser plausibilitet

**Tid:** manus 1:13, anbefalet slide-tid 1:18
**Synligt på slide:** Evidenstrekant: artefakter, beta-feedback, teknisk verifikation. Nederst: "Plausibilitet, ikke effektmåling".
**Visuel:** trekant eller matrix med tre materialetyper.

**Ankre:** metode, materialer, plausibilitet, effektgrænse.

```manus
Metodisk behandler jeg appen som en design- og implementeringscase. Det betyder, at projektet ikke måler, om TræningsMester øger fysisk aktivitet eller fastholder brugere over tid. Det ville kræve et andet studie med flere brugere, længere observation og klare outcome-mål.

I stedet vurderer jeg, om der er en fagligt og teknisk sammenhængende model for problemet. Materialet består af kildesøgning, kursus- og faggrundlag, appens artefakter, anonymiseret beta-feedback og teknisk verifikation. De materialer kan bære forskellige typer påstande. Screenshots viser designede flows. Tests styrker teknisk plausibilitet. Feedback viser friktion og brugerbehov. Ingen af delene dokumenterer langtidseffekt alene. Den grænse er vigtig, fordi konklusionen skal passe til evidensen.

Metoden er derfor stærkest til at besvare hvordan-spørgsmålet. Den kan vise, hvordan problemet er omsat til krav, dataobjekter, brugerflows og testbare mekanismer. Den kan også vise, hvor modellen endnu er usikker. Det er en mere præcis vurdering end at påstå effekt, før appen er afprøvet i et længere og bredere brugerforløb.
```

**Begreber:**
Design- og implementeringsplausibilitet: at løsningen er fagligt og teknisk sandsynliggjort uden at være effektmålt.
Artefaktanalyse: analyse af appskærme, diagrammer, krav, testspor og implementeringsmateriale.
Outcome: et målt resultat, for eksempel øget fysisk aktivitet eller fastholdelse.

**Kilder og evidens:** `metode.tex`; `tab:analysestrategi`; Rethlefsen et al. om PRISMA-S; McGowan et al. om PRESS; Grundtvig og Clotworthy om analyse, etik og generaliserbarhed.

**Backup:** 18, 30.

### Slide 5: Fire faglige spor mødes i næste handling

**Tid:** manus 1:12, anbefalet slide-tid 1:17
**Synligt på slide:** 2x2-model: motivation/adherence, appkvalitet, progression/autoregulering, data/sikkerhed. Midten: "Næste handling".
**Visuel:** enkel faglig ramme med fire spor og én samlet vurdering.

**Ankre:** motivation, appkvalitet, progression, dataansvar.

```manus
Den faglige ramme samler fire spor. Det første spor er motivation, engagement og frafald, fordi appen kun er relevant, hvis den støtter fortsat træning. Det andet spor er app- og trackerevidens, hvor litteraturen viser potentiale, men også store krav til design og kontekst. Det tredje spor er styrketræningsprogression og autoregulering, fordi træning ikke bare er en kalenderaftale, men et forløb med belastning, volumen, øvelser og dagsform. Det fjerde spor er interaktionsdesign, datakvalitet og sikkerhed.

De fire spor mødes i spørgsmålet om næste handling. En god næste handling skal være motiverende nok til at støtte fortsættelse, træningsfagligt meningsfuld, let at forstå i brugerfladen og ansvarlig i data- og adgangsmodellen.

Det er derfor ikke nok, at appen ser overskuelig ud. Den skal også give en handling, der passer til progressionen, og som bygger på data med kendt kvalitet. Omvendt er det heller ikke nok, at datamodellen er teknisk elegant, hvis brugeren i praksis ikke kan komme videre under træning.
```

**Begreber:**
Effektivt engagement: brug der faktisk understøtter den ønskede adfærd.
Autoregulering: justering af træning efter performance, dagsform eller fatigue.
Datakvalitet: om data er gode nok til deres konkrete formål.

**Kilder og evidens:** Teixeira et al.; Yardley et al.; Laranjo et al.; Romeo et al.; Brickwood et al.; Stoyanov MARS; ACSM; Currier et al.; Greig et al.; Mohammed et al.; OWASP MASVS; Supabase RLS docs.

**Backup:** 17.

### Slide 6: Kravene gør problemet målbart

**Tid:** manus 1:17, anbefalet slide-tid 1:21
**Synligt på slide:** Mini-traceability: problem -> underspørgsmål -> use cases -> krav -> appbevis.
**Visuel:** kondenseret udsnit af `tab:tm-use-cases` og `tab:tm-krav-traceability`. Ingen billedfil; genskab som kort PowerPoint-tabel ud fra `billedbilag.tex`.

**Ankre:** sporbarhed, UC-06, UC-08, krav, vurderbarhed.

```manus
Problemformuleringen bliver vurderbar, når den omsættes til use cases og krav. De vigtigste use cases er ikke alle appens funktioner, men de flows der bærer bachelorens problem. UC-06 handler om at starte og gennemføre en workout med tracker. UC-08 handler om aktiv træningscyklus og næste workout. UC-07 dækker watchOS som støtteflade. Kravene binder de flows til tracker, completion, cycle runtime, Live Activity og sikker adgang.

Det er vigtigt, fordi appen ellers let kunne blive vurderet som en samling funktioner. Sporbarheden viser i stedet, at de centrale funktioner har en faglig rolle. Tracker og completion undersøger afvigelser i træningssituationen. Cycle runtime undersøger progression efter faktisk gennemførelse. RLS og Edge Functions undersøger, om fleksibiliteten kan realiseres uden at udvide klientens rettigheder.

På den måde fungerer kravene som en bro mellem rapportens teori og appens konkrete skærme. De gør det muligt at spørge mere præcist, om et flow faktisk understøtter problemformuleringen, eller om det bare er en funktion, der er praktisk at have med i produktet.
```

**Begreber:**
Use case: et bruger- eller systemforløb, appen skal understøtte.
Traceability: sporbarhed mellem problem, krav, implementering og test.
Funktionelt krav: krav til hvad systemet skal kunne gøre.

**Kilder og evidens:** `tab:tm-use-cases`; `tab:tm-krav-traceability`; `use_cases.md`; `krav_traceability.md`.

**Backup:** 19.

### Slide 7: Plan, log og completion skal adskilles

**Tid:** manus 1:18, anbefalet slide-tid 1:27
**Synligt på slide:** Datakæde: planlagt workout -> trackerlog -> completion-event -> cycle runtime -> næste handling.
**Visuel:** beskåret `fig:tm-tracker-completion-summary`. Fil: `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/tracker_completion_summary.svg`. Alternativ/crop: `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/data_model_er.svg` til `fig:tm-data-model-er-middle`.

**Ankre:** plan, faktisk træning, completion, runtime, data.

```manus
Det vigtigste implementeringsvalg er adskillelsen mellem planlagt træning, faktisk logging, completion og næste handling. Planen beskriver intentionen: hvilke øvelser, sæt og mål der er lagt ind. Trackerloggen beskriver det, brugeren faktisk registrerer under træningen. Completion-eventet beskriver, at passet er gennemført. Cycle runtime bruger gennemførelsen til at afgøre næste relevante træning.

Den adskillelse gør afvigelser håndterbare. Hvis alt blev presset ind i ét lineært kalenderindeks, ville systemet få svært ved at skelne mellem et planlagt pas, et delvist logget pas og et gennemført pas uden detaljer. TræningsMester kan derfor bevare kontinuitet uden at lade som om, at alle datatyper er lige detaljerede. Det er ikke maksimal registrering for enhver pris. Det er passende registrering til den beslutning, appen skal støtte.

Et konkret eksempel er et pas, hvor brugeren gennemfører træningen, men ikke registrerer hvert sæt. Det er svagt belæg for præcis volumenanalyse, men stærkt nok til at holde forløbet i gang og vise næste træning. Den forskel bliver kun mulig, fordi systemet ikke blander planen, loggen og gennemførelsen sammen.
```

**Begreber:**
Trackerlog: detaljeret log over sæt, reps, vægt eller varighed.
Completion-event: registrering af at et træningspas er gennemført.
Cycle runtime: den aktive cyklustilstand, der afgør næste workout efter faktisk gennemførelse.
Datagranularitet: hvor detaljerede data er.

**Kilder og evidens:** `fig:tm-tracker-completion-summary`; `fig:tm-data-model-er-middle`; `tab:tm-sql-fields`; Mohammed et al.; Greig et al.; ACSM.

**Backup:** 20, 21, 23.

### Slide 8: Home gør næste handling tydelig

**Tid:** manus 1:13, anbefalet slide-tid 1:18
**Synligt på slide:** Home før og efter completion: "Dag 1 af 3" -> "Dag 2 af 3".
**Visuel:** `fig:tm-ios-home-ready` og `fig:tm-ios-home-next-training` side om side. Filer: `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/app_screenshots/aktuel_ios26/ios26-02-home-ready-testkonto-2026-04-28.jpg` og `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/app_screenshots/aktuel_ios26/ios26-12-home-next-training-testkonto-2026-04-28.jpg`.

**Ankre:** overblik, feedback, kompetence, næste skridt.

```manus
Home-skærmen viser, hvordan datamodellen bliver til brugeroplevelse. Før træning viser den den aktuelle træningshandling og en tydelig startmulighed. Efter completion viser den, at næste træning er rykket frem. Brugeren skal ikke rekonstruere hele programmet for at forstå, hvor i forløbet vedkommende er.

Det er en lille skærmændring, men den har stor faglig betydning. Feedbacken gør ikke afvigelsen til et nederlag. Den fastholder retning og viser, at forløbet stadig fortsætter. Det passer med motivationsteorien, hvor oplevet kompetence og autonomi er vigtige for vedvarende adfærd. Samtidig er enkelheden i brugerfladen afhængig af modellen bagved. Home kan kun vise en enkel næste handling, fordi plan, logging, completion og cycle runtime allerede er adskilt.

Det gør Home til mere end en startside. Den bliver et koncentrat af hele systemets vurdering: hvilken træning er relevant nu, hvad er status, og hvordan kan brugeren handle uden først at læse en lang forklaring. Jo mere træningen afviger fra planen, desto vigtigere bliver den klarhed.
```

**Begreber:**
Home-skærm: appens startflade med status og næste relevante træningshandling.
Oplevet kompetence: brugerens oplevelse af at kunne mestre handlingen.
Feedback: tilbagemelding der hjælper brugeren eller systemet videre.

**Kilder og evidens:** `fig:tm-ios-home-ready`; `fig:tm-ios-home-next-training`; Teixeira et al.; Yardley et al.; Hornbæk.

**Backup:** 24.

### Slide 9: Tracker-on og tracker-off løser forskellige problemer

**Tid:** manus 1:18, anbefalet slide-tid 1:27
**Synligt på slide:** Aktiv tracker til venstre, tracker-on/off-flow til højre. Overskrift: "Mere data er ikke altid bedre i situationen."
**Visuel:** `fig:tm-ios-tracker-active` + `fig:tm-tracker-completion-summary`. Filer: `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/app_screenshots/aktuel_ios26/ios26-10-tracker-active-testkonto-2026-04-28.jpg` og `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/tracker_completion_summary.svg`.

**Ankre:** selvmonitorering, friktion, datakvalitet, tradeoff.

```manus
Trackerflowet viser den tydeligste afvejning i projektet. Når tracker er slået til, kan brugeren logge sæt, reps, vægt og pauser. Det giver bedre datagranularitet og et stærkere grundlag for historik og senere analyse. Men i selve træningssituationen kan detaljeret logging også være en belastning. Brugeren står mellem sæt, skifter udstyr, bliver afbrudt eller vil bare afslutte passet.

Derfor er tracker-off ikke et kvalitetsproblem i sig selv. Det er et lav-friktionsflow med en anden datakvalitet. Det bevarer completion, historik og næste handling, men det er svagere til detaljeret analyse af volumen og belastning. Pointen er, at datakvalitet skal vurderes efter formål. Til præcis træningsanalyse er tracker-on stærkere. Til kontinuitet og progression efter et gennemført pas kan completion være tilstrækkeligt.

Det er også en brugeroplevelsesmæssig afvejning. Hvis appen kræver for meget registrering, kan den skabe modstand mod at bruge flowet. Hvis den kræver for lidt, kan feedbacken blive uklar. Den bedste løsning er derfor ikke ét fast registreringsniveau, men tydelig forskel mellem detaljeret log og simpel gennemførelse.
```

**Begreber:**
Selvmonitorering: brugerens registrering af egen adfærd eller performance.
Lav friktion: lavt betjeningsbesvær i træningssituationen.
Tradeoff: en afvejning hvor én kvalitet styrkes på bekostning af en anden.

**Kilder og evidens:** Michie BCT Taxonomy; Stoyanov MARS; Mohammed et al.; `fig:tm-ios-tracker-active`; `fig:tm-tracker-completion-summary`; `tab:tm-tracker-flow-bpmn`.

**Backup:** 21.

### Slide 10: Progressionen flyttes efter faktisk gennemførelse

**Tid:** manus 1:16, anbefalet slide-tid 1:24
**Synligt på slide:** Cycle runtime: completion -> næste slot -> Home/Tracker/Watch.
**Visuel:** udsnit fra tracker/completion-diagrammet med runtime og næste handling fremhævet. Fil: `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/tracker_completion_summary.svg`.

**Ankre:** cycle runtime, faktisk adfærd, robust progression, normal systemtilstand.

```manus
Progressionen i TræningsMester er ikke kun en visuel markering. Den afhænger af, hvordan systemet bruger completion til at finde næste relevante træning. Når et pas er gennemført, kan cycle runtime flytte forløbet videre ud fra den faktiske handling i stedet for kun at følge et statisk planindeks.

Det er her afvigelsen bliver en normal systemtilstand. Brugeren kan træne på et andet tidspunkt eller gennemføre uden fuld sætlog, og systemet kan stadig fastholde retning. Samtidig er modellen ærlig om, hvad den ved. Et completion-event siger, at passet er gennemført. Det siger ikke nødvendigvis alt om volumen, belastning eller performance. Den forskel er central, fordi fleksibel progression kun er fagligt forsvarlig, hvis appen ikke blander simple gennemførelsesdata sammen med detaljeret træningsanalyse.

Cycle runtime er derfor en nøglemekanisme i appens argument. Den gør det muligt at flytte næste handling på baggrund af faktisk adfærd, men uden at gøre completion-data mere præcise, end de er. Det er her robusthed og datakritik skal være til stede samtidig.
```

**Begreber:**
Progression: udvikling i træningen over tid gennem belastning, volumen, øvelsesvalg, frekvens eller næste handling.
Planindeks: en lineær placering i et planlagt forløb.
Systemtilstand: systemets aktuelle forståelse af status og næste handling.

**Kilder og evidens:** `fig:tm-tracker-completion-summary`; `fig:tm-data-model-er-right`; ACSM; Currier et al.; Greig et al.; Larsen et al.

**Backup:** 23.

### Slide 11: Fleksibilitet kræver en sikkerhedsgrænse

**Tid:** manus 1:15, anbefalet slide-tid 1:23
**Synligt på slide:** Klient -> RLS/RPC -> database og klient -> Edge Function -> servervalidering.
**Visuel:** `fig:tm-security-boundary-summary`. Fil: `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/security_boundary_summary.svg`.

**Ankre:** klient, RLS, Edge Functions, least privilege, persondata.

```manus
Fleksibiliteten i brugerfladen skal have en tydelig sikkerhedsgrænse. I TræningsMester starter klienten handlingen, men backend afgør adgangen. Mobilappen bruger Supabase anon key og en bruger-session. Almindelige læse- og skrivehandlinger går gennem Row Level Security, hvor brugerens identitet og relationer afgør, hvilke rækker der må tilgås. Privilegerede flows, for eksempel admin, træner-klient, import og AI, flyttes til Edge Functions med server-side validering.

Det betyder, at lav friktion ikke kræver brede rettigheder i klienten. Brugeren kan få en enkel oplevelse, mens adgangskontrollen stadig ligger tæt på data og privilegeret logik. Sikkerhedsmodellen er derfor en del af det sundhedsinformatiske argument. Appen arbejder med personlige træningsdata og potentielle relationer mellem træner og klient, så fleksibel adgang må ikke blive uklar adgang.

Det er også grunden til, at sikkerhed ikke kun behandles som et teknisk bilag. I en sundhedsinformatisk app påvirker adgangsmodellen, hvor troværdigt systemet er som løsning. Hvis klienten kunne bestemme for meget alene, ville en god brugeroplevelse kunne skjule en svag dataafgrænsning.
```

**Begreber:**
RLS: Row Level Security, databasepolitikker der begrænser adgang på rækkeniveau.
Anon key: klient-sikker Supabase-nøgle, som først får brugeradgang sammen med auth-session.
Edge Function: server-side funktion til privilegeret eller ekstern logik.
Least privilege: princippet om mindst nødvendige rettigheder.

**Kilder og evidens:** `fig:tm-security-boundary-summary`; `tab:tm-rls-matrix`; Supabase RLS docs; Supabase API security docs; OWASP MASVS; GDPR.

**Backup:** 25.

### Slide 12: Støttefladerne reducerer telefonfriktion

**Tid:** manus 1:08, anbefalet slide-tid 1:13
**Synligt på slide:** "Samme session, mindre telefonfriktion" + watch sync og Live Activity idempotens.
**Visuel:** `fig:tm-watch-sync-sequence` og `fig:tm-live-activity-idempotency-sequence`. Filer: `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/watch_sync_sequence.svg` og `Materiale/traeningsmester-2026-04-28/02_figurer_og_screenshots/diagrammer/renderede_svg/live_activity_idempotency_sequence.svg`.

**Ankre:** watchOS, Live Activity, idempotens, støtteflader, afgrænsning.

```manus
watchOS og Live Activity er støtteflader til den samme træningsmodel. De er relevante, fordi træning er en situation, hvor telefonen ofte er upraktisk. Hvis status, næste sæt eller en aktiv session kan understøttes uden fuld telefoninteraktion, passer det til målet om lav friktion.

De bærer dog ikke konklusionen alene. Watch-sporet viser, hvordan session og workoutdata kan arbejde under samme adgangsmodel som iOS. Live Activity-sporet viser, hvordan App Group snapshot og idempotente skriver med `client_action_id` kan reducere risikoen for dobbeltregistrering. Evidensen er stærkest som build, test og arkitektur. Runtime-screenshots for watchOS og Dynamic Island mangler i materialet, så støttefladerne bruges som dokumenteret designretning og ikke som fuldt produktionsbevis.

Det er en bevidst begrænsning i vurderingen. Støttefladerne styrker argumentet om lav friktion, fordi de passer til træningssituationen. Men det stærkeste belæg i bacheloren ligger stadig i kerneflowet: plan, tracker, completion, runtime, Home og adgangskontrol.
```

**Begreber:**
Støtteflade: en sekundær brugerflade, der hjælper samme kerneflow.
Idempotens: samme handling kan gentages uden at skabe dubletter.
Runtime: faktisk kørsel i brug, ikke kun build eller diagram.

**Kilder og evidens:** `fig:tm-watch-sync-sequence`; `fig:tm-live-activity-idempotency-sequence`; Apple ActivityKit; Apple HIG Live Activities; Apple Watch Connectivity; `TrackerLiveActivityProjectionTests`; `WatchAuthSyncPayloadTests`.

**Backup:** 26, 27.

### Slide 13: Verifikationen viser styrke og grænser

**Tid:** manus 1:10, anbefalet slide-tid 1:18
**Synligt på slide:** Beskåret teststatus: iOS build, watchOS build, Live Activity build, 556 unit tests, integration gaps.
**Visuel:** `tab:tm-test-traceability` i grøn/gul struktur. Ingen billedfil; genskab som kort PowerPoint-tabel ud fra `billedbilag.tex` og `Materiale/traeningsmester-2026-04-28/06_verifikation/test_traceability_matrix.md`.

**Ankre:** build, 556 tests, delvis integration, clean checkout, gaps.

```manus
Verifikationen viser, at den centrale tekniske struktur er mere end en idé. iOS-klienten, watchOS-targetet og Live Activity-targetet kunne bygges, og der var 556 unit tests uden failures. Det styrker især påstande om domænelogik, tracker, completion, cycle runtime, payloads og Live Activity-projection.

Samtidig er verifikationen ikke fuld produktionsdokumentation. Nogle Supabase admin- og non-admin tests blev sprunget over, fordi testcredentials manglede. Edge Function helper tests blev ikke kørt, fordi Deno ikke var tilgængelig. Verifikationen er også fra en lokal freeze-state, ikke en ren reproducerbar CI-checkout. Den præcise vurdering er derfor, at appens centrale struktur er implementeret og delvist verificeret, men at drift, integration og sikkerhed kræver stærkere test før en bredere releasepåstand.

De åbne gaps svækker ikke nødvendigvis projektet, så længe de placeres rigtigt. De forhindrer brede claims om produktionsmodenhed, men de ødelægger ikke belægget for en design- og implementeringsmodel. Tværtimod gør de grænsen for konklusionen tydeligere.
```

**Begreber:**
Unit test: afgrænset test af en mindre del af systemets logik.
Integrationstest: test af om flere systemdele virker sammen.
Clean checkout: reproducerbar test fra en ren kodebase uden lokale ændringer.
Verifikationsgrænse: hvad testene kan og ikke kan dokumentere.

**Kilder og evidens:** `verifikationsrapport.md`; `test_traceability_matrix.md`; `quality_gate_review.md`; `tab:tm-test-traceability`.

**Backup:** 28.

### Slide 14: Brugerindsigten peger på modenhed før effekt

**Tid:** manus 1:15, anbefalet slide-tid 1:20
**Synligt på slide:** Tre feedbacktemaer: TestFlight/installation, katalog/søgning/enheder, støtteflader. Nederst: "Designinput, ikke effektbevis".
**Visuel:** `tab:tm-beta-feedback` og `tab:tm-testflight-timeline`, stærkt kondenseret. Ingen billedfil; genskab som kort PowerPoint-tabel ud fra `billedbilag.tex`, `Materiale/traeningsmester-2026-04-28/04_brugerindsigt_beta/feedbackkatalog.md`, `Materiale/traeningsmester-2026-04-28/04_brugerindsigt_beta/beta_tester_rapport.md` og `Materiale/traeningsmester-2026-04-28/04_brugerindsigt_beta/testflight_tidslinje.md`.

**Ankre:** beta, friktion, katalog, kg/lbs, usability, effektgrænse.

```manus
Beta-feedbacken viser, at friktion ikke kun opstår inde i trackerflowet. Den kan også opstå før appen overhovedet bruges rigtigt, for eksempel i TestFlight, installation og buildforståelse. Den kan opstå i kataloget, søgning, øvelsesmedier og enheder som kg og lbs. Og den kan opstå i støtteflader som watchOS og Live Activity.

Det gør feedbacken værdifuld som designindsigt. Den viser, hvor appen skal modnes, før et egentligt effektstudie giver mening. En god datamodel er ikke nok, hvis brugeren ikke kan finde øvelsen, forstå builden eller bruge flowet i træningssituationen. Samtidig kan feedbacken ikke dokumentere forbedret motivation eller adherence. Den rigtige rækkefølge er derfor usabilitytest, længere og bredere beta, stærkere runtime- og sikkerhedstest og først derefter et effektstudie.

Det er en vigtig rækkefølge. Hvis et effektstudie blev lavet for tidligt, ville resultaterne blande interventionens potentiale sammen med installationsproblemer, katalogfriktion og umodne støtteflader. Før appen kan måles som intervention, skal den være moden nok til at brugeren faktisk kan møde den som en stabil træningsstøtte.
```

**Begreber:**
Kvalitativ designindsigt: brugerobservationer der peger på problemer, behov og prioriteringer.
iOS-skævhed: skævhed fordi betaen primært dækker iOS-brugere.
Usabilitytest: systematisk test af om brugere kan forstå og udføre centrale handlinger.

**Kilder og evidens:** `feedbackkatalog.md`; `beta_tester_rapport.md`; `testflight_tidslinje.md`; `tab:tm-beta-feedback`; `tab:tm-testflight-timeline`; Grundtvig; Clotworthy; Yardley.

**Backup:** 29, 30.

### Slide 15: Fleksibilitet er en systemegenskab

**Tid:** manus 1:15, anbefalet slide-tid 1:19
**Synligt på slide:** Fire svarlinjer: "Adskil plan og handling", "Gør næste handling tydelig", "Håndhæv adgang server-side", "Test effekt senere".
**Visuel:** roadmap gentaget med de fire svar udfyldt.

**Ankre:** direkte svar, systemegenskab, bidrag, næste skridt.

```manus
Mit svar på problemformuleringen er, at fleksibel progression kræver en tydelig adskillelse mellem planlagt træning, faktisk logging, completion, feedback og næste handling. TræningsMester viser en plausibel design- og implementeringsmodel for den adskillelse. Home gør næste handling synlig. Tracker-on og tracker-off håndterer forskellige behov for datakvalitet. Cycle runtime flytter progressionen efter faktisk gennemførelse. RLS og Edge Functions holder adgangskontrollen uden for klienten.

Det vigtigste bidrag er derfor ikke én enkelt feature. Bidraget er en samlet model for, hvordan realistiske afvigelser kan behandles som normale systemtilstande uden at miste retning, historik eller dataansvar. Evidensen dokumenterer design og implementering, ikke effekt på motivation eller adherence. Næste faglige skridt er at teste modellen mere systematisk med brugere, runtime-scenarier og stærkere sikkerheds- og datakvalitetstest.

Den korte konklusion er, at fleksibilitet ikke må betyde uklarhed. Den skal bygges ind i både brugerfladen, datamodellen og adgangskontrollen. Når de dele hænger sammen, kan appen støtte brugeren videre i forløbet, også når træningen ikke passer perfekt til planen.
```

**Begreber:**
Systemegenskab: en kvalitet der opstår gennem samspil mellem UI, data, arkitektur og test.
Perspektivering: næste faglige skridt efter projektets afgrænsede fund.
Effektstudie: studie der måler om appen ændrer et outcome, for eksempel fysisk aktivitet eller fastholdelse.

**Kilder og evidens:** `konklusion.tex`; `diskussion.tex`; hele evidenskæden.

**Backup:** 30, 31.

## Backupslides

Backupslides ligger efter konklusionen. De skal ikke gennemgås fast, men de skal være tydelige nok til, at et spørgsmål kan besvares ved at hoppe direkte til den relevante dokumentation.

### Backup 16: Fuld problemformulering og underspørgsmål

**Brug ved spørgsmål om:** præcis afgrænsning, hovedspørgsmål eller underspørgsmål.
**Synligt:** fuld problemformulering + de fire underspørgsmål.
**Kort svar i notes:** Hovedspørgsmålet handler om fleksibel progression og motivation. Underspørgsmålene oversætter det til datamodel, UI/friktion, sikker arkitektur og evidensgrundlag.
**Begreber:** problemformulering, underspørgsmål, caseafgrænsning.
**Kilder:** `problemformulering_og_afgraensning.tex`; `problemformulering_autoritativ.md`.

### Backup 17: KU-kriterier og fagligt forsvar

**Brug ved spørgsmål om:** hvorfor oplægget ikke følger rapporten kronologisk.
**Synligt:** afgrænsning, teori/state of the art, metodeargument, analyse, kritisk diskussion, konklusion, perspektivering, mundtlig akademisk fremstilling.
**Kort svar i notes:** Oplægget er bygget som en faglig argumentation, fordi eksamen vurderer selvstændig behandling, analyse og diskussion af en sundhedsinformatisk problemstilling.
**Begreber:** bedømmelseskriterier, mundtlig akademisk fremstilling, selvstændig analyse.
**Kilder:** KU-kursusside; KU-censornormside.

### Backup 18: Kildekort for teorien

**Brug ved spørgsmål om:** litteraturvalg eller state of the art.
**Synligt:** fire kildespor med citation keys: motivation/adherence, apps/trackers/MARS, progression/autoregulering, data/sikkerhed/privacy.
**Kort svar i notes:** Kilderne er valgt efter funktion. Motivation forklarer hvorfor friktion og feedback er relevante. Træningslitteraturen forklarer progression. App- og trackerreviews viser potentiale og begrænsninger. Tekniske kilder afgrænser data- og sikkerhedspåstande.
**Begreber:** state of the art, scoping-søgning, kildekritik.
**Kilder:** `referencer.md`; `kildesoegning.tex`.

### Backup 19: Analysestrategi

**Brug ved spørgsmål om:** metode, materialer eller evidensniveau.
**Synligt:** `tab:analysestrategi` kondenseret til underspørgsmål, materiale og vurderingskriterium.
**Kort svar i notes:** Hvert underspørgsmål har egne materialer og egne vurderingskriterier. Det forhindrer, at screenshots bruges som effektbevis eller at tekniske tests bruges som brugeraccept.
**Begreber:** artefaktanalyse, plausibilitet, brugerindsigt, effektgrænse.
**Kilder:** `metode.tex`; `tab:analysestrategi`.

### Backup 20: Use cases og kravsporbarhed

**Brug ved spørgsmål om:** om appen faktisk understøtter problemformuleringen.
**Synligt:** UC-06, UC-07, UC-08 og krav F-08, F-09, F-13, F-14, F-15.
**Kort svar i notes:** Kerneflowet er sporbar fra problem til krav og implementering: tracker, completion, cycle runtime, watch og Live Activity. Admin, import og App Store-spor er sekundære i bachelorens hovedargument.
**Begreber:** use case, funktionelt krav, ikke-funktionelt krav, traceability.
**Kilder:** `tab:tm-use-cases`; `tab:tm-krav-traceability`; `use_cases.md`; `krav_traceability.md`.

### Backup 21: Datamodel for plan, log og completion

**Brug ved spørgsmål om:** teknisk modellering af plan og faktisk træning.
**Synligt:** ER-udsnit med program, workout, workout_exercises, trackerlog, workout_completion_events og training_cycle_runtime.
**Kort svar i notes:** Planen beskriver intentionen. Trackerlog beskriver detaljeret udførelse. Completion beskriver gennemførelse. Cycle runtime forbinder gennemførelsen med næste træning.
**Begreber:** datamodel, datagranularitet, completion-event, cycle runtime.
**Kilder:** `fig:tm-data-model-er-middle`; `fig:tm-data-model-er-right`; `tab:tm-sql-domain-overblik`; `tab:tm-sql-fields`.

### Backup 22: Tracker-on, tracker-off og datakvalitet

**Brug ved spørgsmål om:** om tracker-off skaber datatab.
**Synligt:** sammenligning: tracker-on giver høj datagranularitet, tracker-off giver lavere friktion og completion.
**Kort svar i notes:** Tracker-off er svagere til detaljeret analyse, men kan være stærkere til kontinuitet. Datakvalitet vurderes efter formål, ikke efter maksimal mængde data.
**Begreber:** datakvalitet, formålsbestemt data, selvmonitorering, tradeoff.
**Kilder:** Mohammed et al.; `fig:tm-tracker-completion-summary`; `data_sikkerhed_og_interoperabilitet.tex`.

### Backup 23: Cycle runtime og næste slot

**Brug ved spørgsmål om:** hvordan progressionen faktisk flyttes.
**Synligt:** completion-event -> aktiv training cycle runtime -> RPC/næste slot -> Home/Tracker/Watch.
**Kort svar i notes:** Cycle runtime gør progression afhængig af faktisk gennemførelse. Det er her appen bevæger sig fra kalenderlogik til fleksibel progression.
**Begreber:** cycle runtime, RPC, planindeks, progression.
**Kilder:** `fig:tm-tracker-completion-summary`; `fig:tm-data-model-er-right`; `tab:tm-sql-fields`.

### Backup 24: Home-states ved afvigelse

**Brug ved spørgsmål om:** hvordan UI håndterer afbrudt eller forsinket træning.
**Synligt:** `fig:tm-ios-home-stale-session`, `fig:tm-ios-home-completion-delay`, `fig:tm-ios-home-next-training`.
**Kort svar i notes:** Home viser ikke kun idealtilstanden. Den kan også vise stale session, completion delay og næste træning efter gennemførelse. Det gør afvigelser synlige uden at gøre dem til fejl.
**Begreber:** stale session, completion delay, fortrydelsesvindue, næste handling.
**Kilder:** de tre Home-figurer; `Docs/DesignDebtScorecard.md`.

### Backup 25: RLS og Edge Functions

**Brug ved spørgsmål om:** sikkerhed, privacy eller privilegerede handlinger.
**Synligt:** sikkerhedsboundary + RLS-matrix.
**Kort svar i notes:** Klienten bruger anon key og bruger-session. Egne data afgrænses med RLS. Privilegerede flows flyttes til Edge Functions, hvor serveren validerer brugeren før service-role eller eksterne secrets bruges.
**Begreber:** RLS, anon key, bearer token, service-role, Edge Function, least privilege.
**Kilder:** Supabase docs; OWASP MASVS; GDPR; `fig:tm-security-boundary-summary`; `tab:tm-rls-matrix`.

### Backup 26: Watch sync

**Brug ved spørgsmål om:** om Apple Watch har samme adgangsmodel.
**Synligt:** `fig:tm-watch-sync-sequence`.
**Kort svar i notes:** Watch er en støtteflade. Den får session payload og arbejder under samme Supabase/RLS-logik, ikke som en alternativ klient med privilegeret adgang.
**Begreber:** WatchConnectivity, session payload, companion app, RLS.
**Kilder:** Apple WatchConnectivity; `fig:tm-watch-sync-sequence`; `WatchAuthSyncPayloadTests`.

### Backup 27: Live Activity og idempotens

**Brug ved spørgsmål om:** dobbeltlogging, retry eller Dynamic Island.
**Synligt:** `fig:tm-live-activity-idempotency-sequence`.
**Kort svar i notes:** Live Activity bruger App Group snapshot og idempotente skriver med `client_action_id`, så gentagne handlinger ikke bør skabe dubletter.
**Begreber:** idempotens, `client_action_id`, App Group, ActivityKit.
**Kilder:** Apple ActivityKit; Apple HIG Live Activities; `fig:tm-live-activity-idempotency-sequence`; `TrackerLiveActivityProjectionTests`.

### Backup 28: Test traceability og quality gate

**Brug ved spørgsmål om:** teknisk evidens og åbne gaps.
**Synligt:** build/test status og gaps i grøn/gul/rød.
**Kort svar i notes:** 556 unit tests og target-builds styrker den centrale tekniske plausibilitet. Gaps ligger især i clean checkout, Supabase/admin integration, watch/Live Activity runtime og Edge Function helper tests.
**Begreber:** unit test, integrationstest, clean checkout, quality gate.
**Kilder:** `verifikationsrapport.md`; `test_traceability_matrix.md`; `quality_gate_review.md`.

### Backup 29: Beta-feedback matrix

**Brug ved spørgsmål om:** brugerindsigt og prioritering.
**Synligt:** B01, B11, B13, B15, B16 med temaer: TestFlight, søgning, katalog, kg/lbs, watch/Live Activity.
**Kort svar i notes:** Feedbacken viser praktisk friktion og modningsbehov. Den bruges som kvalitativ designindsigt, ikke som dokumentation for effekt på motivation eller adherence.
**Begreber:** kvalitativ feedback, iOS-skævhed, designimplikation, convenience sample.
**Kilder:** `feedbackkatalog.md`; `beta_tester_rapport.md`; `tab:tm-beta-feedback`.

### Backup 30: Begrænsninger og næste studie

**Brug ved spørgsmål om:** generaliserbarhed eller effekt.
**Synligt:** begrænsninger -> næste trin: usabilitytest, længere beta, runtime/security test, effektstudie.
**Kort svar i notes:** Projektet dokumenterer design- og implementeringsplausibilitet. Effekt på motivation, adherence eller fysisk aktivitet kræver et senere studie efter UX- og teknisk modning.
**Begreber:** generaliserbarhed, effektstudie, outcome, usabilitytest.
**Kilder:** `diskussion.tex`; `konklusion.tex`; Grundtvig; Clotworthy; Yardley.

### Backup 31: App Store og produktmodenhed

**Brug ved spørgsmål om:** at appen skal videreudvikles og udgives.
**Synligt:** "Bachelorbidrag" vs "release readiness".
**Kort svar i notes:** Bacheloren dokumenterer det faglige og tekniske grundlag. App Store-sporet kræver yderligere runtime-test, privacy review, sikkerhedsreview, bredere brugerafprøvning og endelige release-materialer.
**Begreber:** produktmodenhed, release readiness, privacy review, App Store.
**Kilder:** `quality_gate_review.md`; `Docs/DesignDebtScorecard.md`; `Docs/ParityMatrix.md`; appens `brand.md`.

## Figur- Og Kildevalg

| Hovedslide | Primær visuel | Primære kilder i notes |
| ---: | --- | --- |
| 1 | `fig:tm-ios-home-ready` | Teixeira; Yardley; Eysenbach |
| 2 | problemmodel med plan/faktisk/feedback/næste handling | Autoritativ problemformulering; ACSM; Eysenbach |
| 3 | beskåret `fig:tm-system-context` | Systembeskrivelse; KU-kursusside |
| 4 | evidenstrekant | Metode; PRISMA-S; PRESS; Grundtvig; Clotworthy |
| 5 | 2x2 faglig ramme | Teixeira; Laranjo; Stoyanov; ACSM; Mohammed; OWASP/Supabase |
| 6 | `tab:tm-use-cases`, `tab:tm-krav-traceability` | Use cases; kravtraceability |
| 7 | `fig:tm-tracker-completion-summary`, `fig:tm-data-model-er-middle` | Mohammed; Greig; ACSM |
| 8 | `fig:tm-ios-home-ready`, `fig:tm-ios-home-next-training` | Teixeira; Yardley; Hornbæk |
| 9 | `fig:tm-ios-tracker-active`, `fig:tm-tracker-completion-summary` | Michie; MARS; Mohammed |
| 10 | runtime-udsnit fra tracker/completion | ACSM; Currier; Greig; Larsen |
| 11 | `fig:tm-security-boundary-summary` | Supabase; OWASP; GDPR |
| 12 | `fig:tm-watch-sync-sequence`, `fig:tm-live-activity-idempotency-sequence` | Apple ActivityKit; Apple WatchConnectivity |
| 13 | `tab:tm-test-traceability` | Verifikation; quality gate |
| 14 | `tab:tm-beta-feedback`, `tab:tm-testflight-timeline` | Feedbackkatalog; beta-rapport; Grundtvig; Clotworthy |
| 15 | konklusions-roadmap | Diskussion; konklusion |

## Designnoter

- Brug påstandsoverskrifter, ikke kapiteloverskrifter.
- Hold hovedslides visuelle: ét billede, én model eller én tabeludsnit pr. slide.
- Maksimalt 1-3 callouts på screenshots.
- Hele ER-diagrammer, RLS-matrix og testtabeller hører til backup, ikke hovedflow.
- Kilder skal stå diskret i noter eller nederste hjørne, ikke som tekstblokke på slides.
- Brug samme farvekode i hele decket: blå for brugerhandling, grøn for progression, orange for data, rød/gul for gaps og begrænsninger.

## Timingnoter

Beregningen køres på manusblokkene:

```text
beregnet tid i sekunder = antal ord / 130 * 60
```

Der lægges ekstra pause oveni slides med tunge figurer: 7, 9, 10, 11 og 13. Hvis oplægget bliver for langt under øvning, skal der først skæres i slide 3 og 12, ikke i datamodel, tracker, sikkerhed eller verifikation.
