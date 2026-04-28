# Kursusmateriale Fil-Audit Fra Absalon

Dato: 2026-04-28  
Formål: rapportklar audit af observerede Absalon-moduler, filer og lektionsoverskrifter for de seks kurser, der kan forankre bachelorpakken om Træningsmester.  
Kildegrundlag: eksisterende mappingfiler i denne mappe samt private råudtræk under `BachelorPrivateRaw/traeningsmester-2026-04-28/absalon/deep/`.

Denne audit gengiver kun korte titler, modulnavne og parafraser. Den kopierer ikke kursusmaterialets indhold, underviserkommentarer, opgavebesvarelser, forelæsningsoptagelser eller lukkede adgangslinks.

## Auditmetode Og Begrænsning

Materialet er gennemgået på metadata-/outline-niveau fra Absalon DOM-udtræk og eksisterende kursusmapping. Det betyder, at rapporten sikkert kan bruge kursusforløb, filnavne og lektionsoverskrifter som dokumenteret kursuskontekst, men ikke kan citere slideindhold, PDF-afsnit eller feedback uden manuel loginåbning og særskilt kildeudvælgelse.

Vurderingerne nedenfor bruger tre kategorier:

- Direkte rapportrelevant: bør eksplicit indgå i bachelorens teori, metode, arkitektur, design, data- eller projektstyringsafsnit.
- Støtte: relevant som baggrund eller bilagstænkning, men bør ikke fylde i hovedanalysen.
- Gap: kræver manuel åbning i Absalon eller lokal adgang til selve filen, før der kan henvises mere præcist end titel/modul.

## Samlet Overblik

| Kursus | Observeret dækning | Direkte rapportværdi | Hovedgap |
| --- | --- | --- | --- |
| 80540 Software Development for Digital Health | Komplet ugeforløb med krav, UML, arkitektur, test, database, SQL, XML og systems engineering | Meget høj: teknisk ryggrad for krav, UML, arkitektur, database og test | Slideindhold i `SDDH_week*.pdf` skal åbnes manuelt ved konkrete citater |
| 77437 IT-projektledelse | Seminarer 1-7, projektdefinition, benefits, risiko, krav, WBS, modenhed, kompetencer og Tinglysning-case | Høj: scope, risiko, releaseparathed og kritisk projektrefleksion | Seminarpræsentationer og templates bør åbnes ved præcis metodebrug |
| 72545 Interaktionsdesign | Uge 6-12 med mennesker/interaktion, brugerforståelse, design, prototyper, evaluering og UI-typer | Meget høj: UX-rationale for tracker-off, watch, Live Activity og lav friktion | Kursussiden gav kun fuld moduloversigt via separat modules-udtræk; slides/kapitler skal åbnes manuelt |
| 79772 Kvantitative og kvalitative undersøgelsesmetoder | Modul 1-12, spørgeskema, observation, etnografi, digitale metoder, interview, databehandling, etik, analyse | Meget høj: metodekapitel, beta-feedback, etik og evidensbegrænsning | Ingen indholdsaudit af slides; datagrundlagets faktiske størrelse skal dokumenteres i rapporten |
| 88370 Kursus i Bachelorprojekt | Arbejdsbeskrivelse og FAQ | Høj som formel ramme, lav som teori | Arbejdsbeskrivelse/FAQ skal åbnes manuelt for formelle krav og citérbare formuleringer |
| 89332 Sundhedsdata og interoperabilitet | Uge 1-8 med procesdesign, DCR/BPMN, guidelines, healthcare data, data quality, HL7/FHIR/SNOMED, EHR, timed DCR, coding og AI/CDS | Høj: dataansvar, DCR/BPMN, interoperabilitet og afgrænsning fra klinisk system | Standard- og datakvalitetskilder skal åbnes manuelt, hvis rapporten vil bruge dem som egentlige litteraturkilder |

## 80540 - Software Development For Digital Health

