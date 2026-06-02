# Bacheloreksamen: præsentationsskitse for TræningsMester

Dato: 2026-06-02  
Formål: tekstlig skitse til en 20-minutters bachelorpræsentation med hovedslides, backupslides, talenoter, begreber, kilder og figurvalg. Dette er ikke et færdigt slide deck.

## Grundgreb

Præsentationen skal føles som et mundtligt forsvar af en bacheloropgave, ikke som en produktdemo. Den stærke fortælling er:

> TræningsMester undersøger, hvordan en digital træningsapp kan bevare progression, feedback og næste handling, når brugerens faktiske træning afviger fra den planlagte træning.

Det betyder, at appen skal vises, men kun som evidens for et fagligt argument. Hver hovedslide skal have én påstand i overskriften og et visuelt bevis under. Kilder og mere præcise definitioner ligger i speaker notes, ikke som tunge tekstblokke på slides.

Tidsmodellen er beregnet ved cirka 130 danske ord pr. minut plus korte pauser ved slide- og pointersskift. Den mundtlige ramme på KU er 30 minutter for bachelorprojektet, og planen her antager cirka 20 minutters oplæg med plads til dialog bagefter.

## Researchramme

Web- og formaliaresearch brugt til denne skitse:

- KU-kursussiden for `SITA08010U Bachelorprojekt, sundhed og informatik` angiver 20 ECTS, skriftlig aflevering og mundtligt forsvar på 30 minutter. Bedømmelsen vægter samlet skriftligt og mundtligt arbejde, men det faglige indhold i projektopgaven vægter tungest. For karakteren 12 fremhæves blandt andet afgrænsning, teori/litteratur, analyse, kritisk diskussion, metodeargumentation, konklusion, perspektivering og mundtlig akademisk fremstilling. Kilde: https://kurser.ku.dk/course/SITA08010U/2025-2026
- KU's censornormside angiver for bachelorprojektet i Sundhed og Informatik: skriftlig aflevering, mundtlig prøve, 30 minutter og 20 ECTS. Kilde: https://sund.ku.dk/uddannelse/censor/censornormer-folkesundhed/
- CBS' vejledning om mundtligt forsvar understreger, at eksaminatorerne allerede har læst opgaven. Forsvaret bør derfor ikke være en genfortælling, men en faglig diskussion af særligt interessante aspekter. Kilde: https://teach.cbs.dk/resources/examination-formats/oral-exam-written-product/guidelines-for-oral-defense-of-theses-at-cbs/
- MIT Communication Lab anbefaler en tydelig roadmap, en forståelig narrativ rækkefølge frem for ren kronologi og en høj signal-to-noise ratio. Kilde: https://mitcommlab.mit.edu/be/2026/02/25/defense-season-wrapped-what-makes-a-thesis-defense-great/
- Harvard Catalyst anbefaler assertion-evidence slides: stærke overskrifter med visuel evidens, få bullets, konsistent design og cirka én slide pr. minut. Kilde: https://catalyst.harvard.edu/writing-communication-center/visualize-science/slides/
- UCSD's evidensbaserede slidevejledning anbefaler mindre tekst, stærke billeder, højst få bullets og opmærksomhed på kognitiv belastning. Kilde: https://multimedia.ucsd.edu/best-practices/presentation-design.html
- Concordia anbefaler normalt stikord frem for fulde sætninger i talenoter, fordi fulde sætninger kan friste til oplæsning. Her bruges derfor en hybrid: korte ankre øverst i noten og et fuldt fallback-manus nedenunder. Kilde: https://www.concordia.ca/students/success/learning-support/resources/oral-presentations/presentation-notes.html
- Monash anbefaler simple, relevante, rene slides med ét hovedbudskab, læsbare diagrammer og tydelig forklaring af grafernes relevans. Kilde: https://www.monash.edu/it/current-students/resources-and-support/style-guide/giving-an-oral-presentation

## Tidsfordeling

| Del | Slides | Mål | Ratio | Funktion |
| --- | ---: | ---: | ---: | --- |
| Introduktion og problem | 1-3 | 4:11 | 21% | Gør problemet konkret og viser, hvorfor præsentationen ikke er en produktpitch. |
| Metode og faglig ramme | 4-6 | 4:08 | 21% | Forklarer evidenskæde, evidensniveau og hvilke fagspor appen vurderes ud fra. |
| Analyse og resultater | 7-11 | 7:23 | 37% | Viser datamodel, Home, tracker/completion, sikkerhedsarkitektur og støtteflader. |
| Diskussion og evidensgrænser | 12-13 | 2:58 | 15% | Viser verifikation, brugerindsigt, afvejninger og begrænsninger. |
| Konklusion | 14 | 1:14 | 6% | Svarer direkte på problemformuleringen og åbner for spørgsmål. |
| Samlet mål | 14 hovedslides | 19:54 | 100% | Cirka 20 minutter med naturlige pauser og plads til dialog i en 30-minutters mundtlig prøve. |

## Beregnet timing

Manustiden er beregnet ved cirka 130 ord pr. minut. Den anbefalede slide-tid lægger få sekunder oveni til at pege på figuren, skifte slide og lade de tekniske pointer lande.

| Slide | Ord i manus | Manus alene | Ekstra pause | Anbefalet slide-tid |
| ---: | ---: | ---: | ---: | ---: |
| 1 | 168 | 1:18 | 0:07 | 1:25 |
| 2 | 178 | 1:22 | 0:06 | 1:28 |
| 3 | 159 | 1:13 | 0:05 | 1:18 |
| 4 | 149 | 1:09 | 0:05 | 1:14 |
| 5 | 179 | 1:23 | 0:07 | 1:30 |
| 6 | 170 | 1:18 | 0:06 | 1:24 |
| 7 | 188 | 1:27 | 0:11 | 1:38 |
| 8 | 158 | 1:13 | 0:05 | 1:18 |
| 9 | 197 | 1:31 | 0:12 | 1:43 |
| 10 | 166 | 1:17 | 0:10 | 1:27 |
| 11 | 153 | 1:11 | 0:06 | 1:17 |
| 12 | 175 | 1:21 | 0:11 | 1:32 |
| 13 | 173 | 1:20 | 0:06 | 1:26 |
| 14 | 153 | 1:11 | 0:03 | 1:14 |
| Total | 2366 | 18:12 | 1:42 | 19:54 |

## Praktisk Notestruktur

Hver slide bør have speaker notes i denne rækkefølge:

