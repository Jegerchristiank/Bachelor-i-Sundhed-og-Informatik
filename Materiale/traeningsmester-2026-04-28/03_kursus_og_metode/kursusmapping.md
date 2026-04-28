# Dyb Absalon-kursusmapping til Træningsmester

Dato: 2026-04-28  
Formål: rapportklar kobling mellem Absalon-kursernes forløb og bachelorprojektets afsnit, artefakter og refleksioner.  
Kildegrundlag: private Absalon-råudtræk i `BachelorPrivateRaw/traeningsmester-2026-04-28/absalon/deep/`, især det strukturerede kursusoutline-udtræk og moduludtræk for kursus 72545, 80540, 77437, 79772, 88370 og 89332.

Denne fil gengiver kun kursustitler, modul-/lektionsoverskrifter, artikeltitler og korte emneparafraser. Den kopierer ikke fulde slides, pensumtekster, opgaver, feedback, underviserkommentarer eller andet lukket kursusmateriale.

## Projektets faglige kerne

Træningsmester undersøger, hvordan en digital træningsapp kan understøtte programstruktur, progression og feedback uden at gøre realistiske afvigelser fra et træningsprogram demotiverende. Caseimplementeringen er en native SwiftUI-app med iOS-app, watchOS companion, Live Activity, Supabase backend, typed repositories, RLS, Edge Functions, betaafprøvning og rapportklare bilag.

Den autoritative problemformulering er:

> Hvordan kan en digital træningsapp designes og implementeres, så programstruktur, progression og feedback understøtter vedvarende motivation og fleksibel håndtering af afvigelser fra et planlagt træningsforløb uden at øge risikoen for demotivation og frafald?

Kursusmappingen bruges derfor ikke kun som en liste over relevante fag. Den viser, hvor bachelorrapporten kan dokumentere, at problem, metode, softwarearkitektur, brugerinddragelse, dataansvar og kritisk refleksion hænger sammen.

## Rapportafsnit og primære kursusspor

| Rapportafsnit | Primært kursusspor | Projektkobling |
| --- | --- | --- |
| Problemformulering og afgrænsning | Kursus i Bachelorprojekt, kvalitative/kvantitative metoder, interaktionsdesign | Motivation, adherence, afvigelser fra plan og empirisk afgrænset brugerproblem |
| Krav og use cases | Software Development for Digital Health, interaktionsdesign, projektledelse | Use cases for login, onboarding, tracker, tracker-off, watch, Live Activity, trainer-client og admin |
| UML, klassediagram og sekvensdiagram | Software Development for Digital Health | Domain models, repositories, AppState, Supabase dataflow og trackersekvens |
| Systemarkitektur | Software Development for Digital Health, IT-projektledelse | SwiftUI-lagdeling, watchOS, Live Activity, Supabase, Edge Functions, StoreKit og HealthKit |
| Database, SQL og XML | Software Development for Digital Health, Sundhedsdata og interoperabilitet | Postgres/Supabase schema, RLS, RPC, views, payloads, JSON/XML-perspektiv og dataformatgrænser |
| Projektledelse | IT-projektledelse | Scope, risiko, release-gates, TestFlight, sikkerhedsgates og teknisk gæld |
| Interaktionsdesign | Interaktionsdesign | Home, tracker, tracker-off, onboarding, watch og Live Activity som friktionsreducerende UX |
| Kvalitativ og kvantitativ metode | Kvantitative og kvalitative undersøgelsesmetoder | Beta-feedback, spørgeramme, tematisk kodning, TestFlight-tidslinje og begrænsninger |
| Bachelorprojektkrav | Kursus i Bachelorprojekt | Problemformulering, arbejdsbeskrivelse, bilagsstruktur, metode og kritisk vurdering |
| DCR, BPMN og interoperabilitet | Sundhedsdata og interoperabilitet | Autorisations-DCR, tracker-BPMN, data quality, HealthKit-afgrænsning og FHIR/HL7-refleksion |

## 80540 - Software Development for Digital Health

Absalon: `https://absalon.ku.dk/courses/80540`  
Kursusforløb: introduktion, procesmodeller, requirements engineering, use cases, class/sequence diagrams, testing, system architecture, databases, relational data models, SQL, diagrams/databases, XML og systems engineering.

### Konkrete koblinger