Absalon-kursus: `https://absalon.ku.dk/courses/80540`  
Observerede råfiler: `course-80540-outline-filter-2026-04-28.txt`, `course-80540-home-filter-2026-04-28.txt`, `course-80540-full-dom-2026-04-28.txt`, `course-outlines-structured-2026-04-28.json`.

### Observerede moduler, filer og lektionsoverskrifter

| Modul | Observerede titler/filer | Auditnote |
| --- | --- | --- |
| About the Course | General Information | Kursusramme observeret, men ikke indholdsåbnet |
| Week 1 - Introduction | `SDDH_week1.pdf`, Padlet om fremtidig rolle, læsning i software engineering og UML-introduktion | Direkte relevant til at positionere projektet som software engineering-case |
| Week 2 - Process Models | `SDDH_week2.pdf`, Padlet om telemedicine user stories | Direkte relevant til iterativ udvikling, parity-migration og procesvalg |
| Week 3 - Requirements Engineering | `SDDH_week3.pdf`, læsning om krav og UML | Direkte relevant til kravsporbarhed og problem-til-krav |
| Week 4 - Use Case and Class Diagrams | `SDDH_week4.pdf`, `week4.py` | Direkte relevant til use cases og klassediagram |
| Week 5 - Class and Sequence Diagrams | `SDDH_week5.pdf`, `week5.py` | Direkte relevant til sekvensdiagrammer for tracker, Live Activity og watch-sync |
| Week 6 - Testing | `SDDH_week6.pdf`, `week6.py` | Direkte relevant til teststrategi, unit/integration og traceability |
| Week 7 - System Architecture | `SDDH_week7.pdf`, `week7.py`, note om aflyst forelæsning | Direkte relevant, men forelæsningsaflysningen bør nævnes som kildebegrænsning hvis nødvendigt |
| Week 8 - Intro to Databases | `SDDH_week8.pdf`, læsning om databaser og modellering | Direkte relevant til relationel backend og ERD |
| Week 9 - Relational Data Models | `SDDH_week9.pdf` | Direkte relevant til plan/workout/trackerlog/completion/cycle-modellen |
| Week 10 - SQL | `SDDH_week10.pdf` | Direkte relevant til Supabase SQL, views, RPC og RLS |
| Week 11-12 | Holiday/partial holiday-noter | Støtte; ikke rapportrelevant ud over at forklare kursusrytme |
| Week 13 - Diagrams and Databases | `SDDH_week13.pdf` | Direkte relevant til kobling mellem diagrammer og datamodel |
| Week 14 - XML | `SDDH_week14.pdf`, `week14.py`, ekstern XML-introduktion, valgfrit Sundhedsdatastyrelsen-XML | Direkte relevant som dataformatrefleksion, ikke som implementeret appformat |
| Week 15 - Systems Engineering | `SDDH_week15.pdf` | Direkte relevant til systemgrænser mellem iOS, watchOS, Live Activity, Supabase og Edge Functions |
| Week 16-17 | Q&A og exam preparation | Støtte; kan bruges til eksamensramme, ikke hovedrapport |
| TA | Intro, OOP, SQL, code examples, SQL samples, database-application interaction | Direkte/støtte: implementeringsnære koblinger mellem Swift-modeller, repositories og relationel backend |

### Direkte rapportrelevante dele

- Requirements engineering til at vise sporbarhed fra problemformulering til krav for tracker-off, progression, sikker dataadgang og flere klientflader.
- Use case-, class- og sequence diagrams til bachelorens UML-afsnit.
- System architecture til lagdeling: SwiftUI, AppState, domain models, repositories, Supabase, Edge Functions, watchOS og ActivityKit.
- Databases, relational models og SQL til ERD, schema, RLS, RPC, views og datakvalitet.
- Testing til teststrategi, test traceability og begrænsninger i integrationstests.
- XML/systems engineering til kort interoperabilitetsrefleksion.