1. **Ankre**: 3-5 korte stikord, som kan skimmes hurtigt.
2. **Manus**: fuldt fallback-manus i naturligt første person. Brug det ved kulde, men øv det, så det ikke lyder læst.
3. **Begreber**: fagtermer brugt på sliden med korte definitioner.
4. **Kilder og figurer**: citation keys, figurlabels og eventuelle bilag.
5. **Mulige spørgsmål**: 1-2 sandsynlige censor-/vejlederspørgsmål med korte svar.

## Hovedslides

### Slide 1: Når planen møder hverdagen

**Tid:** manus 1:18, anbefalet slide-tid 1:25  
**Synligt på slide:** Titel, undertitel og et stort crop af Home-skærmen med `Dagens træning` og `Start træning`.  
**Visuel:** `fig:tm-ios-home-ready`. Brug appnavn og problemformuleringens nøgleord diskret nederst: programstruktur, progression, feedback, afvigelser.

**Ankre:** plan vs hverdag, næste handling, ikke produktpitch.

```manus
Det centrale problem i min bachelor er ikke, om man kan lave endnu en træningsapp. Problemet er, hvad der sker, når en træningsplan møder en almindelig hverdag. I praksis træner brugeren ikke altid på den rigtige dag, med den rigtige øvelse, med den rigtige vægt eller med fuld logging af alle sæt. Hvis appen kun fungerer, når planen følges perfekt, bliver den svag netop i de situationer, hvor brugeren har brug for overblik. Derfor undersøger jeg TræningsMester som en design- og implementeringscase. Spørgsmålet er, hvordan appen kan bevare retning, progression og feedback, selv når træningen bliver rodet, afbrudt eller ufuldstændigt registreret. Det er den spænding mellem struktur og realistisk adfærd, som hele præsentationen handler om. Jeg starter med Home-skærmen, fordi den gør problemet synligt med det samme: brugeren skal ikke først forstå hele appen, men skal kunne se næste træningshandling. Når jeg peger på knappen "Start træning", er pointen derfor ikke knappen i sig selv, men hele systemet der afgør, hvorfor netop den handling er rigtig nu.
```

**Begreber:**  
Friktion: besvær, ventetid eller ekstra beslutninger, der gør en handling sværere.  
Fleksibel progression: progression der kan fortsætte, selv når faktisk træning afviger fra planen.

**Kilder og evidens:** Teixeira et al. om autonom motivation; Yardley et al. om effektivt digitalt engagement; Eysenbach om frafald; `fig:tm-ios-home-ready`.

**Mulige spørgsmål:**  
Hvorfor starte med Home? Fordi Home er appens mest konkrete svar på brugerens spørgsmål: hvad skal jeg gøre nu?

### Slide 2: Problemformuleringen er et designkrav

**Tid:** manus 1:22, anbefalet slide-tid 1:28  
**Synligt på slide:** Problemformuleringen omskrevet til én stor linje: "Hvordan kan appen håndtere afvigelser uden at tabe progression, feedback eller motivation?" Under den fire små ikoner/kolonner: plan, faktisk træning, feedback, næste handling.  
**Visuel:** enkel model, ikke fuld tekstblok.

**Ankre:** hovedspørgsmål, fire underspørgsmål, sundhed + informatik.

```manus
Min problemformulering spørger, hvordan en digital træningsapp kan designes og implementeres, så programstruktur, progression og feedback understøtter vedvarende motivation og fleksibel håndtering af afvigelser fra et planlagt træningsforløb uden at øge risikoen for demotivation og frafald. Mundtligt kan den koges ned til én faglig test: kan appen skelne mellem planen, det brugeren faktisk gør, og den næste meningsfulde handling? Det er derfor både et sundhedsfagligt og informatikfagligt spørgsmål. Motivation, adherence og frafald forklarer, hvorfor problemet er relevant. Men i min opgave bliver de først konkrete, når de omsættes til dataobjekter, brugerflows, adgangsregler og tests. Derfor behandler jeg problemformuleringen som et designkrav. Appen skal ikke bare vise et program. Den skal kunne håndtere, at programmet møder virkeligheden. De fire underspørgsmål følger samme logik: først modellen for data, så brugerfladen, så sikkerhedsarkitekturen, og til sidst hvordan evidensen faktisk kan vurderes. Det gør også præsentationen lettere at diskutere, fordi hvert svar kan kobles tilbage til ét konkret underspørgsmål. Hvis jeg bliver bedt om at uddybe, kan jeg derfor altid gå tilbage til, hvilken del af hovedspørgsmålet vi taler om.
```

**Begreber:**  
Adherence: vedvarende efterlevelse eller fortsættelse af et træningsforløb.  
Programstruktur: organisering af programmer, træningsdage, øvelser, sæt og progression.  
Analysegenstand: appens håndtering af afvigelser i træningsforløbet.

**Kilder og evidens:** Autoritativ problemformulering; Teixeira et al.; Eysenbach; ACSM; Currier et al.; `problemformulering_og_afgraensning.tex`.

**Mulige spørgsmål:**  
Hvorfor ikke måle effekt? Fordi projektets metode undersøger design- og implementeringsplausibilitet før et senere effektstudie.

### Slide 3: TræningsMester er casen, ikke konklusionen

**Tid:** manus 1:13, anbefalet slide-tid 1:18  
**Synligt på slide:** Appen som case: iOS app, watchOS, Live Activity, Supabase. Brug et roligt systemkort med "caseartefakt" i midten og "ikke effektstudie" som afgrænsning.  
**Visuel:** forenklet system context, ikke hele diagrammet.

**Ankre:** egenudviklet artefakt, afgrænsning, ikke featureliste.

```manus
TræningsMester er den app, jeg har designet og implementeret for at undersøge problemformuleringen. Det er vigtigt, fordi appen ikke er en ekstern case, og den er heller ikke bare et eksempel, der ligger ved siden af teorien. Den er selve artefaktet, som analysen drejer sig om. Men det betyder ikke, at alle features er lige vigtige i eksamen. Appen rummer meget: SwiftUI, Supabase, watchOS, Live Activity, trænerfunktioner, import, social og senere produktspor. Her skal de kun med, når de belyser kerneproblemet. Derfor handler præsentationen ikke om flest mulige funktioner. Den handler om den kæde, hvor plan, faktisk logging, completion, progression, feedback og adgangskontrol hænger sammen. Det er den kæde, der afgør, om appen er fagligt relevant. Hvis jeg bliver spurgt ind til App Store eller videreudvikling, kan jeg tage det i backup, men hovedforsvaret skal blive ved bachelorens undersøgelse. På den måde undgår jeg, at præsentationen bliver en salgspræsentation, selv om appen faktisk er bygget som et rigtigt produkt.
```