| Absalon-modul eller materiale | Faglig brug i rapporten | Træningsmester-kobling | Evidens i bachelorpakken |
| --- | --- | --- | --- |
| Week 1 - Introduction, inkl. software engineering og UML-introduktion | Placere projektet som softwareudviklingscase, ikke kun appbeskrivelse | SwiftUI-migrationen behandles som systemudvikling med krav, arkitektur, test og datamodel | `05_arkitektur_data_sikkerhed/arkitektur/arkitekturfortaelling.md` |
| Week 2 - Process Models | Forklare iterativ udvikling og parity-migration | Appen er udviklet i iterationer med buildlogs, TestFlight-builds, parity-afstemning og løbende redesign | `04_brugerindsigt_beta/testflight_tidslinje.md`, `Docs/ParityMatrix.md` |
| Week 3 - Requirements Engineering | Kravafsnit og traceability | Krav kobles til brugerproblemet: fleksibel progression, tracker-off, sikker dataadgang, watch og Live Activity | `05_arkitektur_data_sikkerhed/arkitektur/krav_traceability.md` |
| Week 4 - Use Case and Class Diagrams | Use case-model og klassediagram | Use cases for start workout, log sæt, afslut uden tracker, import program, trainer-client, admin og watch | `05_arkitektur_data_sikkerhed/arkitektur/use_cases.md` |
| Week 5 - Class and Sequence Diagrams | Sekvensdiagrammer for dataflow | Trackersekvens: Home vælger workout, tracker henter rows, logger sæt, skriver completion-event og kalder cycle progression | `05_arkitektur_data_sikkerhed/arkitektur/systembeskrivelse.md`, `05_arkitektur_data_sikkerhed/data_og_sikkerhed/dataflow.md` |
| Week 6 - Testing | Verifikation og teststrategi | Unit tests dækker payload encoding, planprogression, JWT, onboarding, Live Activity projection og cycle flow; integration tests dækker Supabase paths | `06_verifikation/verifikationsrapport.md`, `06_verifikation/test_traceability_matrix.md` |
| Week 7 - System Architecture | Arkitekturafsnit og containerdiagram | Lagdeling mellem SwiftUI views, AppState, domain models, repositories, support services, Supabase og Edge Functions | `05_arkitektur_data_sikkerhed/arkitektur/arkitekturfortaelling.md` |
| Week 8 - Intro to Databases | Datamodel og databaseansvar | Plan/workout/trackerlog/completion/cycle-modellen analyseres som persistenslag, ikke kun som UI-state | `05_arkitektur_data_sikkerhed/data_og_sikkerhed/sql_schema_overblik.md` |
| Week 9 - Relational Data Models | ERD og relationel modellering | `plan`, `workout`, `plan_workouts`, `workout_exercises`, `trackerlog`, `workout_completion_events` og `training_cycle_*` viser normaliseret træningsstruktur | `05_arkitektur_data_sikkerhed/data_og_sikkerhed/sql_inventory_report.md` |
| Week 10 - SQL | SQL-, RLS- og RPC-afsnit | Supabase/Postgres bruges med tabeller, views, RLS, constraints, security definer functions og RPC'er | `05_arkitektur_data_sikkerhed/data_og_sikkerhed/rls_matrix.md`, `SUPABASE_MASTER_SETUP.sql` |
| Week 13 - Diagrams and Databases | Koble diagrammer til databasebeslutninger | ERD forklarer, hvorfor tracker-off completion kan eksistere uden detaljeret `trackerlog` | `05_arkitektur_data_sikkerhed/arkitektur/arkitekturfortaelling.md` |
| Week 14 - XML og XML-introduktion | Dataformatrefleksion | Appen bruger primært Swift Codable/JSON/PostgREST, men XML bruges som sammenligningspunkt for strukturerede sundhedsdataformater og historisk interoperabilitet | `05_arkitektur_data_sikkerhed/data_og_sikkerhed/interoperabilitet_dcr_bpmn_notat.md` |
| Week 15 - Systems Engineering | Systemperspektiv og grænseflader | iOS, watchOS, Live Activity, Supabase, Edge Functions, StoreKit og HealthKit analyseres som sammenhængende system | `05_arkitektur_data_sikkerhed/arkitektur/systembeskrivelse.md` |
| TA-materiale om OOP, SQL og database-application interaction | Implementeringsnær forklaring | Domain models, payload DTO'er og repository-pattern viser koblingen mellem objektorienteret Swift-kode og relationel backend | `Traeningsmester/Core/Domain/*`, `Traeningsmester/Core/Data/*` |