### Støttemateriale

- Padlet-filerne om rolle og telemedicine user stories kan støtte refleksion, men er ikke centrale for bachelorens app-case.
- TA-code og SQL-eksempler kan støtte forklaringen af repository-pattern og database access, men bør ikke citeres tungt.
- Holiday-, Q&A- og exam preparation-moduler er primært kursusadministration.

### Gaps Ved Manuel Login/Filåbning

- Åbn `SDDH_week3.pdf`, `SDDH_week4.pdf`, `SDDH_week5.pdf`, `SDDH_week6.pdf`, `SDDH_week7.pdf`, `SDDH_week9.pdf` og `SDDH_week10.pdf`, hvis rapporten skal citere eller præcist definere krav, UML, test, arkitektur eller SQL.
- Åbn `week*.py` og database-application-eksemplet kun hvis de skal bruges som teknisk inspiration; ellers er titlerne nok.
- Afklar om XML-materialet fra Sundhedsdatastyrelsen må bruges som offentlig kilde, eller om det kun skal nævnes som kursusobserveret ressource.

## 77437 - IT-Projektledelse

Absalon-kursus: `https://absalon.ku.dk/courses/77437`  
Observerede råfiler: `course-77437-outline-filter-2026-04-28.txt`, `course-77437-full-dom-2026-04-28.txt`, `course-outlines-structured-2026-04-28.json`.

### Observerede moduler, filer og lektionsoverskrifter

| Modul | Observerede titler/filer | Auditnote |
| --- | --- | --- |
| About the Course | Undervisningsplan for IT-projektledelse | Rammefil; bør åbnes ved eksakt kursusbeskrivelse |
| Seminar 1 | Forelæsningsoptagelse, præsentation, offentlige IT-projektproblemer, damage cases, Bonnerup-rapporten, statslig projektprofessionalisering, styringsdiscipliner/faser, artikel om IT-katastrofer, idéskitse-skabelon | Direkte relevant til risiko, governance og tidlig idéafgrænsning |
| Seminar 2 | Forelæsningsoptagelse, præsentation, omtankeløs forvaltning, projektdefinition, benefits | Direkte relevant til projektdefinition og benefits |
| Seminar 3 | Præsentation, risici i større IT-projekter, risikoanalyse-skabelon, optagelse | Direkte relevant til risikolog og sikkerhedsgates |
| Seminar 4 | Præsentation, gæsteoplæg, kravskabelon, Boehm/Turner, Larman/Basili, aktivitetsbeskrivelse, leveranceplan/WBS/projektplan | Direkte relevant til kravstyring, agil/planlagt balance og leveranceplan |
| Seminar 5 | Præsentation, optagelse, modenhedspublikation | Direkte relevant til produktionsparathed og release-gates |
| Seminar 6 | Præsentation og optagelse | Støtte; titlerne angiver ikke nok til direkte rapportbrug uden åbning |
| Seminar 7 | Præsentation, Lent/Pinkowska, kompetencestyring, kompetencestyringsværktøj, optagelse | Støtte/direkte til rolle- og kompetencerefleksion i soloprojekt |
| Case: Tinglysningsprojektet | Kontrakt, bilag om tidsplan og kravspecifikation, overtagelsesprøve, leverandørdokument, notater, Rigsrevision/Statsrevisorer, opfølgninger | Støtte som kritisk referencecase for krav, overtagelsesprøve og governance |

### Direkte rapportrelevante dele

- Idéskitse, projektdefinition og benefits til at forklare bachelorens scope og nytte: mindre træningsfriktion, fleksibel progression og sikker dataadgang.
- Risikoanalyse til service-role, RLS, cross-user access, persondata, TestFlight/release og feature scope.
- Kravskabelon, WBS og leveranceplan til at forklare hvordan bachelorpakken er planlagt og dokumenteret.
- Modenhed til at skelne prototype, beta, releasekandidat og resterende production gaps.