**Begreber:**  
Artefakt: det konkrete udviklede produkt, der analyseres.  
Design- og implementeringscase: en case, hvor designvalg og teknisk realisering er det centrale materiale.  
Afgrænsning: præcisering af, hvad projektet undersøger og ikke undersøger.

**Kilder og evidens:** `fig:tm-system-context`; `systembeskrivelse.md`; KU's mål om selvstændig analyse, metodeargumentation og kritisk diskussion.

**Mulige spørgsmål:**  
Hvorfor nævne større appdele, hvis de ikke er hovedproblem? Fordi de viser systemets modenhed, men de skal underordnes bachelorens problem.

### Slide 4: Jeg bruger en evidenskæde, ikke en kronologisk gennemgang

**Tid:** manus 1:09, anbefalet slide-tid 1:14  
**Synligt på slide:** Roadmap som fem trin: problem -> metode -> model -> brugerflow -> evidensgrænse -> konklusion.  
**Visuel:** vandret roadmap med markør for "vi er her" ved hver sektion.

**Ankre:** ikke kapitelreferat, vurderingskæde, KU-kriterier.

```manus
Jeg gennemgår ikke rapporten kapitel for kapitel. Eksaminator og censor har allerede læst opgaven, så den mundtlige præsentation skal vise dømmekraft: hvad er det vigtigste, hvad bærer evidensen, og hvor går grænsen for mine claims? Strukturen er derfor en evidenskæde i stedet for en kronologisk fortælling. Først fastlægger jeg problemet og metoden. Derefter viser jeg den centrale model for plan, trackerlog, completion og næste handling. Så viser jeg, hvordan modellen kan ses i brugerflowet, og hvordan den understøttes af sikkerhedsarkitekturen. Til sidst diskuterer jeg verifikation, brugerindsigt og begrænsninger. Det følger KU's fokus på afgrænsning, metode, analyse, kritisk diskussion og perspektivering. Målet er, at hver slide skal hjælpe diskussionen videre. Jeg bruger derfor roadmapet som en måde at holde censor og vejleder orienteret i argumentet, ikke som pynt eller en indholdsfortegnelse. Når roadmapet vender tilbage i konklusionen, viser det også, at præsentationen faktisk har besvaret de dele, den lovede.
```

**Begreber:**  
Evidenskæde: sammenhæng mellem problem, metode, materiale, analyse og konklusion.  
Claim: en faglig påstand, som skal bæres af passende evidens.

**Kilder og evidens:** KU-kursusside; CBS oral defense guideline; MIT Communication Lab om roadmap og signal-to-noise.

**Mulige spørgsmål:**  
Hvorfor ikke vise alt? Fordi eksamen belønner faglig prioritering og kritisk afgrænsning mere end total funktionsgennemgang.

### Slide 5: Metoden viser plausibilitet, ikke effekt

**Tid:** manus 1:23, anbefalet slide-tid 1:30  
**Synligt på slide:** Tre evidenstyper i en trekant: artefakter, anonymiseret beta-feedback, teknisk verifikation. Nederst: "Effekt kræver senere studie."  
**Visuel:** trekant eller evidensmatrix.

**Ankre:** designcase, scoping-søgning, artefaktanalyse, beta, tests.

```manus
Metodisk behandler jeg TræningsMester som en design- og implementeringscase. Det betyder, at jeg ikke måler, om appen øger fysisk aktivitet eller fastholder brugere over tid. Det ville kræve et andet undersøgelsesdesign, flere brugere, længere observation og klare outcome-mål. I stedet vurderer jeg, om der er en fagligt begrundet og teknisk dokumenteret sammenhæng mellem problem, designvalg og implementering. Materialet består af en problemstyret kildesøgning, kursus- og faggrundlag, appens synlige artefakter, anonymiseret beta-feedback og teknisk verifikation. Det vigtigste er at bruge materialerne korrekt. Screenshots kan vise, at et flow er designet. Tests kan styrke teknisk plausibilitet. Feedback kan pege på friktion. Men ingen af delene kan alene dokumentere langtidseffekt. Den grænse er en del af metoden, ikke en svaghed jeg forsøger at skjule. Det er også derfor, jeg bruger ord som plausibilitet, designindsigt og verifikation i stedet for at tale om dokumenteret effekt. Metoden passer altså til spørgsmålet "hvordan kan det designes og implementeres?", ikke til spørgsmålet "hvor stor effekt har det?" Det er præcis den skelnen, jeg vil holde fast i, hvis diskussionen går mod brugeradfærd og outcome.
```

**Begreber:**  
Design- og implementeringsplausibilitet: at løsningen er fagligt og teknisk sandsynliggjort, men ikke effektmålt.  
Artefaktanalyse: analyse af konkrete appskærme, diagrammer, krav, tests og implementeringsspor.  
Scoping-søgning: bred, problemstyret litteratursøgning uden at være et fuldt systematisk review.

**Kilder og evidens:** Rethlefsen et al. PRISMA-S; McGowan et al. PRESS; `metode.tex`; `kildesoegning.tex`; `tab:analysestrategi`.

**Mulige spørgsmål:**  
Er beta-feedback så nok? Ja til designindsigt og friktionstemaer, nej til generaliserbar effekt.

### Slide 6: Fire faglige spor styrer vurderingen

**Tid:** manus 1:18, anbefalet slide-tid 1:24  
**Synligt på slide:** Fire kvadranter: motivation/adherence, appkvalitet/trackers, progression/autoregulering, interaktionsdesign/data/sikkerhed. I midten: "Næste meningsfulde handling."  
**Visuel:** 2x2 model.

**Ankre:** motivation, appkvalitet, progression, data/sikkerhed.