### Rapportklar pointe

Dette kursus er det stærkeste fundament for rapportens tekniske kapitler. Træningsmester kan demonstrere hele kæden fra krav til model, arkitektur, database, SQL, test og systemintegration. For topkarakter bør rapporten ikke nøjes med at vise diagrammer; den bør forklare, hvordan diagrammerne har styret konkrete designbeslutninger, fx hvorfor `workout_completion_events` findes ved siden af `trackerlog`, og hvorfor Edge Functions bruges til privilegerede flows.

## 77437 - IT-projektledelse

Absalon: `https://absalon.ku.dk/courses/77437`  
Kursusforløb: seminarer om offentlige IT-projekter, projektdefinition, benefits, risici, krav, planlægning, modenhed, kompetencestyring og Tinglysningsprojektet som casegrundlag.

### Konkrete koblinger

| Absalon-modul eller materiale | Faglig brug i rapporten | Træningsmester-kobling | Evidens i bachelorpakken |
| --- | --- | --- | --- |
| Seminar 1 med materiale om problemer i offentlige IT-projekter, damage cases og styringsdiscipliner | Indledning til projektstyringsrisici | Projektet håndterer risiko for scope creep ved at skelne mellem bachelorens hovedproblem og teknisk caseafgrænsning | `01_rapportgrundlag/problemformulering/problemformulering_autoritativ.md` |
| Skabelon for idéskitse | Tidlig projektdefinition | Problemfeltet afgrænses til digital træning, motivation, progression og afvigelser fra plan | `01_rapportgrundlag/problemformulering/problemformulering_resume.md` |
| Seminar 2 med projektdefinition og benefits | Business-/nytteargument | Nytten beskrives som lavere friktion under træning, bedre håndtering af realistiske afvigelser og mere sikker dataadgang | `05_arkitektur_data_sikkerhed/arkitektur/beslutningslog.md` |
| Seminar 3 med risikoanalyse | Risikoafsnit | Centrale risici: service-role leakage, RLS-fejl, cross-user adgang, App Store/TestFlight usikkerhed, HealthKit-overdrivelse og for stor featurebredde | `05_arkitektur_data_sikkerhed/data_og_sikkerhed/sikkerhedsnotat.md`, `06_verifikation/quality_gate_review.md` |
| Seminar 4 med kravskabelon, agil/planlagt udvikling og leveranceplan/WBS | Kravstyring og leveranceplan | Projektet kombinerer parity-krav, native UX-forbedringer, sikkerhedsbaseline og bachelorbilag i en iterativ leverance | `05_arkitektur_data_sikkerhed/arkitektur/krav_traceability.md` |
| Seminar 5 om modenhed | Vurdering af produktionsparathed | Rapporten kan skelne mellem fungerende prototype, beta, sikkerhedsverificeret release og resterende modenhedsgab | `01_rapportgrundlag/rapportstruktur/rapportklar_gap_lukning.md` |
| Seminar 7 om kompetencestyring | Refleksion over soloprojekt og rollefordeling | Den samme person har haft roller som udvikler, tester, produktansvarlig og rapportskriver; det giver fart, men øger risiko for blind spots | `06_verifikation/quality_gate_review.md` |
| Tinglysningsprojektets kontrakt-, krav-, prøve- og revisionsmateriale | Kritisk referencecase for IT-projektfejl | Bruges ikke som direkte sammenligning, men som advarsel mod uklare krav, svag overtagelsesprøve og manglende realistisk risikostyring | `06_verifikation/final_publication_checklist.md` |

### Rapportklar pointe

Projektledelsessporet bør bruges kritisk. Træningsmester er ikke et offentligt megaprojekt, men kursets temaer er relevante, fordi bacheloren har mange integrationsflader og høj risiko for at forveksle "flere features" med "bedre projekt". Det stærke argument er, at rapporten dokumenterer afgrænsning, risici, release-gates og evidens. Hullet er, at projektledelsen primært er dokumenteret retrospektivt; rapporten bør derfor ærligt beskrive, hvor planlægningen blev rekonstrueret fra logs og artefakter.

## 72545 - Interaktionsdesign

Absalon: `https://absalon.ku.dk/courses/72545`  
Kursusforløb: introduktion, mennesker og interaktion, brugerforståelse, design, prototyper, evaluering, tænke-højt/eksperimenter, brugergrænseflader og afrunding.

