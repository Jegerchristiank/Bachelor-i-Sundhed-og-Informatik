# Skrivematrix for rapportens første kapitler

Dato: 2026-04-30  
Status: internt arbejdsdokument til skriveiterationer. Filen skal ikke inputtes i `main.tex` og må ikke omtales synligt i rapporten.

## Absolutte rammer

### Autoritativt hovedspørgsmål

Rapportens styrende spørgsmål er:

> Hvordan kan en digital træningsapp designes og implementeres, så programstruktur, progression og feedback understøtter vedvarende motivation og fleksibel håndtering af afvigelser fra et planlagt træningsforløb uden at øge risikoen for demotivation og frafald?

### Caseafgrænsning

Træningsmester er en design- og implementeringscase. SwiftUI, Supabase, watchOS, Live Activity, trænerfunktioner, adminfunktioner og import/AI er tekniske og organisatoriske midler til at undersøge hovedspørgsmålet. De må ikke blive konkurrerende hovedproblemer.

### Skriveregel for rapporttekst

Synlig rapporttekst må kun henvise til artikler, standarder, kursusmateriale registreret i referencebiblioteket, appen, synlige figurer/tabeller og anonymiserede undersøgelser, der faktisk er indsat i bilag. Interne arbejdsfiler, mapper, lokale PDF-statusser, Overleaf/BibTeX-arbejdsgange, approval-matricer og lokale stier må ikke omtales synligt.

### Internt skrivegrundlag

Følgende interne filer må bruges til at skrive, men må ikke citeres eller omtales direkte i rapporten:

- `AGENTS.md`
- `NAVIGATOR.md`
- `referencer.md`
- `kildesoegning.tex`
- `billedbilag.tex`
- `Materiale/traeningsmester-2026-04-28/01_rapportgrundlag/problemformulering/problemformulering_autoritativ.md`
- `Materiale/traeningsmester-2026-04-28/01_rapportgrundlag/rapportstruktur/rapportafsnit_mapping.md`
- `Materiale/traeningsmester-2026-04-28/03_kursus_og_metode/kursusmapping.md`
- `Materiale/traeningsmester-2026-04-28/06_verifikation/quality_gate_review.md`

Når disse filer bruges, skal indholdet omsættes til rapporttekst som faglig analyse, ikke som dokumenthenvisninger.

## Rød tråd

De første kapitler skal føre læseren fra et bredt problem til en præcis undersøgelsesramme:

1. **Indledning** etablerer problemet: digitale træningsapps kan understøtte fysisk aktivitet og træningsadfærd, men effekten afhænger af engagement, kvalitet, friktion og evnen til at håndtere realistiske afvigelser.
2. **Problemformulering og afgrænsning** oversætter problemet til rapportens hovedspørgsmål og afgrænser Træningsmester som case frem for som produktpitch.
3. **Teoretisk og faglig ramme** giver de begreber, rapporten senere bruger til at analysere motivation, behavior change, appkvalitet, progression, interaktionsdesign, datakvalitet og sikkerhed.
4. **Metode** forklarer, hvordan projektet undersøges: som design- og implementeringscase med kildesøgning, dokument-/artefaktanalyse, anonymiseret beta-feedback, bilagsmateriale og teknisk verifikation.

Den røde tråd skal være: **fra brugerens realistiske træningsadfærd til et systemdesign, der gør afvigelser håndterbare uden at gøre dem til nederlag.**

## Evidenspolitik

| Evidenstype | Brug i rapporten | Må ikke bruges til |
| --- | --- | --- |
| App-/trackerstudier | Samlet evidensspor om digitale interventioner, appkvalitet, self-monitoring, feedback og wearables. | Direkte bevis for, at Træningsmester forbedrer motivation, adherence eller sundhedseffekt. |
| Træningsfaglige kilder | Fagligt grundlag for programstruktur, progression, autoregulering, deload og fleksibel justering. | Dokumentation for appens effekt eller brugeraccept. |
| Teori om motivation og behavior change | Begreber til at forklare autonom motivation, engagement, frafald, feedback og adfærdsdesign. | Påstande om at en bestemt UI-funktion alene skaber varig adfærdsændring. |
| Kursusmateriale | Metodisk og faglig støtte til design, metode, databehandling, etik, evaluering, interoperabilitet og procesmodellering. | Empirisk effektbevis for Træningsmester. |
| Tekniske primærkilder | Dokumentation for platformvalg, RLS, API-sikkerhed, Live Activity, Watch Connectivity, HealthKit og databeskyttelse. | Sundhedsfaglig effekt eller brugerudbytte. |
| Beta-feedback | Anonymiseret design- og brugerindsigt om friktion, behov, forståelighed og iteration. | Statistisk generalisering, klinisk effekt eller dokumenteret langtidsadherence. |
| Tests og bilag | Verifikation af implementering, build, udvalgte flows, datamodel, sikkerhedsdesign og UI-dokumentation. | Fuld produktionsmodenhed, komplet security proof eller uafhængig clean CI-verifikation. |