```manus
Den faglige ramme er bygget op af fire spor. Først motivation, frafald og effektivt engagement: appbrug er kun værdifuld, hvis den faktisk støtter den ønskede adfærd. Dernæst app- og trackerevidens samt appkvalitet: digitale værktøjer kan støtte fysisk aktivitet, men effekten afhænger af design, brugskontekst og kvalitet. Det tredje spor er styrketræningsprogression og autoregulering, fordi styrketræning kræver mere end en kalender. Belastning, volumen, øvelsesvalg og dagsform betyder noget. Det fjerde spor er interaktionsdesign, datakvalitet og sikkerhed. Her handler det om, om brugeren kan handle hurtigt, og om data samtidig er meningsfulde og beskyttede. Min vurdering samler de spor i ét praktisk spørgsmål: får brugeren en næste handling, der både er fagligt meningsfuld, forståelig i appen og datamæssigt ansvarlig? Hvis et designvalg kun er motiverende, men ikke sikkert, er det ikke nok. Hvis det kun er teknisk sikkert, men ubrugeligt i træning, er det heller ikke nok. Det er netop kombinationen, der gør casen sundhedsinformatisk. På sliden skal modellen derfor ikke ligne fire separate teorier, men fire krav til samme apphandling.
```

**Begreber:**  
Effektivt engagement: brug der faktisk støtter mål-adfærd, ikke bare meget skærmtid.  
Autoregulering: justering af træning efter performance, dagsform eller fatigue.  
Datakvalitet: om data er gode nok til deres konkrete formål.

**Kilder og evidens:** Teixeira et al.; Yardley et al.; Laranjo et al.; Romeo et al.; Brickwood et al.; Stoyanov MARS; ACSM; Currier et al.; Greig et al.; Mohammed et al.; OWASP MASVS; Supabase RLS docs.

**Mulige spørgsmål:**  
Hvilket spor er vigtigst? Kombinationen. Appen fejler, hvis den kun er motiverende, kun træningsfaglig eller kun teknisk.

### Slide 7: Fleksibel progression kræver adskilte dataobjekter

**Tid:** manus 1:27, anbefalet slide-tid 1:38  
**Synligt på slide:** Forenklet datakæde: planlagt workout -> trackerlog -> completion-event -> cycle runtime -> næste handling.  
**Visuel:** brug `fig:tm-tracker-completion-summary`, men beskær/omtegn så kun de fem kerneobjekter står tilbage.

**Ankre:** plan, log, completion, runtime, næste handling.

```manus
Det vigtigste implementeringsvalg er adskillelsen mellem planlagt træning, faktisk logging, completion og progression. En plan beskriver intentionen: hvilke øvelser, sæt og mål der er tænkt. En trackerlog beskriver det, brugeren faktisk registrerer under træningen. Et completion-event beskriver, at et træningspas er gennemført, også hvis alle sæt ikke blev logget. Cycle runtime bruger derefter gennemførelsen til at afgøre næste relevante træning. Den adskillelse gør afvigelser håndterbare. Hvis alt blev presset ind i ét kalenderindeks, ville systemet have svært ved at skelne mellem et planlagt pas, et delvist logget pas og et gennemført pas uden detaljer. Det er her appen bliver mere end en logbog. En logbog gemmer, hvad der skete. TræningsMester skal også kunne bruge det, der skete, til at foreslå næste meningsfulde handling. Samtidig gør adskillelsen det lettere at være ærlig om datakvalitet: detaljeret log og simpel completion kan begge være nyttige, men til forskellige formål. Den pointe er vigtig, fordi løsningen ikke er maksimal registrering. Løsningen er passende registrering til den beslutning, appen skal støtte. På sliden skal pilene derfor læses som et argument: dataobjekterne gør det muligt at komme fra afvigelse til næste handling.
```

**Begreber:**  
Trackerlog: detaljeret log over sæt, reps, vægt eller varighed.  
Completion-event: registrering af, at et træningspas er gennemført.  
Cycle runtime: den aktive cyklustilstand, der afgør næste workout efter faktisk gennemførelse.  
Datagranularitet: hvor detaljerede data er.

**Kilder og evidens:** `fig:tm-tracker-completion-summary`; `fig:tm-data-model-er-middle`; `tab:tm-sql-fields`; ACSM; Greig et al.; Larsen et al.; Mohammed et al.

**Mulige spørgsmål:**  
Mister man ikke data ved completion uden trackerlog? Jo, man mister detaljer, men bevarer kontinuitet og næste handling. Det er en bevidst afvejning.

### Slide 8: Home gør næste handling synlig

**Tid:** manus 1:13, anbefalet slide-tid 1:18  
**Synligt på slide:** To screenshots side om side: Home før træning og Home efter progression. Brug få callouts: "Dag 1 af 3", "Start træning", "Dag 2 af 3".  
**Visuel:** `fig:tm-ios-home-ready` og `fig:tm-ios-home-next-training`.

**Ankre:** status, overblik, ikke skælde ud, næste handling.

```manus
Home-skærmen er ikke bare forsiden. Den er appens næste-handling-flade. På den første tilstand kan brugeren se dagens træning og starte uden at rekonstruere hele programmet. Efter completion viser Home, at næste træning er rykket frem. Det er et lille visuelt flow, men det bærer en stor del af argumentet. Brugeren skal ikke mødes af en lang forklaring af hele systemet eller en negativ besked om alt det, der ikke blev logget perfekt. Brugeren skal kunne se: jeg er stadig i forløbet, og dette er næste skridt. Det er også her motivationsteorien bliver konkret. Feedbacken skal støtte oplevet kompetence og fortsættelse, ikke gøre afvigelsen til et nederlag. Samtidig skal appen stadig kunne skelne mellem detaljeret logging og mere simpel completion. Derfor er Home både et interaktionsdesignvalg og et dataflow-resultat: skærmen kan kun være enkel, fordi modellen bagved har styr på tilstanden. Det er derfor, jeg ville vise to screenshots her i stedet for mange bullets.
```

**Begreber:**  
Næste-handling-flade: en skærm, der tydeligt viser den næste sikre handling.  
Oplevet kompetence: brugerens oplevelse af at kunne mestre handlingen.

**Kilder og evidens:** `fig:tm-ios-home-ready`; `fig:tm-ios-home-next-training`; Teixeira et al.; Yardley et al.; Hornbæk om kontekst og evaluering.

**Mulige spørgsmål:**  
Hvorfor ikke vise flere Home-states? Backupslide viser stale session og completion delay.

### Slide 9: Tracker-on og tracker-off er et bevidst tradeoff

**Tid:** manus 1:31, anbefalet slide-tid 1:43  
**Synligt på slide:** Aktiv tracker screenshot til venstre, tracker/completion-flow til højre. Overskrift: "Mere detaljer er ikke altid bedre i situationen."  
**Visuel:** `fig:tm-ios-tracker-active` + forenklet flow fra `fig:tm-tracker-completion-summary`.

**Ankre:** detaljer vs friktion, selvmonitorering, completion som lav-friktionsflow.