### Støttemateriale

- Tinglysningsmaterialet er nyttigt som negativ referencecase, men bør kun bruges kort og analytisk. Bacheloren er ikke et offentligt megaprojekt.
- Kompetencestyringsmateriale kan støtte refleksion over soloprojektets rolleblanding, men bør ikke overtage metodeafsnittet.
- Forelæsningsoptagelser er primært støtte, medmindre de åbnes og der tages præcise noter.

### Gaps Ved Manuel Login/Filåbning

- Åbn undervisningsplanen og seminarpræsentationerne, hvis rapporten skal beskrive kursets læringsmål eller bruge begreber mere præcist.
- Åbn risikoanalyse-, projektdefinition-, krav- og WBS-skabelonerne, hvis bachelorens egne artefakter skal spejles eksplicit mod skabelonfelter.
- Seminar 6 kræver manuel åbning; DOM-titlerne viser ikke nok til at afgøre direkte relevans.
- Brug ikke Zoom-/optagelseslinks i rapporten; de er adgangsmateriale, ikke rapportkilder.

## 72545 - Interaktionsdesign

Absalon-kursus: `https://absalon.ku.dk/courses/72545`  
Observerede råfiler: `course-72545-outline-filter-2026-04-28.txt`, `course-72545-full-dom-2026-04-28.txt`, `course-72545-modules-outline-filter-2026-04-28.txt`, `course-72545-modules-full-dom-2026-04-28.txt`, `course-outlines-structured-2026-04-28.json`.

### Observerede moduler, filer og lektionsoverskrifter

| Modul | Observerede titler/filer | Auditnote |
| --- | --- | --- |
| Uge 6 | Introduktion til kurset, læseseddel, øvelsesopgaver, Afleveringsopgave 1, Hornbæk-kapitler 1-4, introduktionsslides, "Forstå mennesker" | Direkte relevant som startpunkt for designramme og menneske-/brugerforståelse |
| Uge 7 | Mennesker og interaktion, læseseddel, Afleveringsopgave 2, øvelser, Hornbæk-kapitler 5-7 og 16/18/19, slides om mennesker og interaktion | Direkte relevant til fysisk træningskontekst, opmærksomhed og interaktion |
| Uge 8 | Forstå brugerne, læseseddel, Afleveringsopgave 3, øvelser, Hornbæk-kapitler 11-14, brugerundersøgelser, observation/spørgeskema | Direkte relevant til brugerindsigt og beta-feedback |
| Uge 9 | Design, læsesedler, Afleveringsopgave 3, øvelser, Hornbæk-kapitler 30-33, design- og prototypeslides | Direkte relevant til designiterationer og prototypebegrundelse |
| Uge 10 | Evaluering, læseseddel, Afleveringsopgave 4, øvelser, Hornbæk-kapitler 40-43, evaluation, tænke-højt/eksperimenter | Direkte relevant til evaluering af TestFlight/beta, men evidensniveau skal begrænses |
| Uge 11 | Brugergrænseflader, læseseddel, Hornbæk-kapitler 23-28, Afleveringsopgave 4, UI-slides, fem typer brugergrænseflader | Direkte relevant til iOS/watch/Live Activity som forskellige UI-kontekster |
| Uge 12 | Afrunding, øvelsesopgaver, Hornbæk-kapitler 45-46, afslutningsslides | Støtte til syntese og kritisk designvurdering |
| Faggrupper | Afleveringsgrupper observeret | Ikke rapportrelevant |

### Direkte rapportrelevante dele

- Mennesker og interaktion til at beskrive træningssituationen som lav-opmærksomheds, fysisk belastet kontekst.
- Brugerundersøgelser, observation og spørgeskema til at begrunde beta-feedback som designinput.
- Design/prototyper til migrationen fra FlutterFlow-parity til native SwiftUI.
- Evaluering, tænke-højt og eksperimenter til at beskrive TestFlight-feedback som praktisk evaluering, ikke langtidsadherence-studie.
- Brugergrænseflader til at forklare hvorfor samme træningsproces findes i app, watch og Live Activity.