### Formuleringsstandard

- Skriv: "studier peger på", "kan understøtte", "giver et fagligt grundlag for", "i denne case undersøges".
- Undgå: "Træningsmester beviser", "appen øger adherence", "brugerne bliver motiverede", "sikkerheden er fuldt dokumenteret".
- Når en påstand handler om effekt, skal den knyttes til litteraturen generelt.
- Når en påstand handler om Træningsmester, skal den knyttes til designrationale, implementering, bilag eller anonymiseret feedback.

## Kapitel 1: Indledning

### Kapitelmål

Indledningen skal gøre det klart, hvorfor problemet er relevant, og hvorfor en digital træningsapp er en rimelig, men ikke triviel, case. Den skal introducere spændingen mellem planlagt træning og faktisk træningsadfærd: brugere springer pas over, træner uden fuld logging, ændrer belastning, mister overblik eller oplever friktion i appen. Indledningen skal ende i et behov for et system, der understøtter progression og feedback uden at straffe afvigelser.

### Hovedpointe

Digitale træningsapps kan være relevante for fysisk aktivitet og træningsadfærd, men deres værdi afhænger ikke kun af at vise planer og registrere data. De skal også understøtte autonom motivation, effektivt engagement, lav friktion og fleksibel progression, fordi realistisk træning sjældent følger en perfekt lineær plan.

### Delargumenter i anbefalet rækkefølge

1. **Fysisk aktivitet og træningsadfærd er ikke kun et spørgsmål om information.** Brugeren skal kunne fastholde motivation og opleve autonomi, kompetence og mening i forløbet.  
   Primære kilder: cite:teixeira2012_sdt_exercise, cite:yardley2016_effective_engagement_dbci.

2. **Digitale interventioner har potentiale, men engagement og frafald er centrale problemer.** Brug af apps og trackere kan understøtte aktivitet, men lav vedvarende brug, friktion og appkvalitet begrænser effekten.  
   Primære kilder: cite:eysenbach2005_law_of_attrition, cite:laranjo2021_apps_trackers_meta, cite:romeo2019_smartphone_apps_pa_meta, cite:brickwood2019_wearable_trackers_meta.

3. **Træningsapps skal vurderes kritisk som apps, ikke kun som sundhedsinterventioner.** Kvalitet, funktionalitet, engagement, self-monitoring, feedback og behavior change-komponenter har betydning for, om appen reelt understøtter brugerens adfærd.  
   Primære kilder: cite:bondaronek2018_quality_pa_apps, cite:kebede2018_evidence_informed_pa_apps, cite:stoyanov2015_mobile_app_rating_scale, cite:middelweerd2014_apps_physical_activity.

4. **Styrketræning kræver progression og justering.** Et træningsprogram er ikke kun en kalender; det rummer valg om volumen, intensitet, øvelser, progression, deload og regulering efter faktisk performance.  
   Primære kilder: cite:acsm2009_progression_models, cite:currier2026_acsm_resistance_training, cite:greig2020_autoregulation_resistance_training, cite:larsen2021_autoregulation_systematic_review.

5. **Rapportens case er relevant, fordi den samler disse problemer i ét systemdesign.** Træningsmester undersøges som en app, hvor plan, tracker, completion, feedback, watchOS/Live Activity og datamodel skal understøtte fleksibel progression frem for kun perfekt registrering.  
   Synlige bilag: label:fig:tm-ios-home-ready, label:fig:tm-ios-tracker-active, label:fig:tm-ios-home-completion-delay, label:fig:tm-ios-home-next-training, label:fig:tm-tracker-completion-summary.

### Primære citation keys