```manus
Trackerflowet er der, hvor problemformuleringen bliver mest konkret. Når tracker er slået til, kan brugeren logge sæt, reps, vægt og pauser, og det giver et stærkere datagrundlag for historik, feedback og senere progression. Men under træning kan detaljeret logging også skabe friktion. Brugeren står måske mellem sæt, skifter udstyr, har svedige hænder eller bliver afbrudt. Derfor er tracker-off ikke en undskyldning for manglende data, men et bevidst lav-friktionsflow. Appen kan markere træningen som gennemført, bevare historik og flytte progressionen videre, selv om datagranulariteten er lavere. Det er den centrale afvejning: højere præcision, når brugeren logger detaljer, men stadig kontinuitet, når det realistiske valg er at afslutte uden fuld sætlog. Et godt system skal kunne navngive den forskel i stedet for at lade den blive skjult. Hvis censor spørger kritisk, er mit svar derfor ikke, at tracker-off er lige så præcist. Svaret er, at det er mere brugbart i bestemte situationer og tydeligt svagere til detaljeret analyse. Det er også derfor, tracker-off skal forklares i UI'et og ikke bare være en skjult genvej. Her vil jeg pege på tracker-skærmen og flowdiagrammet samtidig: den ene viser brugerens arbejdssituation, den anden viser systemets datalogik.
```

**Begreber:**  
Selvmonitorering: brugerens registrering af egen adfærd eller performance.  
Lav friktion: lavt betjeningsbesvær i selve træningssituationen.  
Tradeoff: en faglig afvejning, hvor én kvalitet styrkes på bekostning af en anden.

**Kilder og evidens:** Michie BCT Taxonomy; MARS; ACSM; `fig:tm-ios-tracker-active`; `fig:tm-tracker-completion-summary`; `tab:tm-tracker-flow-bpmn`.

**Mulige spørgsmål:**  
Er tracker-off ikke bare mindre kvalitet? Det er mindre detaljeret data, men højere sandsynlighed for, at systemet stadig kan støtte næste handling.

### Slide 10: Fleksibiliteten skal have en sikkerhedsgrænse

**Tid:** manus 1:17, anbefalet slide-tid 1:27  
**Synligt på slide:** Forenklet sikkerhedsdiagram: klient -> anon session -> RLS/RPC -> database; klient -> Edge Function -> servervalidering -> service-role kun server-side.  
**Visuel:** `fig:tm-security-boundary-summary`.

**Ankre:** klient starter, backend afgør, RLS, Edge Functions, least privilege.

```manus
Fleksibilitet er kun forsvarlig, hvis adgangskontrollen følger med. I TræningsMester starter klienten handlingen, men backend afgør adgangen. Appen bruger kun Supabase anon key og en bruger-session. Almindelige læse- og skrivehandlinger går gennem RLS, hvor `auth.uid()` og relationer afgør, hvilke rækker brugeren må se eller ændre. Privilegerede flows som admin, træner-klient, import og AI går gennem Edge Functions, hvor brugerens token valideres før service-role eller eksterne secrets bruges server-side. Det er vigtigt, fordi appen arbejder med personlige træningsdata, profiltilstande og potentielle trænerrelationer. Hvis klienten selv var sikkerhedsautoritet, kunne en UI-fejl blive til bredere dataadgang. Her er pointen, at lav friktion i brugerfladen ikke behøver at betyde brede rettigheder i klienten. Fleksibiliteten skal have en backendgrænse. Det gør også sikkerhed til en del af sundhedsinformatikken i projektet, ikke bare et teknisk efterord. I den mundtlige diskussion vil jeg derfor skelne mellem sikkerhedsdesign, delvis verifikation og egentlig sikkerhedscertificering. Den konkrete formulering er: sikkerhedsmodellen er designet og dokumenteret, men ikke fuldt certificeret eller penetrationstestet.
```

**Begreber:**  
RLS: Row Level Security, databasepolitikker der begrænser adgang på rækkeniveau.  
Anon key: klient-sikker Supabase-nøgle, som først får brugeradgang sammen med auth-session.  
Edge Function: server-side funktion til privilegeret eller ekstern logik.  
Least privilege: princippet om mindst nødvendige rettigheder.

**Kilder og evidens:** Supabase RLS docs; Supabase API security docs; OWASP MASVS; GDPR; `fig:tm-security-boundary-summary`; `tab:tm-rls-matrix`.

**Mulige spørgsmål:**  
Er sikkerheden bevist? Nej. Den er stærkt design- og dokumentationsunderbygget, men fuld sikkerhedsverifikation kræver flere integrationstests.

### Slide 11: Watch og Live Activity er støtteflader, ikke hovedbeviset

**Tid:** manus 1:11, anbefalet slide-tid 1:17  
**Synligt på slide:** To små diagrammer: watch sync og Live Activity idempotency. Overskrift: "Samme session, samme model, mindre telefonfriktion."  
**Visuel:** `fig:tm-watch-sync-sequence` og `fig:tm-live-activity-idempotency-sequence`.

**Ankre:** støtteflader, samme session, idempotens, evidensgrænse.

```manus
watchOS og Live Activity er vigtige, fordi de kan reducere telefonfriktion under træning. Hvis brugeren kan se status, pause eller næste sæt uden at åbne appen fuldt, passer det godt til en træningssituation. Men i bacheloren skal de placeres rigtigt. De er støtteflader til den samme træningsmodel, ikke separate hovedresultater. Watch får en bruger-session og arbejder under samme RLS-model som iOS. Live Activity bruger App Group snapshot og idempotente writes med `client_action_id`, så gentagne handlinger ikke bør skabe dobbeltlogging. Det viser, at støttefladerne er tænkt ind i arkitekturen. Evidensen er dog primært build, tests og diagrammer. Der mangler runtime-screenshots for watchOS og Dynamic Island, så jeg bruger dem som dokumenteret designretning, ikke som fuldt produktionsbevis. Det er en vigtig nuance: de styrker argumentet om lav friktion, men de bærer ikke alene konklusionen. Hvis der spørges ind til dem, vil jeg derfor gå til backupslides med sync- og idempotenssekvenserne.
```

**Begreber:**  
Idempotens: samme handling kan gentages uden at skabe dubletter.  
App Group snapshot: delt lokal state mellem app og extension.  
Runtime: faktisk kørsel i brug, ikke kun build.