### Støttemateriale

- Læsesedler og øvelsesopgaver støtter forståelsen af kursusforløbet, men er ikke nødvendige i hovedrapporten.
- Afleveringsopgaverne bør kun nævnes, hvis de faktisk har skabt artefakter eller refleksioner, der bruges i bacheloren.
- Hornbæk-kapitlerne er potentielt stærke teoretiske kilder, men filindholdet er ikke auditeret her.

### Gaps Ved Manuel Login/Filåbning

- Den normale kursusforside viste primært faggrupper; den fulde ugeoversigt kom fra modules-udtrækket. Verificér manuelt i Absalon, hvis kursusstrukturen skal dokumenteres formelt.
- Åbn relevante slides om brugerundersøgelser, observation/spørgeskema, design, prototyper, evaluation og brugergrænseflader før præcise begrebsdefinitioner.
- Åbn Hornbæk-kapitlerne eller brug officiel bogreference, hvis rapporten vil henvise til teori om interaktion, prototyping eller evaluering.

## 79772 - Kvantitative Og Kvalitative Undersøgelsesmetoder

Absalon-kursus: `https://absalon.ku.dk/courses/79772`  
Observerede råfiler: `course-79772-outline-filter-2026-04-28.txt`, `course-79772-full-dom-2026-04-28.txt`, `course-outlines-structured-2026-04-28.json`.

### Observerede moduler, filer og lektionsoverskrifter

| Modul | Observerede titler/filer | Auditnote |
| --- | --- | --- |
| Modul 1 | Introduktion, metoder og videnskabsteori | Direkte relevant til metodeposition |
| Modul 2 | Spørgeskema 1 | Direkte relevant til survey/spørgeramme |
| Modul 3 | Spørgeskema 2 | Direkte relevant til surveykvalitet og operationalisering |
| Modul 4 | Deltagerobservation og etnografi | Direkte relevant til træning som praksiskontekst |
| Modul 5 | Digitale metoder | Direkte relevant til TestFlight, logs, screenshots og digitale feedbackspor |
| Modul 6 | Fænomenologi og interview, ethnographic interview, holdundervisning | Direkte relevant til kvalitativ brugerforståelse |
| Modul 7 | Databehandling, kvalitet og etik, samtykke/oplysningspligt | Meget direkte relevant til anonymisering, PII og etisk databrug |
| Modul 8 | Synopsis-skabelon | Støtte til rapportstruktur |
| Modul 9 | Analyse af data | Direkte relevant til tematisk feedbackanalyse |
| Modul 10 | Modul observeret uden links i udtrækket | Gap |
| Modul 11 | Minikonference og program | Støtte til formidling, ikke hovedmetode |
| Modul 12 | Forelæsning | Gap/støtte; kræver åbning for relevans |
| Projektopgaven | Synopsis-skabelon, eksamensinformation | Støtte til metodefremstilling og eksamensramme |
| Diverse | Lighthouse, holdundervisning/øvelser | Støtte, ikke direkte bachelorargument |

### Direkte rapportrelevante dele

- Videnskabsteori og metodevalg til at placere projektet som design-/implementeringscase med kvalitativ brugerindsigt.
- Spørgeskema-modulerne til at forklare spørgsmål om friktion, værdi, prioritering og betalingsvillighed.
- Observation/etnografi og interview/fænomenologi til at læse træningsbrug som praksis og oplevet friktion.
- Digitale metoder til at legitimere TestFlight, repoartefakter, screenshots og anonymiserede digitale beskeder som datakilder.
- Databehandling, kvalitet, etik og samtykke til PII-redaktion og privat rådatamappe udenfor repoet.
- Dataanalyse til feedbacktemaer og designbeslutninger.