- Motivation og engagement: cite:teixeira2012_sdt_exercise, cite:eysenbach2005_law_of_attrition, cite:yardley2016_effective_engagement_dbci.
- App-/tracker-evidens: cite:laranjo2021_apps_trackers_meta, cite:romeo2019_smartphone_apps_pa_meta, cite:brickwood2019_wearable_trackers_meta, cite:metzendorf2024_mhealth_obesity_cochrane.
- Appkvalitet og BCT: cite:bondaronek2018_quality_pa_apps, cite:kebede2018_evidence_informed_pa_apps, cite:stoyanov2015_mobile_app_rating_scale, cite:middelweerd2014_apps_physical_activity.
- Træningsprogression: cite:acsm2009_progression_models, cite:currier2026_acsm_resistance_training, cite:greig2020_autoregulation_resistance_training.

### Relevante kursusspor

- 72545 Interaktionsdesign: brugerens kontekst, friktion, prototyper og evaluering. Citationer kan bruges senere via cite:hornbaek2024_brugerundersoegelser, cite:hornbaek2024_prototyper og cite:hornbaek2024_evaluering, men indledningen bør ikke overbelastes med kursuscitater.
- 79772 Kvantitative og kvalitative undersøgelsesmetoder: præcision om, at brugerindsigt ikke er statistisk effektmåling.
- 88370 Bachelorprojekt: problemstyret fremstilling, ikke produktpitch.

### Relevante bilag og synlige henvisninger

- Appens aktuelle UI: label:fig:tm-ios-home-ready, label:fig:tm-ios-programmer, label:fig:tm-ios-tracker-active.
- Afvigelses- og completionflow: label:fig:tm-ios-home-completion-delay, label:fig:tm-ios-home-next-training, label:fig:tm-tracker-completion-summary.
- Kildesøgningens appspor kan nævnes senere i metode, ikke nødvendigvis i indledningen: label:tab:kildesoegning-appspor.

### Hvad kapitlet ikke må påstå

- At Træningsmester dokumenteret forbedrer fysisk aktivitet, motivation eller adherence.
- At appen er en klinisk intervention eller en journal-/behandlingsløsning.
- At beta-feedback generaliserer til alle motionister.
- At flere funktioner i sig selv gør appen bedre.

### Overgang til næste kapitel

Indledningen skal afslutte med, at denne problematik kræver en præcis problemformulering og en klar caseafgrænsning. Overgangen bør pege på, at rapporten ikke undersøger "om appen virker" i klinisk eller statistisk forstand, men hvordan et konkret design- og implementeringsarbejde kan understøtte de relevante mekanismer.

### Acceptkriterier for første version

- Læseren forstår problemet uden at kende Træningsmester på forhånd.
- Indledningen bruger mindst tre kildegrupper: motivation/engagement, app-/tracker-evidens og træningsprogression.
- Træningsmester introduceres kort som case, ikke som produktpræsentation.
- Ingen interne arbejdsfiler, mapper eller lokale processer omtales.
- Claims om effekt er forsigtige og koblet til litteratur, ikke til appens egen dokumentation.

## Kapitel 2: Problemformulering og afgrænsning

### Kapitelmål

Kapitlet skal låse rapportens undersøgende ramme. Det skal præsentere hovedspørgsmålet, forklare hvorfor det er afgrænset til design og implementering, og placere Træningsmester som case. Kapitlet skal også gøre det tydeligt, hvilke dele af appen der er centrale for problemformuleringen, og hvilke der kun er støttefunktioner.

### Hovedpointe

Rapportens problem er ikke at bygge flest mulige funktioner, men at undersøge hvordan digital programstruktur, progression og feedback kan designes, så brugeren kan håndtere realistiske afvigelser uden datatab, unødig friktion eller demotiverende feedback.

### Anbefalet struktur

1. **Problemformulering.** Indsæt hovedspørgsmålet ordret og kort begrund, at det kombinerer sundhedsadfærd, interaktionsdesign og softwareimplementering.
2. **Underspørgsmål.** Brug fire underspørgsmål:
   - Hvordan modelleres plan, workout, trackerlog, completion-events og cycle runtime, så faktisk træningsadfærd kan afvige fra den lineære plan uden datatab?
   - Hvordan kan UI og interaktionsdesign reducere friktion under træning, herunder tracker-off flow, watchOS og Live Activity?
   - Hvordan kan Supabase, RLS, typed repositories og Edge Functions understøtte fleksible brugerflows uden at eksponere privilegerede credentials?
   - Hvordan kan beta-feedback, screenshots, buildlogs, tests og diagrammer bruges som evidens for designvalg og implementering?