**Kilder og evidens:** Apple ActivityKit; Apple HIG Live Activities; Apple Watch Connectivity; `fig:tm-watch-sync-sequence`; `fig:tm-live-activity-idempotency-sequence`; `TrackerLiveActivityProjectionTests`.

**Mulige spørgsmål:**  
Hvorfor ikke udelade watch/Live Activity? Fordi de er relevante for lav friktion, men de skal afgrænses ærligt.

### Slide 12: Verifikationen viser fungerende struktur og tydelige gaps

**Tid:** manus 1:21, anbefalet slide-tid 1:32  
**Synligt på slide:** Test traceability tabel i tre farver: bestået, delvist, mangler. Brug kun 5-6 rækker: iOS build, 556 unit tests, integration, watch build, Live Activity build, RLS/security model.  
**Visuel:** `tab:tm-test-traceability`, stærkt beskåret.

**Ankre:** 556 tests, build, delvis integration, gaps som styrke.

```manus
Verifikationen skal bruges præcist. Den stærke del er, at iOS-klienten kunne bygges, watchOS-targetet kunne bygges, Live Activity-targetet kunne bygges, og der var 556 unit tests uden failures. Det er især relevant for domænelogik, payloads, tracker, completion, cycle runtime og Live Activity-projection. Den svagere del er integration og drift. Nogle Supabase admin- og non-admin tests blev sprunget over, fordi de rigtige testcredentials manglede. Edge Function helper tests blev ikke kørt, fordi Deno ikke var tilgængelig. Verifikationen var også fra en lokal freeze-state, ikke en ren reproducerbar CI-checkout. Min konklusion bliver derfor ikke, at appen er produktionscertificeret eller sikkerhedsbevist i fuld bredde. Konklusionen er mere præcis: den centrale tekniske struktur er plausibel, implementeret og delvist verificeret, men videre drift kræver stærkere test. Den præcision er vigtig, fordi teknisk dokumentation ellers let bliver enten under- eller oversolgt. Jeg vil hellere være skarp på, hvad der er vist, end bred på noget, materialet ikke kan bære. På selve sliden skal grønne og gule statusfelter derfor være lige tydelige, så begrænsningerne ikke gemmes.
```

**Begreber:**  
Unit test: afgrænset test af en lille del af systemets logik.  
Integrationstest: test af om flere systemdele virker sammen.  
Clean checkout: reproducerbar test fra en ren kodebase uden lokale ændringer.  
Verifikationsgrænse: hvad testene kan og ikke kan dokumentere.

**Kilder og evidens:** `verifikationsrapport.md`; `test_traceability_matrix.md`; `quality_gate_review.md`; `tab:tm-test-traceability`.

**Mulige spørgsmål:**  
Hvorfor nævne gaps på hovedslide? Fordi kritisk afgrænsning er et bedømmelseskriterium og gør claims troværdige.

### Slide 13: Brugerindsigten peger på friktion før effektmåling

**Tid:** manus 1:20, anbefalet slide-tid 1:26  
**Synligt på slide:** Tre grupper af feedback: installation/TestFlight, katalog/søgning/enheder, støtteflader/watch/Live Activity. Nederst: "Designinput, ikke effektbevis."  
**Visuel:** `tab:tm-beta-feedback` + `tab:tm-testflight-timeline`, stærkt kondenseret.

**Ankre:** kvalitativ feedback, iOS-bias, katalog, kg/lbs, watch, næste testtrin.

```manus
Betaindsigten giver et godt korrektiv til den tekniske implementering. Den viser, at friktion ikke kun ligger inde i trackerflowet. Den kan også ligge i TestFlight, installation, søgning, katalogkvalitet, øvelsesmedier, enheder som kg og lbs og robustheden i støtteflader. Det er vigtigt, fordi brugeren møder appen som en samlet oplevelse. En god datamodel hjælper ikke nok, hvis brugeren ikke kan finde øvelsen eller ikke forstår, hvilken build der skal installeres. Derfor bruger jeg feedbacken som kvalitativ designindsigt. Den siger noget om, hvor appen skal modnes, før en større evaluering giver mening. Den siger ikke, at appen forbedrer motivation eller adherence. Det næste rigtige skridt er derfor systematisk usabilitytest, længere og bredere beta samt stærkere runtime- og sikkerhedstests. På den måde bliver brugerindsigten ikke pynt i rapporten, men en prioritering af, hvad der skal løses før effektmåling. Det viser også, at appens kvalitet ikke kun handler om kode, men om hele vejen ind i træningssituationen. Hvis jeg får spørgsmål om generaliserbarhed, er svaret, at feedbacken er tematisk og begrænset, men stadig fagligt relevant som designinput.
```

**Begreber:**  
Kvalitativ designindsigt: brugerobservationer der peger på problemer, behov og prioriteringer.  
iOS-bias: skævhed fordi betaen primært dækker iOS-brugere.  
Usabilitytest: systematisk test af om brugere forstår og kan gennemføre centrale handlinger.

**Kilder og evidens:** `feedbackkatalog.md`; `beta_tester_rapport.md`; `testflight_tidslinje.md`; Eysenbach; Yardley; Grundtvig; Clotworthy.

**Mulige spørgsmål:**  
Hvorfor ikke lave effektstudie nu? Fordi umoden friktion ville blande interventionens potentiale sammen med beta- og brugeroplevelsesproblemer.

### Slide 14: Konklusionen er, at fleksibilitet er en systemegenskab

**Tid:** manus 1:11, anbefalet slide-tid 1:14  
**Synligt på slide:** Fire korte linjer: "Adskil plan og handling", "Gør næste handling tydelig", "Lad backend håndhæve adgang", "Test effekten senere".  
**Visuel:** gentag roadmap fra slide 4, nu med svar udfyldt.

**Ankre:** direkte svar, fire underspørgsmål, næste skridt.

```manus
Mit svar på problemformuleringen er, at fleksibel progression kræver en tydelig adskillelse mellem planlagt træning, faktisk logging, completion, feedback og næste handling. TræningsMester viser en plausibel design- og implementeringsmodel for den adskillelse. Home og tracker gør næste handling forståelig. Completion-events bevarer kontinuitet uden perfekt logging. Cycle runtime kan flytte progressionen videre. RLS og Edge Functions holder adgangskontrollen uden for klienten. Den samlede pointe er, at fleksibilitet ikke ligger i én knap eller én skærm. Det er en systemegenskab, hvor brugerflade, datamodel, arkitektur og verifikation skal passe sammen. Samtidig er evidensen afgrænset. Projektet dokumenterer ikke effekt på motivation eller adherence. Det dokumenterer et systemdesign, som er klarere at teste videre. Det er også mit vigtigste faglige bidrag: at vise, hvordan en realistisk træningsafvigelse kan behandles som en normal systemtilstand frem for en fejl. Herfra giver det mening at åbne for spørgsmål, fordi backupslides kan uddybe både metode, sikkerhed, tests og brugerindsigt.
```