### Konkrete koblinger

| Absalon-modul eller materiale | Faglig brug i rapporten | Træningsmester-kobling | Evidens i bachelorpakken |
| --- | --- | --- | --- |
| Uge 6 - Introduktion til kurset | Grundlag for at beskrive UI som designbeslutning | Native SwiftUI vælges ikke kun af teknisk grund, men for at kunne skabe hurtigere, mere platformskonsistente træningsflows | `05_arkitektur_data_sikkerhed/arkitektur/designrationale.md` |
| Uge 7 - Mennesker og interaktion | Brugerens kontekst under træning | Appen designes til situationer med sved, tidspres, lav opmærksomhed og behov for hurtig registrering | `04_brugerindsigt_beta/beta_tester_rapport.md` |
| Uge 8 - Forstå brugerne, brugerundersøgelser, observation/spørgeskema | Empirisk brugerindsigt | Beta-feedback og spørgeramme bruges til at forstå friktion, værdi, betalingsvillighed og prioriterede forbedringer | `04_brugerindsigt_beta/feedbackkatalog.md`, `04_brugerindsigt_beta/beta_observationsmatrix.csv` |
| Uge 9 - Design og prototyper | Designiterationer | Onboarding, Home, tracker, tracker-off og premium flows kan præsenteres som iterationer fra FlutterFlow-parity til native UX | `02_figurer_og_screenshots/app_screenshots/screenshot_daekning.md` |
| Uge 10 - Evaluering, tænke-højt og eksperimenter | Evaluering af designvalg | TestFlight og anonymiseret feedback bruges som praktisk evaluering, ikke som fuldt kontrolleret eksperiment | `04_brugerindsigt_beta/beta_tester_rapport.md` |
| Uge 11 - Brugergrænseflader og typer af UI | UI-analyse | Watch app og Live Activity viser, at samme træningsflow kan have forskellige grænseflader afhængigt af kontekst | `05_arkitektur_data_sikkerhed/arkitektur/arkitekturfortaelling.md` |
| Uge 12 - Afrunding | Designkritik | Rapporten kan samle, hvilke designbeslutninger der direkte støtter motivation, og hvilke der stadig mangler empirisk validering | `01_rapportgrundlag/rapportstruktur/rapportklar_gap_lukning.md` |

### Rapportklar pointe

Interaktionsdesignsporet er stærkt, fordi bachelorens problem netop handler om brugeradfærd og motivation. Det centrale er at vise, at funktionerne ikke blot er tekniske: tracker-off, watch, Live Activity og completion-events er UX-greb, der anerkender realistisk træningsadfærd. For topkarakter bør rapporten dog undgå at påstå dokumenteret motivationsforbedring uden tilstrækkelig empiri. Den kan stærkt argumentere for designrationalet og vise plausibel brugerfeedback, men effekten på adherence kræver længere måling.

## 79772 - Kvantitative og kvalitative undersøgelsesmetoder

Absalon: `https://absalon.ku.dk/courses/79772`  
Kursusforløb: metoder og videnskabsteori, spørgeskema, deltagerobservation, etnografi, digitale metoder, fænomenologi og interview, databehandling, kvalitet og etik, synopsis, dataanalyse og minikonference.

### Konkrete koblinger