3. **Caseafgrænsning.** Forklar at Træningsmester er en native SwiftUI-case med Supabase-backend, watchOS, Live Activity og server-side funktioner, men at disse kun behandles i det omfang de belyser hovedspørgsmålet.
4. **Faglig afgrænsning.** Afgræns fra klinisk effektstudie, kommerciel produktlancering, fuld sikkerhedscertificering og national sundhedsdata-/FHIR-integration.
5. **Bidrag.** Formuler bidraget som en dokumenteret design- og implementeringsmodel for fleksibel progression og feedback, understøttet af bilag, kilder og teknisk verifikation.

### Primære citation keys

- Problemets adfærdsmæssige begrundelse: cite:teixeira2012_sdt_exercise, cite:eysenbach2005_law_of_attrition, cite:yardley2016_effective_engagement_dbci.
- App- og trackerbaggrund: cite:laranjo2021_apps_trackers_meta, cite:romeo2019_smartphone_apps_pa_meta, cite:brickwood2019_wearable_trackers_meta.
- Træningsfaglig afgrænsning: cite:acsm2009_progression_models, cite:currier2026_acsm_resistance_training, cite:greig2020_autoregulation_resistance_training.
- Databeskyttelse og sikkerhed som caseafgrænsning: cite:europeanparliament2016_gdpr, cite:owasp2024_masvs, cite:supabase_rls_docs.

### Relevante kursusspor

- 88370 Bachelorprojekt: rapporten skal være problemstyret, dokumenteret og kritisk.
- 80540 Software Development for Digital Health: krav, use cases, arkitektur, database, SQL og test som teknisk metode.
- 77437 IT-projektledelse: scopekontrol, risiko, releaseparathed og undgåelse af scope creep.
- 79772 Metode: skelnen mellem designcase, artefaktanalyse og brugerindsigt.

### Relevante bilag og synlige henvisninger

- Use cases: label:tab:tm-use-cases.
- Kravsporbarhed: label:tab:tm-krav-traceability.
- Systemkontekst: label:fig:tm-system-context.
- Datamodel og completion: label:fig:tm-data-model-er, label:fig:tm-data-model-er-left, label:fig:tm-data-model-er-middle, label:fig:tm-tracker-completion-summary.
- Verifikationsbegrænsninger: label:tab:tm-test-traceability.

### Hvad kapitlet ikke må påstå

- At rapporten måler appens sundhedseffekt.
- At alle appfeatures er lige centrale.
- At watchOS, Live Activity, trainer/admin eller AI/import er selvstændige hovedproblemer.
- At appen er produktionscertificeret, klinisk valideret eller fuldt sikkerhedsbevist.
- At lukkede eller private rådata indgår direkte i rapporten.

### Overgang til næste kapitel

Kapitlet skal afslutte med, at problemformuleringen kræver en tværfaglig ramme. Den næste del skal derfor etablere begreberne for motivation, digital behavior change, appkvalitet, træningsprogression, interaktionsdesign og datakvalitet.

### Acceptkriterier for første version

- Hovedspørgsmålet står ordret og tydeligt.
- Caseafgrænsningen gør Træningsmester til middel, ikke mål.
- De fire underspørgsmål matcher senere kapitler og bilag.
- Afgrænsningerne er eksplicitte nok til at forhindre overpåstande.
- Kapitlet forbereder teorikapitlet uden at begynde at analysere alle tekniske detaljer.

## Kapitel 3: Teoretisk og faglig ramme

### Kapitelmål

Kapitlet skal give rapporten et samlet begrebsapparat. Det skal ikke være en løs litteraturgennemgang, men en ramme der forklarer, hvilke faglige begreber der senere bruges til at vurdere Træningsmesters design og implementering.

### Hovedpointe

Træningsmester skal forstås i krydsfeltet mellem motivation, adfærdsdesign, appkvalitet, træningsprogression, interaktionsdesign og data-/sikkerhedsarkitektur. Et godt digitalt træningssystem skal både understøtte adfærd, træningsfaglig progression og teknisk pålidelighed.

### Anbefalet struktur

#### 3.1 Motivation, adherence og effektivt engagement

Fokus: autonom motivation, behovsstøtte, frafald, digitalt engagement og forskellen mellem skærmtid og målrettet brug.

Primære kilder: cite:teixeira2012_sdt_exercise, cite:eysenbach2005_law_of_attrition, cite:yardley2016_effective_engagement_dbci.

Brug i senere kapitler: begrunder hvorfor feedback, completion og fleksibel afvigelseshåndtering skal vurderes som motivationsstøtte, ikke kun som datalogik.

#### 3.2 Behavior change, feedback og persuasive systems