### Støttemateriale

- Synopsis- og eksamensinformation kan støtte rapportstruktur, men bør ikke være hovedteori.
- Minikonference og Lighthouse er primært proces-/formidlingsstøtte.
- Holdundervisningsøvelser kan være relevante, men kræver åbning.

### Gaps Ved Manuel Login/Filåbning

- Modul 10 har ingen synlige filer i udtrækket; manuel Absalon-kontrol kræves.
- Modul 12 kræver åbning for at vurdere konkret relevans.
- Åbn Modul 7-filerne, hvis rapporten skal formulere et stærkt etikafsnit med præcise begreber.
- Kvantitativ metode må ikke overpåstås: rapporten skal dokumentere faktisk antal deltagere/svar og beskrive resultater som indikative, hvis datagrundlaget er lille.

## 88370 - Kursus I Bachelorprojekt

Absalon-kursus: `https://absalon.ku.dk/courses/88370`  
Observerede råfiler: `course-88370-outline-filter-2026-04-28.txt`, `course-88370-full-dom-2026-04-28.txt`, `course-outlines-structured-2026-04-28.json`.

### Observerede moduler, filer og lektionsoverskrifter

| Modul | Observerede titler/filer | Auditnote |
| --- | --- | --- |
| Om bachelor projekter | `2025-06-25 Bachelorprojekt - arbejdsbeskrivelse.rtf`, `2025-06-25 FAQ om bachelorprojektet.docx` | Direkte relevant som formel ramme |
| Nylig feedback | Overskrift observeret | Ikke brugbar uden manuel åbning; feedback bør ikke gengives i rapporten |
| Aktiviteter/kalender/meddelelser | Standard Absalon-links | Ikke rapportrelevant |

### Direkte rapportrelevante dele

- Arbejdsbeskrivelsen bør bruges til at sikre, at rapporten er problemstyret, metodebevidst og kritisk.
- FAQ bør bruges til formelle afklaringer om omfang, bilag og forventninger.

### Støttemateriale

- Selve kurset er primært rammesættende. Det er ikke en stærk teorikilde sammenlignet med softwareudvikling, metode, interaktionsdesign og interoperabilitet.

### Gaps Ved Manuel Login/Filåbning

- Åbn arbejdsbeskrivelse og FAQ manuelt før endelig rapport, så formalia ikke baseres på filnavne alene.
- Undgå at bruge "Nylig feedback" som kilde, medmindre indholdet er relevant, privat håndteret og må gengives.

## 89332 - Sundhedsdata Og Interoperabilitet

Absalon-kursus: `https://absalon.ku.dk/courses/89332`  
Observerede råfiler: `course-89332-outline-filter-2026-04-28.txt`, `course-89332-full-dom-2026-04-28.txt`, `course-outlines-structured-2026-04-28.json`.

### Observerede moduler, filer og lektionsoverskrifter

| Modul | Observerede titler/filer | Auditnote |
| --- | --- | --- |
| About the Course | Kursusramme observeret uden synlige filer | Støtte; kræver åbning ved formel kursusbeskrivelse |
| Uge 1 | Procesdesignværktøjer, introduktion, pensum kap. 1-3+19 og artikel, declarative workflows, process management, DCR vs BPMN | Direkte relevant til procesmodellering og fleksible workflows |
| Uge 2 | Guidelines/protokoller, BPMN-forelæsning, assignment, pensum kap. 15-17 | Direkte relevant til BPMN og træningsprogrammer som protokollignende flows |
| Uge 3 | Health informatics chapters, methods of knowing + healthcare data | Direkte relevant til sundhedsdata-afgrænsning og datakildekritik |
| Uge 4 | Benson/Grieve om SNOMED CT/HL7/FHIR, data quality + interoperability, Mohammed et al. om data quality assessment | Meget direkte relevant til interoperabilitet, datakvalitet og standardafgrænsning |
| Uge 5 | SP/FMK/SMR-slides, tredje afleveringsopgave | Støtte til national sundhedsdata-afgrænsning |
| Uge 6 | Elektroniske patientjournaler, timed DCR, kodning af data | Direkte/støtte til at afgrænse Træningsmester fra EHR og kliniske beslutningsregler |
| Uge 7 | Health informatics chapters, clinical decision support and AI | Direkte relevant til AI-afgrænsning og server-side programreview/import |
| Uge 8 | Review | Støtte |
| Faggrupper/Nylig feedback | Afleveringsgruppe og feedbackoverskrifter observeret | Ikke rapportrelevant uden manuel og privat håndtering |