| Absalon-modul eller materiale | Faglig brug i rapporten | Træningsmester-kobling | Evidens i bachelorpakken |
| --- | --- | --- | --- |
| Modul 1 - introduktion, metoder og videnskabsteori | Metodeposition | Rapporten bør tydeligt skelne mellem design case, software engineering-evidens og brugerindsigt | `01_rapportgrundlag/problemformulering/problemformulering_autoritativ.md` |
| Modul 2 og 3 - spørgeskema | Kvantitativt perspektiv | Spørgerammen om brug, friktion, værdi og betalingsvillighed kan operationaliseres, men datagrundlaget er ikke stort nok til statistisk generalisering | `04_brugerindsigt_beta/beta_tester_rapport.md` |
| Modul 4 - deltagerobservation og etnografi | Observation af praksis | Træningssituationen analyseres som praksiskontekst: brugeren er i bevægelse, og appen må ikke kræve perfekt registreringsdisciplin | `05_arkitektur_data_sikkerhed/arkitektur/use_cases.md` |
| Modul 5 - digitale metoder | Digitalt datagrundlag | TestFlight metadata, Messenger-temaer, screenshots og repoartefakter bruges som digitale spor med redaktions- og samtykkekrav | `04_brugerindsigt_beta/indsamlingsprotokol.md` |
| Modul 6 - fænomenologi og interview | Kvalitativ brugerforståelse | Feedback kan læses som brugerens oplevede friktion og værdi, ikke kun som bug reports | `04_brugerindsigt_beta/messenger_dybdeanalyse.md` |
| Modul 7 - databehandling, kvalitet og etik | Etik og anonymisering | Public dokumentation pseudonymiserer testere og holder rå persondata udenfor repoet | `06_verifikation/pii_redaction_audit.md`, `04_brugerindsigt_beta/indsamlingsprotokol.md` |
| Modul 8 - synopsis | Rapportstruktur | Problem, metode, data, analyse, refleksion og bilag samles i en bachelorrettet struktur | `README.md`, `01_rapportgrundlag/rapportstruktur/rapportafsnit_mapping.md` |
| Modul 9 - analyse af data | Tematisk analyse | Feedbacktemaer som Live Activity-værdi, øvelsesmedier, katalogdækning og releaseprioritering kobles til designbeslutninger | `04_brugerindsigt_beta/feedbackkatalog.md` |
| Projektopgaven og eksamensinformation | Metodisk transparens | Rapporten skal vise datagrundlag, begrænsninger og hvad der ikke kan konkluderes | `04_brugerindsigt_beta/beta_tester_rapport.md` |

### Rapportklar pointe

Metodesporet kan løfte bacheloren, hvis rapporten er præcis om evidensniveau. Der er stærk kvalitativ og artefaktbaseret dokumentation for designbeslutninger, men ikke et stort kvantitativt studie. Det bør formuleres som designbaseret evaluering med anonymiseret beta-feedback, ikke som statistisk dokumentation for motivationseffekt.

## 88370 - Kursus i Bachelorprojekt

Absalon: `https://absalon.ku.dk/courses/88370`  
Kursusforløb: "Om bachelor projekter", arbejdsbeskrivelse og FAQ.

### Konkrete koblinger

| Absalon-modul eller materiale | Faglig brug i rapporten | Træningsmester-kobling | Evidens i bachelorpakken |
| --- | --- | --- | --- |
| Bachelorprojekt - arbejdsbeskrivelse | Rapportens formelle ramme | Problemformulering, metode, teknisk løsning, evaluering og kritisk refleksion skal fremstå som bachelorprojekt, ikke produktpitch | `01_rapportgrundlag/problemformulering/problemformulering_autoritativ.md` |
| FAQ om bachelorprojektet | Afklaring af omfang og dokumentation | Appens mange features skal underordnes en tydelig problemformulering og vurderes efter fagligt udbytte | `01_rapportgrundlag/rapportstruktur/rapportklar_gap_lukning.md` |
| Om bachelor projekter | Selvstændigt bidrag | Bidraget ligger i kombinationen af fleksibel træningsprogression, sikker dataarkitektur og brugercentreret native UX | `05_arkitektur_data_sikkerhed/arkitektur/arkitekturfortaelling.md` |

### Rapportklar pointe

Bachelorprojektkurset er ikke en indholdsfaglig kilde på samme måde som software-, metode- og interoperabilitetskurserne. Det er rammen for, hvordan projektet skal præsenteres: problemstyret, dokumenteret, afgrænset og kritisk. Rapporten skal derfor ikke drukne i featureliste, men vise hvorfor netop disse features belyser problemformuleringen.

## 89332 - Sundhedsdata og interoperabilitet

Absalon: `https://absalon.ku.dk/courses/89332`  
Kursusforløb: procesdesignværktøjer, introduktion, process management, DCR vs BPMN, guidelines/protokoller, BPMN, healthcare data, data quality, interoperability, SNOMED CT/HL7/FHIR, SP/FMK/SMR, elektroniske patientjournaler, timed DCR, kodning af data, clinical decision support og AI.

### Konkrete koblinger