Fokus: COM-B, Behaviour Change Wheel, BCT Taxonomy, self-monitoring, feedback, prompts, goals, action planning, tailoring og system credibility.

Primære kilder: cite:michie2011_behaviour_change_wheel, cite:michie2013_bct_taxonomy_v1, cite:oinaskukkonen2009_persuasive_systems_design, cite:nahumshani2018_jitai_mobile_health.

Brug i senere kapitler: gør det muligt at navngive appens mekanismer uden at påstå effekt. Trackerlog, completion, næste handling, reminders/statusflader og feedback skal analyseres som BCT-/PSD-lignende designvalg.

#### 3.3 App-effekt, appkvalitet og wearables

Fokus: hvad litteraturen siger om smartphone-apps, activity trackers, wearables, appbaserede interventioner, appkvalitet og BCT-indhold i fysiske aktivitetsapps.

Primære kilder: cite:laranjo2021_apps_trackers_meta, cite:romeo2019_smartphone_apps_pa_meta, cite:floresmateo2015_mobile_apps_weight_pa_meta, cite:brickwood2019_wearable_trackers_meta, cite:bondaronek2018_quality_pa_apps, cite:kebede2018_evidence_informed_pa_apps, cite:stoyanov2015_mobile_app_rating_scale, cite:conroy2014_bct_top_ranked_pa_apps.

Brug i senere kapitler: danner kritisk baggrund for at vurdere Træningsmester som app, ikke bare som teknisk system. MARS og appkvalitetslitteraturen kan bruges til at diskutere funktionalitet, engagement, æstetik og informationskvalitet.

#### 3.4 Træningsprogrammering, progression og autoregulering

Fokus: progression i styrketræning, volumen/intensitet, periodisering, deload, readiness, autoregulering og justering efter faktisk træning.

Primære kilder: cite:acsm2009_progression_models, cite:currier2026_acsm_resistance_training, cite:greig2020_autoregulation_resistance_training, cite:larsen2021_autoregulation_systematic_review, cite:plotnikoff2023_ecofit_rct.

Brug i senere kapitler: begrunder hvorfor en app bør skelne mellem plan, faktisk logging, completion og næste træningshandling. Tracker-off completion kan forklares som et tradeoff mellem datadetaljer og lav friktion.

#### 3.5 Interaktionsdesign og brugerens træningskontekst

Fokus: brugerundersøgelser, prototyping, evaluering, tænkehøjt-test, usability, friktion og kontekstfølsomme grænseflader.

Primære kilder: cite:hornbaek2024_brugerundersoegelser, cite:hornbaek2024_prototyper, cite:hornbaek2024_evaluering, cite:hornbaek2024_taenkehoejt_eksperimenter.

Brug i senere kapitler: forklarer hvorfor Home, tracker, tracker-off, watchOS og Live Activity skal vurderes som interaktionsdesign under fysisk aktivitet, ikke bare som skærme.

#### 3.6 Datakvalitet, interoperabilitet og sikkerhed som designbetingelser

Fokus: datakvalitet, kontekstuel databrug, relationel model, DCR/BPMN, interoperabilitetsniveauer, RLS, service-role boundary, GDPR og mobile security.

Primære kilder: cite:mohammed2025_five_facets_data_quality, cite:vanderalst2009_declarative_workflows, cite:benson2016_principles_health_interoperability, cite:zajac2026_data_quality_interoperability, cite:ku2026_dcr_bpmn_modeling, cite:owasp2024_masvs, cite:europeanparliament2016_gdpr, cite:supabase_rls_docs.

Brug i senere kapitler: gør det muligt at diskutere completion-events, trackerlog, RLS, HealthKit-afgrænsning og Edge Functions som faglige designvalg, ikke kun implementeringsdetaljer.

### Relevante kursusspor

- 72545 Interaktionsdesign: brugerforståelse, prototyper, evaluering og tænkehøjt.
- 79772 Kvantitative og kvalitative undersøgelsesmetoder: metodeposition, interview/spørgeskema, digitale metoder, etik og analyse.
- 89332 Sundhedsdata og interoperabilitet: data quality, DCR/BPMN, interoperabilitet, FHIR/HL7-afgrænsning.
- 80540 Software Development for Digital Health: krav, use cases, systemarkitektur, database og test som softwarefaglig ramme. Må kun bruges direkte, hvis præcise citebare kursuskilder senere verificeres; ellers som intern strukturinspiration.
- 77437 IT-projektledelse: scope, risici og modenhed. Må kun bruges direkte, hvis præcise citebare kursuskilder senere verificeres; ellers som intern strukturinspiration.