### Direkte rapportrelevante dele

- DCR vs BPMN til at skelne mellem sekventielle brugerflows og deklarative sikkerheds-/autorisationsregler.
- Process management/guidelines til at beskrive workout-start, tracker-on/off, completion og cyklusprogression som processer.
- Healthcare data og methods of knowing til at afgrænse fitnessdata fra kliniske journaldata.
- Data quality og interoperability til at diskutere tradeoff mellem lav friktion og detaljerede trackerlogs.
- SNOMED CT/HL7/FHIR som standardiseringsperspektiv, ikke som implementeret integration.
- Timed DCR og coding of data som refleksion over tidslige events, logs og completion-events.
- Clinical decision support and AI til at afgrænse AI-import/programreview fra klinisk beslutningsstøtte.

### Støttemateriale

- SP/FMK/SMR og elektroniske patientjournaler er stærke afgrænsningskilder, men de bør ikke fremstilles som noget Træningsmester implementerer.
- Assignments og feedback er ikke nødvendige for bachelorrapporten, medmindre de bruges som egen læringsproces og må omtales.
- Review-modulet er støtte til eksamensforberedelse.

### Gaps Ved Manuel Login/Filåbning

- Åbn DCR/BPMN-filerne, hvis rapporten skal definere forskellen mellem notationsformerne præcist.
- Åbn data quality- og interoperability-materialet før konkrete kriterier som fuldstændighed, korrekthed, aktualitet og formålsfit bruges.
- Åbn Benson/Grieve og Mohammed et al. hvis de skal ind som litteraturkilder i referenceafsnittet.
- Afklar præcist hvor HealthKit nævnes i bacheloren: det bør beskrives som samtykkebaseret fitness-/platformsintegration, ikke klinisk FHIR/HL7-udveksling.

## Tværgående Gaps Der Stadig Skal Lukkes

| Gap | Hvorfor det betyder noget | Foreslået handling |
| --- | --- | --- |
| Filindhold er ikke fuldt åbnet | Outlines dokumenterer titler, men ikke definitioner, modeller eller citérbare pointer | Åbn kun de få filer, der skal bruges som egentlige kilder i rapporten |
| Kursusmateriale må ikke overkopieres | Bachelorpakken skal være rapportklar uden lukket kursusindhold | Brug korte titler/parafraser og henvis til kursus/materialetype |
| Metodeevidens kan blive for stærkt formuleret | Beta-feedback og digitale spor viser plausibilitet, ikke statistisk motivationseffekt | Skriv "designbaseret evaluering" og begræns kvantitative konklusioner |
| Interoperabilitet kan blive overdrevet | Træningsmester er ikke klinisk EHR/FHIR-system | Brug 89332 til kritisk afgrænsning og datakvalitet, ikke til at påstå klinisk integration |
| Projektledelse er delvist retrospektiv | Rapporten kan ligne efterrationalisering | Adskil faktiske logs/artefakter fra efterfølgende refleksion |
| Mange features kan sløre hovedproblemet | Appen kan fremstå som produktkatalog | Prioritér tracker-off, completion-events, cycle runtime, watch/Live Activity og sikker dataadgang |

## Topkaraktervurdering