**Begreber:**  
Systemegenskab: en kvalitet der opstår gennem samspil mellem UI, data, arkitektur og test, ikke i én funktion alene.  
Perspektivering: næste faglige skridt efter projektets afgrænsede fund.

**Kilder og evidens:** `konklusion.tex`; `diskussion.tex`; hele evidenskæden.

**Mulige spørgsmål:**  
Hvad er det vigtigste bidrag? En dokumenteret model for at gøre realistiske afvigelser håndterbare uden at miste retning, historik eller adgangskontrol.

## Backupslides

Backupslides skal ligge efter konklusionen. De skal ikke gennemgås i oplægget, men være klar, hvis censor beder om dokumentation eller vil gå dybere i et punkt.

### Backup 15: Fuld problemformulering og underspørgsmål

**Brug hvis:** censor vil se den præcise formulering eller spørger, hvorfor præsentationen er afgrænset.  
**Synligt:** fuld problemformulering + fire underspørgsmål.  
**Kort svar:** Problemformuleringen styrer hele strukturen. De fire underspørgsmål oversætter den til datamodel, UI/friktion, sikker arkitektur og evidensgrundlag.  
**Begreber:** problemformulering, underspørgsmål, afgrænsning.  
**Kilder:** `problemformulering_og_afgraensning.tex`; `problemformulering_autoritativ.md`.

### Backup 16: Bedømmelseskriterier fra KU

**Brug hvis:** der spørges til, hvorfor præsentationen lægger vægt på metode og kritisk afgrænsning.  
**Synligt:** 12-kriterier kondenseret til: afgrænsning, teori/state of the art, analyse, metodeargument, kritisk diskussion, konklusion/perspektivering, mundtlig fremstilling.  
**Kort svar:** Jeg har bygget præsentationen efter KU's læringsmål, så jeg viser selvstændig analyse og kritisk diskussion frem for en lineær funktionsdemo.  
**Begreber:** bedømmelseskriterier, ekstern censur, samlet vurdering.  
**Kilder:** KU-kursusside; KU-censornormside.

### Backup 17: Kildekort for teorien

**Brug hvis:** der spørges til litteraturvalg eller state of the art.  
**Synligt:** fire kildespor med 3-5 citation keys pr. spor.  
**Kort svar:** Motivation/adherence dækker hvorfor friktion og feedback betyder noget. App-/trackerlitteratur dækker digital støtte og appkvalitet. Træningslitteratur dækker progression/autoregulering. Tekniske kilder dækker datakvalitet, RLS, platform og privacy.  
**Begreber:** state of the art, scoping-søgning, kildekritik.  
**Kilder:** `referencer.md`; `kildesoegning.tex`.

### Backup 18: Analysestrategi

**Brug hvis:** der spørges til metode eller hvorfor materialerne er tilstrækkelige.  
**Synligt:** `tab:analysestrategi` kondenseret.  
**Kort svar:** Hvert underspørgsmål har sit eget materiale og sit eget vurderingskriterium. Det forhindrer, at screenshots bruges som effektbevis eller at tests bruges som brugeraccept.  
**Begreber:** artefaktanalyse, plausibilitet, triangulering.  
**Kilder:** `metode.tex`; `tab:analysestrategi`.

### Backup 19: Use cases og kravsporbarhed

**Brug hvis:** der spørges, om appen faktisk understøtter problemformuleringen.  
**Synligt:** UC-06, UC-08, UC-07 og F-08/F-09/F-13/F-15.  
**Kort svar:** Kerneflowet er sporbar fra problem til krav og implementering: tracker, completion, cycle runtime, watch og Live Activity. Støttefeatures som admin/import er sekundære i bacheloren.  
**Begreber:** use case, funktionelt krav, ikke-funktionelt krav, traceability.  
**Kilder:** `use_cases.md`; `krav_traceability.md`; `tab:tm-use-cases`; `tab:tm-krav-traceability`.

### Backup 20: Datamodel for plan, log og completion

**Brug hvis:** der spørges teknisk ind til plan vs faktisk træning.  
**Synligt:** ER-udsnit for `plan`, `workout`, `workout_exercises`, `trackerlog`, `workout_completion_events`, `training_cycle_runtime`.  
**Kort svar:** Planen beskriver intentionen, trackerlog beskriver detaljeret udførelse, completion beskriver gennemførelse, og cycle runtime forbinder completion med næste træning.  
**Begreber:** datamodel, datagranularitet, completion-event, cycle runtime.  
**Kilder:** `fig:tm-data-model-er-middle`; `tab:tm-sql-domain-overblik`; `tab:tm-sql-fields`.

### Backup 21: Tracker-off og datakvalitet

**Brug hvis:** der spørges kritisk til datatab.  
**Synligt:** sammenligningstabel: tracker-on vs tracker-off.  
**Kort svar:** Tracker-on giver bedre detaljeret analyse. Tracker-off giver lavere datagranularitet, men bevarer kontinuitet og næste handling. Datakvalitet vurderes efter formål, ikke efter maksimal mængde data.  
**Begreber:** datakvalitet, datagranularitet, formålsbestemt data, tradeoff.  
**Kilder:** Mohammed et al.; `fig:tm-tracker-completion-summary`; `data_sikkerhed_og_interoperabilitet.tex`.

### Backup 22: RLS og Edge Functions

**Brug hvis:** der spørges til sikkerhed eller privacy.  
**Synligt:** sikkerhedsboundary + RLS-matrix.  
**Kort svar:** Klienten bruger anon key og user session. Egne data beskyttes med RLS. Privilegerede flows flyttes til Edge Functions, hvor serveren validerer brugeren før service-role eller eksterne secrets bruges.  
**Begreber:** RLS, anon key, bearer token, service-role, Edge Function.  
**Kilder:** Supabase docs; OWASP MASVS; GDPR; `fig:tm-security-boundary-summary`; `tab:tm-rls-matrix`.

### Backup 23: Live Activity og idempotens