### Relevante bilag og synlige henvisninger

- Kildesøgningsgrundlag: label:tab:kildesoegning-platforme, label:tab:kildesoegning-appspor, label:tab:kildesoegning-progression-data-metode, label:tab:kursusmateriale-gennemgang.
- App- og interaktionsdesign: label:fig:tm-ios-home-ready, label:fig:tm-ios-tracker-active, label:fig:tm-ios-home-current-qa.
- Progression og afvigelse: label:fig:tm-tracker-completion-summary, label:fig:tm-data-model-er-middle.
- Datamodel og sikkerhed: label:fig:tm-data-model-er, label:fig:tm-security-boundary-summary, label:tab:tm-rls-matrix.

### Hvad kapitlet ikke må påstå

- At teorierne tilsammen beviser appens effekt.
- At appkvalitet alene er det samme som sundhedseffekt.
- At mHealth- og vægttabsstudier direkte kan overføres til styrketræning.
- At HealthKit, FHIR eller HL7 er implementeret som klinisk integration.
- At sikkerhedsrammerne dokumenterer fuld sikkerhed uden flere integrationstests.

### Overgang til næste kapitel

Teorikapitlet skal afslutte med, at rammen viser, hvad der skal undersøges empirisk og teknisk i projektet: kilder, artefakter, brugerindsigt, bilag og verifikation. Det leder direkte til metodekapitlet.

### Acceptkriterier for første version

- Kapitlet er struktureret i tydelige underafsnit, ikke som en lang kildegennemgang.
- Hver kildegruppe har en klar funktion i resten af rapporten.
- Kursusmateriale bruges som faglig støtte med præcise citation keys, ikke som effektbevis.
- Der er eksplicitte broformuleringer mellem teori og Træningsmester uden at overpåstå.
- Kapitlet gør plads til senere analyse af konkrete figurer og tabeller.

## Kapitel 4: Metode

### Kapitelmål

Metodekapitlet skal forklare, hvordan rapporten undersøger problemformuleringen. Det skal gøre læseren tryg ved, at projektet ikke foregiver at være et klinisk effektstudie, men er en design- og implementeringscase med flere typer evidens: litteratur, kursusgrundlag, artefakter, bilag, anonymiseret feedback og teknisk verifikation.

### Hovedpointe

Metoden er en problemstyret kombination af scoping-kildesøgning, design-/implementeringscase, dokument- og artefaktanalyse, anonymiseret beta-feedback og teknisk verifikation. Metoden er egnet til at vurdere designvalg og implementeringskvalitet, men ikke til at konkludere statistisk effekt på motivation eller adherence.

### Anbefalet struktur

#### 4.1 Design- og implementeringscase

Forklar at Træningsmester undersøges som konkret case, hvor appens arkitektur, datamodel, UI, feedbackflows og verifikation bruges til at belyse problemformuleringen.

Synlige bilag: label:tab:tm-bilag-materialegennemgang, label:fig:tm-system-context, label:tab:tm-container-architecture.

#### 4.2 Kildesøgning

Beskriv søgningen som problemstyret scoping-søgning med flere søgeflader: KB.dk/Primo, PubMed/PMC, DOI/Crossref og udgiversider. Henvis til kildesøgningsbilaget, ikke til interne referencefiler.

Primære kilder: cite:rethlefsen2021_prisma_s, cite:mcgowan2016_press_guideline_statement.  
Synlige bilag: label:tab:kildesoegning-platforme, label:tab:kildesoegning-appspor, label:tab:kildesoegning-progression-data-metode.

#### 4.3 Kursus- og faggrundlag

Forklar at udvalgt kursusmateriale bruges som metodisk og fagligt støttepunkt for design, metode, etik og interoperabilitet. Marker klart, at kursusmaterialet ikke bruges som empirisk effektbevis.

Primære kilder: cite:hornbaek2024_brugerundersoegelser, cite:hornbaek2024_prototyper, cite:hornbaek2024_evaluering, cite:gjoedsboel2025_metoder_videnskabsteori, cite:grundtvig2025_analyse_data, cite:clotworthy2025_persondata_datasikkerhed, cite:zajac2026_data_quality_interoperability, cite:ku2026_dcr_bpmn_modeling.  
Synlige bilag: label:tab:kursusmateriale-gennemgang.

#### 4.4 Dokument- og artefaktanalyse

Beskriv hvordan appens screenshots, diagrammer, use cases, datamodel, sikkerhedstabeller og verifikationstabeller analyseres som dokumentation for design og implementering.