| Absalon-modul eller materiale | Faglig brug i rapporten | Træningsmester-kobling | Evidens i bachelorpakken |
| --- | --- | --- | --- |
| Uge 1 - adgang til procesdesignværktøjer og introduktion | Procesmodellering | Trackerflow, authorization og dataudveksling modelleres som BPMN/DCR-lignende artefakter | `05_arkitektur_data_sikkerhed/data_og_sikkerhed/interoperabilitet_dcr_bpmn_notat.md` |
| Lektion om process management | Proces frem for enkeltstående skærme | Workout-start, tracker-on/off, completion og cycle progression beskrives som proces med alternative grene | `05_arkitektur_data_sikkerhed/arkitektur/arkitekturfortaelling.md` |
| Artikel om declarative workflows | DCR-fortolkning | Autorisation passer bedre som deklarative regler end som ren sekvens: RLS, admin guard, service-role boundary og cross-user denial | `05_arkitektur_data_sikkerhed/data_og_sikkerhed/interoperabilitet_dcr_bpmn_notat.md` |
| Modelling in DCR vs BPMN | Metodevalg for diagrammer | BPMN bruges til brugerflowets rækkefølge; DCR bruges til sikkerhedsbetingelser og eksklusioner | `05_arkitektur_data_sikkerhed/data_og_sikkerhed/interoperabilitet_dcr_bpmn_notat.md` |
| Uge 2 - guidelines/protokoller og BPMN | Workflow og protokoller | Træningsprogrammer kan læses som personlige protokoller, men appen tillader fleksibel afvigelse uden at miste sammenhæng | `05_arkitektur_data_sikkerhed/arkitektur/use_cases.md` |
| Uge 3 - methods of knowing og healthcare data | Sundhedsdata-afgrænsning | Rapporten bør præcisere, at appen håndterer trænings-/fitnessdata, ikke klinisk journalføring eller diagnose | `05_arkitektur_data_sikkerhed/data_og_sikkerhed/data_og_sikkerhed_rapportklar.md` |
| Uge 4 - data quality og interoperability | Datakvalitet | Completion-events øger adfærdsdatakvalitet for "træning gennemført", mens manglende trackerlog reducerer detaljeringsgrad. Det er et bevidst tradeoff | `05_arkitektur_data_sikkerhed/data_og_sikkerhed/dataflow.md` |
| Benson/Grieve-materiale om principper for interoperabilitet, SNOMED CT, HL7 og FHIR | Standardiseringsrefleksion | Projektet implementerer ikke FHIR/HL7, men kan reflektere over, hvad der skulle til for klinisk interoperabilitet | `05_arkitektur_data_sikkerhed/data_og_sikkerhed/interoperabilitet_dcr_bpmn_notat.md` |
| Mohammed et al. 2025 om data quality assessment | Kritisk datakvalitetsvurdering | Logs, completion-events, bodyweight, HealthKit-import og brugerindtastede øvelsesdata skal vurderes efter fuldstændighed, korrekthed og formål | `05_arkitektur_data_sikkerhed/data_og_sikkerhed/sql_schema_overblik.md` |
| Uge 5 - SP/FMK/SMR | National sundhedsdata-afgrænsning | Træningsmester bør ikke fremstilles som national sundhedsintegration; det er en app med afgrænset HealthKit-samtykke | `05_arkitektur_data_sikkerhed/data_og_sikkerhed/interoperabilitet_dcr_bpmn_notat.md` |
| Uge 6 - elektroniske patientjournaler, timed DCR og kodning af data | Afgrænsning og modellering | Systemet bruger tidslige events som logs og completion, men uden EHR-status eller kliniske beslutningsregler | `05_arkitektur_data_sikkerhed/data_og_sikkerhed/dataflow.md` |
| Uge 7 - clinical decision support and AI | AI- og beslutningsstøtterefleksion | Program-review/import og AI-features ligger server-side via Edge Functions; appen bør ikke beskrives som klinisk beslutningsstøtte | `05_arkitektur_data_sikkerhed/data_og_sikkerhed/edge_functions_overblik.md` |

### Rapportklar pointe

Dette kursus er vigtigt, fordi projektet ligger i gråzonen mellem fitnessapp, sundhedsdata og personlig adfærdsstøtte. Den stærke rapportvinkel er afgrænsning: Træningsmester demonstrerer praktisk interoperabilitet mellem iOS, watchOS, Live Activity, Supabase, Edge Functions og HealthKit, men ikke klinisk FHIR/HL7-integration. En topkarakterstekst bør netop være præcis om denne grænse.

## Tværgående mapping til bachelorens hovedafsnit

### UML, use cases, class diagrams og sequence diagrams

Den tekniske diagramdel bør bygges på 80540 og understøttes af 89332, når diagrammerne handler om proces eller autorisation.

Rapporten kan koble:

- Use cases: `UC-01` login/bootstrap, `UC-06` tracker, `UC-07` watch, `UC-08` training cycle, `UC-09` trainer-client, `UC-10` admin og `UC-11` onboarding/import.
- Klassediagram: `AppState`, domain models, payloads, repository protocols og Supabase repository implementations.
- Sekvensdiagram: start workout, write trackerlog, complete workout, progress training cycle, Live Activity intent write og watch sync.
- Systemdiagram: iOS app, watchOS app, Live Activity extension, Supabase Postgres/Auth/Storage, Edge Functions, StoreKit, HealthKit og OpenAI/Stripe kun server-side.

Den stærke analyse er at vise, at diagrammerne forklarer konkrete problemer: afvigelse fra plan, sikker dataadgang og flere klientflader.

### System architecture

Systemarkitekturen bør fremstilles som et lagdelt system:

| Lag | Rapportforklaring |
| --- | --- |
| Presentation | SwiftUI features, watch views og Live Activity UI |
| Application state | AppState, navigation, auth, profile mode og runtime state |
| Domain | Typed Swift models, payloads og routes |
| Data access | Repository-protokoller og Supabase-klient |
| Integration | WatchConnectivity, ActivityKit, StoreKit, HealthKit og Edge Functions |
| Backend/security | Postgres, RLS, RPC, views, storage og function runtime |

Koblingen til 80540 er systemarkitektur og software engineering. Koblingen til 89332 er interoperabilitet og kontrollerede dataformatgrænser.

### Database, SQL og XML

Databaseafsnittet bør koble 80540's database-/SQL-moduler til Supabase-implementeringen:

- Relationel modellering: `plan`, `workout`, `plan_workouts`, `workout_exercises`, `trackerlog`, `workout_completion_events`, `training_cycle_*`.
- SQL: RLS policies, views, RPC'er og constraints.
- Data quality: forskellen på fulde sætlogs og completion-events.
- XML: ikke implementeret som primært format, men relevant som sammenligningspunkt for strukturerede sundhedsdataformater. Rapporten bør skrive, at Træningsmester primært bruger Swift Codable/JSON/PostgREST, mens XML/FHIR/HL7 hører til interoperabilitetsrefleksionen.

### Projektledelse

Projektledelsesafsnittet bør koble 77437 til:

- Scopekontrol: bachelorens hovedproblem er motivation/progression, ikke "alle appfeatures".
- Risiko: dataadgang, RLS, service-role, cross-user adgang, anonymisering, TestFlight og releaseparathed.
- Leveranceplan: app, bilag, testlogs, screenshots, SQL-inventory og rapportklar dokumentation.
- Benefits: lavere træningsfriktion, mere realistisk progression og sikrere samarbejdsflows.
- Modenhed: hvad er beta-validitet, og hvad mangler før produktion.

### Interaktionsdesign

Interaktionsdesignafsnittet bør koble 72545 til:

- Brugerens kontekst: træning foregår under fysisk belastning, ofte med lav opmærksomhed.
- Designrespons: tracker-off, watch, Live Activity og tydelig completion.
- Evaluering: TestFlight og anonymiseret feedback.
- Begrænsning: der er ikke nok langtidsdata til at dokumentere forbedret adherence.

### Kvalitative og kvantitative metoder

Metodeafsnittet bør koble 79772 til:

- Kvalitativ analyse: anonymiserede temaer fra beta-feedback.
- Digitale metoder: TestFlight, Messenger-temaer, screenshots og repoartefakter.
- Spørgeskema/interviewlogik: brug, værdi, friktion, betalingsvillighed og prioritering.
- Etik: pseudonymisering, samtykke, privat råmappe og ingen public persondata.
- Kvantitativ begrænsning: TestFlight-builds og eventuelle tællinger kan beskrive proces, men ikke statistisk effekt.

### Bachelorprojektkrav

Bachelorprojektsporet bør bruges til at holde rapporten skarp:

- Hovedspørgsmålet skal styre featureudvælgelsen.
- Implementeringen skal være evidens, ikke hele argumentet.
- Bilag skal understøtte påstande med traceability, diagrammer, tests og anonymiseret brugerindsigt.
- Kritisk refleksion skal være tydeligere end produktmarkedsføring.

### DCR, BPMN, interoperabilitet, data quality, FHIR og HL7

Sundhedsdataafsnittet bør koble 89332 til:

- BPMN: trackerflowets rækkefølge fra workout-start til completion og historik.
- DCR: autorisationsregler for auth, RLS, admin, trainer-client, Live Activity og service-role boundary.
- Interoperabilitet: iOS, watchOS, Live Activity, Supabase, Edge Functions og HealthKit.
- Data quality: tradeoff mellem lav friktion og detaljeret logging.
- FHIR/HL7: ikke implementeret; bruges som kritisk perspektiv på, hvad der ville kræves ved klinisk datadeling.

## Kritisk vurdering i forhold til topkarakter

### Stærkt nok til topkarakter

| Styrke | Hvorfor det er stærkt | Rapportkrav |
| --- | --- | --- |
| Tydelig problem-case-kobling | Problemformuleringen om motivation og afvigelser er direkte implementeret i tracker-off, completion-events og cycle runtime | Rapporten skal vise sporbarhed fra problem til krav og kode |
| Solid software engineering-kæde | Projektet har krav, use cases, arkitektur, repositories, Supabase schema, RLS, tests og diagrammer | Diagrammer og tests skal forklares, ikke kun vedlægges |
| Sikkerhedsbevidst backendmodel | Anon key, RLS, Edge Functions og service-role boundary er stærke bachelorargumenter | Rapporten skal dokumentere konkrete policies/RPC'er og failure modes |
| Reelt interaktionsdesignrationale | Watch, Live Activity og tracker-off er designet til brugerens kontekst under træning | Rapporten skal knytte UX-valg til brugerindsigt og friktion |
| Etisk håndtering af brugerdata | Public bilag undgår persondata og bruger anonymiserede temaer | Rapporten skal beskrive samtykke, redaktion og databegrænsninger |
| Tværfaglig kursusforankring | Software, projektledelse, metode, UX og sundhedsdata er alle konkret repræsenteret | Mappingen skal bruges aktivt i kapitlerne, ikke som appendiks alene |

### Huller der kræver egen refleksion

| Hul | Risiko hvis det ignoreres | Nødvendig refleksion |
| --- | --- | --- |
| Begrænset kvantitativ evidens | Rapporten kan komme til at overpåstå effekt på motivation/adherence | Beskriv beta som kvalitativ/designbaseret evaluering og foreslå længere effektmåling |
| Retrospektiv projektledelse | Projektstyringen kan ligne efterrationalisering | Vær ærlig om hvilke planer der fandtes før, og hvilke der er rekonstrueret fra logs |
| Mange features i forhold til ét hovedproblem | Rapporten kan fremstå som produktkatalog | Prioritér tracker-off, completion, cycle runtime, watch/Live Activity og sikker dataadgang som problemrelevante |
| Klinisk interoperabilitet er ikke implementeret | FHIR/HL7 kan blive overdrevet | Skriv klart, at HealthKit er fitness-/samtykkeintegration, ikke EHR/FHIR/HL7 |
| AI-features er sekundære | AI kan stjæle fokus fra problemformuleringen | Placer AI/import som støttefunktion og diskuter server-side sikkerhed frem for modelperformance |
| Datakvalitet vs friktion | Tracker-off reducerer detaljeringsgrad | Gør tradeoffet eksplicit: completion-events forbedrer adherence-/gennemførelsesdata, men ikke sætdetaljer |
| UX-effekt ikke langtidsmålt | Designintention kan forveksles med dokumenteret resultat | Brug feedback som plausibilitet og kravvalidering, ikke som endeligt bevis |

## Anbefalet brug i selve rapporten

1. Brug 80540 som rygrad for teknisk metode: krav, UML, arkitektur, database, SQL og test.
2. Brug 72545 og 79772 til at begrunde, hvordan brugerindsigt og designbeslutninger hænger sammen.
3. Brug 77437 til en kort, kritisk projektstyringssektion med scope, risiko og releaseparathed.
4. Brug 89332 til at vise moden dataforståelse: DCR/BPMN, interoperabilitet, datakvalitet og klar afgrænsning fra kliniske standarder.
5. Brug 88370 til at holde rapporten problemstyret og kritisk.

Den samlede topkarakterstrategi er at fremstille Træningsmester som et veldokumenteret software- og designprojekt, hvor de tekniske valg er metodisk begrundede og kritisk afgrænsede. Det stærkeste argument er ikke, at appen har mange funktioner, men at de centrale funktioner realiserer en sammenhængende idé: fleksibel progression uden at straffe brugeren for realistiske afvigelser.