**Brug hvis:** der spørges til race conditions, dobbeltlogging eller Dynamic Island.  
**Synligt:** Live Activity sequence.  
**Kort svar:** Live Activity læser et App Group snapshot, laver intent write med brugerens auth-session og bruger `client_action_id` til idempotens. Det skal forhindre dubletter ved retry eller dobbelttryk.  
**Begreber:** idempotens, client_action_id, App Group, ActivityKit.  
**Kilder:** Apple ActivityKit; `fig:tm-live-activity-idempotency-sequence`; `TrackerLiveActivityProjectionTests`.

### Backup 24: Watch sync

**Brug hvis:** der spørges, om Apple Watch har samme adgangsmodel.  
**Synligt:** watch sync sequence.  
**Kort svar:** Watch får ikke service-role. Det får et session payload og bruger samme Supabase/RLS-model som iOS. Det gør watch til en lav-friktionsflade, ikke en alternativ datakilde uden sikkerhedsgrænse.  
**Begreber:** WatchConnectivity, session payload, RLS, companion app.  
**Kilder:** Apple WatchConnectivity; `fig:tm-watch-sync-sequence`; `WatchAuthSyncPayloadTests`.

### Backup 25: Beta-feedback matrix

**Brug hvis:** der spørges til brugerindsigt eller designprioriteringer.  
**Synligt:** B01, B11, B13, B15, B16 og designimplikationer.  
**Kort svar:** Feedbacken pegede især på Live Activity, TestFlight-friktion, katalog/søgning, kg/lbs og watch. Det er designinput, ikke effektbevis.  
**Begreber:** kvalitativ feedback, iOS-bias, convenience sample, designimplikation.  
**Kilder:** `feedbackkatalog.md`; `beta_tester_rapport.md`; `tab:tm-beta-feedback`.

### Backup 26: Test traceability og quality gate

**Brug hvis:** der spørges til teknisk evidens.  
**Synligt:** build/test status og gaps.  
**Kort svar:** 556 unit tests og target-builds giver stærk teknisk plausibilitet for centrale flows. Gaps ligger i clean checkout, bredere integrationstest, watch/Live Activity runtime og Edge Function helper tests.  
**Begreber:** unit test, integrationstest, clean checkout, quality gate.  
**Kilder:** `verifikationsrapport.md`; `test_traceability_matrix.md`; `quality_gate_review.md`.

### Backup 27: Plan for næste studie

**Brug hvis:** der spørges, hvad der skulle til for at dokumentere effekt.  
**Synligt:** tre trin: usabilitytest -> længere beta -> effektstudie.  
**Kort svar:** Først bør centrale flows testes systematisk med realistiske opgaver. Derefter bør betaen udvides med bredere brugere og længere tid. Først derefter giver et egentligt effektstudie på motivation/adherence mening.  
**Begreber:** usabilitytest, længere beta, effektstudie, outcome.  
**Kilder:** `diskussion.tex`; `konklusion.tex`; metodekilder om validitet og generaliserbarhed.

### Backup 28: App Store og produktperspektiv

**Brug hvis:** der spørges til, at appen skal videreudvikles og ud på App Store.  
**Synligt:** "Bachelorbidrag" vs "produktroadmap".  
**Kort svar:** Bacheloren dokumenterer det faglige og tekniske grundlag. App Store-sporet kræver yderligere runtime-test, privacy review, sikkerhedsreview, bredere brugertest og endelige App Store-/databeskyttelsesmaterialer.  
**Begreber:** produktmodenhed, release readiness, privacy review, App Store.  
**Kilder:** `quality_gate_review.md`; appens `brand.md`; `Docs/DesignDebtScorecard.md`.

## Slidekilder og figurvalg

| Slide | Primære figurer | Primære kilder i noter |
| ---: | --- | --- |
| 1 | `fig:tm-ios-home-ready` | Teixeira; Yardley; Eysenbach |
| 2 | enkel problemformuleringsmodel | Autoritativ problemformulering; ACSM; Eysenbach |
| 3 | forenklet `fig:tm-system-context` | Systembeskrivelse; KU-mål |
| 4 | roadmap | KU-kursusside; CBS; MIT |
| 5 | evidenstrekant | Metode; PRISMA-S; PRESS |
| 6 | fire faglige spor | Teixeira; Laranjo; Stoyanov; ACSM; Supabase/OWASP |
| 7 | `fig:tm-tracker-completion-summary` | ACSM; Greig; Mohammed |
| 8 | `fig:tm-ios-home-ready`, `fig:tm-ios-home-next-training` | Teixeira; Yardley; Hornbæk |
| 9 | `fig:tm-ios-tracker-active`, `fig:tm-tracker-completion-summary` | Michie BCT; MARS; datakvalitet |
| 10 | `fig:tm-security-boundary-summary` | Supabase RLS/API docs; OWASP; GDPR |
| 11 | `fig:tm-watch-sync-sequence`, `fig:tm-live-activity-idempotency-sequence` | Apple ActivityKit/HIG/WatchConnectivity |
| 12 | `tab:tm-test-traceability` | Verifikationsrapport; quality gate |
| 13 | `tab:tm-beta-feedback`, `tab:tm-testflight-timeline` | Feedbackkatalog; beta-rapport; metodeetik |
| 14 | roadmap gentaget | Konklusion; diskussion |

## Designnoter til de faktiske slides

- Brug mørk, rolig TræningsMester-stil med neutral baggrund og brand-blå accent, men undgå at gøre præsentationen til marketing.
- Hovedoverskrifter skal være påstandsoverskrifter, fx "Fleksibel progression kræver adskilte dataobjekter", ikke neutrale kapiteloverskrifter som "Datamodel".
- Brug screenshots som reelle beviser. Giv dem plads, og tilføj kun 1-3 callouts.
- Brug ikke hele ER-diagrammet i hoveddeck, medmindre det beskæres. Hele diagrammet hører til backup.
- Kilder bør ikke stå som lange citationer på slides. Brug små kildehenvisninger i nederste hjørne eller i speaker notes.
- Backupslides må gerne være tekniske og tætte, fordi de kun bruges ved spørgsmål.

## Timingnoter

Når manus lægges ind i PowerPoint, bør hvert slide have både mål og beregnet tid. Beregningen bør laves som:

```text
beregnet tid i sekunder = antal ord / 130 * 60
```

Hold 10-20 sekunder ekstra til naturlige pauser ved slide 7, 9, 10 og 12, fordi de slides bærer de mest tekniske forklaringer. Hvis oplægget under øvning bliver for langt, skal der først skæres i slide 3, 6 og 11, ikke i datamodel-, tracker- eller verifikationsslides.