Synlige bilag: label:fig:tm-ios-home-ready, label:fig:tm-ios-tracker-active, label:fig:tm-data-model-er, label:fig:tm-tracker-completion-summary, label:tab:tm-use-cases, label:tab:tm-krav-traceability, label:tab:tm-rls-matrix.

#### 4.5 Anonymiseret beta-feedback og brugerindsigt

Beskriv feedback som kvalitativ, anonymiseret og designorienteret brugerindsigt. Brug den til at identificere friktion, behov og designimplikationer, ikke til statistisk effektmåling.

Primære metodekilder: cite:gjoedsboel_grundtvig2025_interview, cite:grundtvig2025_digitale_metoder, cite:grundtvig2025_analyse_data, cite:clotworthy2025_etik_kvalitet_forskning.  
Synlige bilag: label:tab:tm-testflight-timeline, label:tab:tm-beta-feedback.

#### 4.6 Teknisk verifikation og begrænsninger

Beskriv test, build, screenshotdokumentation, sikkerhedsdesign og kendte gaps. Formuler verifikation som dokumentation for implementeringsstatus, ikke som fuld produktionsklarhed.

Primære tekniske kilder: cite:owasp2024_masvs, cite:supabase_rls_docs, cite:supabase_securing_api_docs, cite:apple_swiftui_docs, cite:apple_activitykit_live_data_docs, cite:apple_watchconnectivity_docs.  
Synlige bilag: label:tab:tm-test-traceability, label:fig:tm-security-boundary-summary, label:fig:tm-watch-sync-sequence, label:fig:tm-live-activity-idempotency-sequence.

### Relevante kursusspor

- 79772 Metode: videnskabsteori, interview/spørgeskema, digitale metoder, etik, analyse og databehandling.
- 72545 Interaktionsdesign: brugerundersøgelser, prototyper og evaluering.
- 89332 Sundhedsdata og interoperabilitet: datakvalitet, DCR/BPMN og interoperabilitetsafgrænsning.
- 80540 Software Development for Digital Health: intern metodeinspiration for krav, use cases, database, SQL og test. Direkte citation kræver verificeret citation key; ellers bruges de synlige bilag og tekniske kilder.

### Hvad kapitlet ikke må påstå

- At projektet er et randomiseret studie eller et systematisk review.
- At beta-feedback er repræsentativt eller statistisk generaliserbart.
- At alle tests er kørt i clean CI.
- At Supabase/admin/cross-user sikkerhed er fuldt integrationstestet.
- At watchOS og Live Activity runtime er dokumenteret visuelt, hvis det kun er dokumenteret via build/test/arkitektur.
- At lukkede kursusfiler eller private kommunikationsdata er en synlig del af rapportens evidens.

### Overgang til næste kapitel

Metodekapitlet skal afslutte med, at denne metode gør det muligt at omsætte problemformuleringen til krav og use cases. Næste kapitel bør derfor begynde med at vise, hvordan motivation, progression, friktion og sikker dataadgang bliver til konkrete funktionelle og ikke-funktionelle krav.

### Acceptkriterier for første version

- Metoden er ærlig om evidensniveau og begrænsninger.
- Kildesøgningen beskrives som transparent scoping-søgning med flere søgeflader.
- Kursusmateriale er placeret som faglig/metodisk støtte, ikke som effektbevis.
- Beta-feedback er anonymiseret og kvalitativt afgrænset.
- Teknisk verifikation nævner både dokumenteret status og kendte gaps.
- Der henvises kun til synlige bilag og formelle kilder i rapportteksten.

## Kildepakker til skrivearbejdet