### Teorier Og Metoder Der Bør Eksplicit Ind I Bacheloren

1. Software engineering-kæden fra 80540: krav, use cases, klassediagram, sekvensdiagram, systemarkitektur, relationel datamodel, SQL/RLS og test. Det er bachelorens stærkeste tekniske fundament.
2. Interaktionsdesign fra 72545: brugerens kontekst under træning, prototyping, evaluering og brugergrænseflader på tværs af iPhone, watch og Live Activity. Det binder appens funktioner til problemformuleringens motivation/friktion.
3. Metodepakken fra 79772: kvalitativ tematisk analyse, digitale metoder, spørgeskema-/interviewlogik, databehandling, etik og samtykke. Det skal bruges til at legitimere beta-feedback og samtidig afgrænse evidensniveauet.
4. Projektledelse fra 77437: scope, benefits, risikoanalyse, kravstyring, leveranceplan/WBS og modenhed. Det er især vigtigt for at vise, at featurebredden er styret og risikobevidst.
5. Sundhedsdata og interoperabilitet fra 89332: BPMN/DCR, procesmodellering, data quality, interoperability og HL7/FHIR/SNOMED som kritisk perspektiv. Det skal især bruges til at vise moden afgrænsning fra klinisk sundhedssystem.
6. Bachelorprojektkursets ramme fra 88370: problemstyring, formalia, kritisk refleksion og bilagsdisciplin.

### Hvad Der Er Stærkt Nok Til Topkarakter

- Problemformuleringen kan kobles direkte til konkrete implementeringsvalg: tracker-off, completion-events, cycle runtime, watch/Live Activity og sikker dataadgang.
- Kursusgrundlaget dækker både teknisk software engineering, UX, metode, projektledelse og sundhedsdata. Det giver en tværfaglig bachelor, ikke kun en appbeskrivelse.
- Appens arkitektur giver gode analyseobjekter: typed repositories, Supabase/RLS, Edge Functions, ActivityKit, WatchConnectivity og testbar domain logic.
- Datakvalitetstradeoffet er fagligt interessant: lavere brugerfriktion giver bedre gennemførelsesdata, men mindre detaljeret sæthistorik.
- Etik og PII-håndtering kan dokumenteres stærkt, fordi rådata ligger privat, mens rapportpakken bruger anonymiserede og redigerede artefakter.

### Hvad Der Stadig Er For Tyndt

- Motivation/adherence-effekt er ikke dokumenteret som langtidsmåling. Rapporten bør ikke konkludere, at appen øger vedvarende motivation; den kan argumentere for, at designet adresserer kendte friktionspunkter og er plausibelt støttet af beta-feedback.
- Kvantitativ metode er sandsynligvis svagere end kvalitativ metode. Hvis svarantal og varighed er begrænset, skal det beskrives åbent.
- Klinisk interoperabilitet er ikke implementeret. FHIR/HL7/SNOMED bør være refleksion og perspektivering, ikke påstand om produktfunktion.
- Projektledelsesmaterialet skal kobles til faktiske artefakter, ellers bliver det retrospektiv pynt. Brug logs, backlog, quality gates og traceability-matrix som evidens.
- AI-features bør holdes sekundære. De er relevante som server-side import/programreview, men bachelorens hovedargument er fleksibel progression og lav friktion, ikke AI-performance.

### Anbefalet Topkarakterlinje

Den stærkeste rapportvinkel er at præsentere Træningsmester som en problemstyret software- og designcase: en native mobil løsning, hvor krav, arkitektur, dataansvar, interaktionsdesign og evaluering alle peger mod samme kerneproblem, nemlig fleksibel progression uden at straffe brugeren for realistiske afvigelser. Topkarakteren kræver især præcis afgrænsning: stærke design- og arkitekturargumenter, men ærlig begrænsning af effektmåling, klinisk interoperabilitet og kvantitativ generalisering.