| Påstandstype | Førstevalg af citation keys |
| --- | --- |
| Autonom motivation og fysisk aktivitet | cite:teixeira2012_sdt_exercise |
| Digital frafaldsproblematik | cite:eysenbach2005_law_of_attrition |
| Effektivt engagement | cite:yardley2016_effective_engagement_dbci |
| Behavior change framework | cite:michie2011_behaviour_change_wheel, cite:michie2013_bct_taxonomy_v1 |
| Persuasive/digital feedback | cite:oinaskukkonen2009_persuasive_systems_design, cite:nahumshani2018_jitai_mobile_health |
| Apps og activity trackers | cite:laranjo2021_apps_trackers_meta, cite:romeo2019_smartphone_apps_pa_meta, cite:brickwood2019_wearable_trackers_meta |
| Appkvalitet og BCT-indhold | cite:stoyanov2015_mobile_app_rating_scale, cite:bondaronek2018_quality_pa_apps, cite:kebede2018_evidence_informed_pa_apps, cite:middelweerd2014_apps_physical_activity |
| Fitnessapp-/træningsnære interventioner | cite:direito2015_aimfit_rct, cite:plotnikoff2023_ecofit_rct |
| Styrketræningsprogression | cite:acsm2009_progression_models, cite:currier2026_acsm_resistance_training |
| Autoregulering | cite:greig2020_autoregulation_resistance_training, cite:larsen2021_autoregulation_systematic_review |
| Kildesøgningsmetode | cite:rethlefsen2021_prisma_s, cite:mcgowan2016_press_guideline_statement |
| Interaktionsdesignkursus | cite:hornbaek2024_brugerundersoegelser, cite:hornbaek2024_prototyper, cite:hornbaek2024_evaluering, cite:hornbaek2024_taenkehoejt_eksperimenter |
| Metodekursus | cite:gjoedsboel2025_metoder_videnskabsteori, cite:gjoedsboel_grundtvig2025_interview, cite:grundtvig2025_analyse_data, cite:grundtvig2025_digitale_metoder, cite:clotworthy2025_persondata_datasikkerhed, cite:clotworthy2025_etik_kvalitet_forskning |
| Datakvalitet og interoperabilitet | cite:mohammed2025_five_facets_data_quality, cite:zajac2026_data_quality_interoperability, cite:benson2016_principles_health_interoperability |
| Procesmodellering | cite:vanderalst2009_declarative_workflows, cite:ku2026_dcr_bpmn_modeling |
| Platform, sikkerhed og privacy | cite:apple_swiftui_docs, cite:apple_activitykit_live_data_docs, cite:apple_hig_live_activities, cite:apple_watchconnectivity_docs, cite:apple_healthkit_docs, cite:supabase_rls_docs, cite:supabase_securing_api_docs, cite:owasp2024_masvs, cite:europeanparliament2016_gdpr |

## Bilagspakker til skrivearbejdet

| Rapportbrug | Synlige labels |
| --- | --- |
| Appens hovedflows | label:fig:tm-ios-home-ready, label:fig:tm-ios-programmer, label:fig:tm-ios-tracker-active, label:fig:tm-ios-home-current-qa |
| Completion og næste handling | label:fig:tm-ios-home-completion-delay, label:fig:tm-ios-home-next-training, label:fig:tm-tracker-completion-summary |
| System og arkitektur | label:fig:tm-system-context, label:tab:tm-container-architecture |
| Datamodel | label:fig:tm-data-model-er, label:fig:tm-data-model-er-left, label:fig:tm-data-model-er-middle, label:fig:tm-data-model-er-right, label:tab:tm-sql-domain-overblik, label:tab:tm-sql-fields |
| Krav og use cases | label:tab:tm-use-cases, label:tab:tm-krav-traceability |
| Sikkerhed og RLS | label:fig:tm-security-boundary-summary, label:tab:tm-authorization-dcr, label:tab:tm-rls-matrix |
| Watch og Live Activity | label:fig:tm-watch-sync-sequence, label:fig:tm-live-activity-idempotency-sequence |
| Import/AI-afgrænsning | label:fig:tm-import-ai-edge-boundary |
| Beta og verifikation | label:tab:tm-testflight-timeline, label:tab:tm-beta-feedback, label:tab:tm-test-traceability |
| Kildesøgning og kursusgrundlag | label:tab:kildesoegning-platforme, label:tab:kildesoegning-appspor, label:tab:kildesoegning-progression-data-metode, label:tab:kursusmateriale-gennemgang |

## Før næste skriveiteration

1. Læs denne fil sammen med `referencer.md`, `kildesoegning.tex` og `billedbilag.tex`.
2. Skriv de fire kapitler i rækkefølge: Indledning, Problemformulering og afgrænsning, Teoretisk og faglig ramme, Metode.
3. Brug citation keys direkte i LaTeX som `\cite{...}`.
4. Brug bilagshenvisninger med `\ref{...}` eller `Figur~\ref{...}`/`Tabel~\ref{...}` i rapporten.
5. Kontrollér efter skrivning, at rapportens synlige tekst ikke omtaler interne filer, mapper, lokale referencebiblioteker eller arbejdsgange.
6. Kør XeLaTeX/LuaLaTeX-kompilering, tjek citationer, tjek figur-/tabelhenvisninger og scan PDF-tekst for interne arbejdsreferencer.
