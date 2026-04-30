# Skrivematrix for hele rapporten

Dato: 2026-04-30
Status: internt arbejdsdokument til skriveiterationer. Filen skal ikke indlæses i `main.tex` og må ikke omtales synligt i rapporten.

## Absolutte rammer

### Autoritativt hovedspørgsmål

Rapportens styrende spørgsmål er:

> Hvordan kan en digital træningsapp designes og implementeres, så programstruktur, progression og feedback understøtter vedvarende motivation og fleksibel håndtering af afvigelser fra et planlagt træningsforløb uden at øge risikoen for demotivation og frafald?

### Caseafgrænsning

Træningsmester er bachelorprojektets egenudviklede design- og implementeringscase. Case betyder her projektets egen app som undersøgelsesartefakt, ikke et eksternt eksempel. SwiftUI, Supabase, watchOS, Live Activity, trænerfunktioner, adminfunktioner og import/AI er tekniske og organisatoriske midler i appen til at undersøge hovedspørgsmålet. De må ikke blive konkurrerende hovedproblemer.

### Skriveregel for rapporttekst

Synlig rapporttekst må kun henvise til artikler, standarder, kursusmateriale registreret i referencebiblioteket, appen, synlige figurer/tabeller og anonymiserede undersøgelser, der faktisk er indsat i bilag. Interne arbejdsfiler, mapper, lokale PDF-statusser, Overleaf/BibTeX-arbejdsgange, godkendelsesmatricer og lokale stier må ikke omtales synligt.

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
- `Materiale/traeningsmester-2026-04-28/04_brugerindsigt_beta/beta_tester_rapport.md`
- `Materiale/traeningsmester-2026-04-28/05_arkitektur_data_sikkerhed/arkitektur/use_cases.md`
- `Materiale/traeningsmester-2026-04-28/05_arkitektur_data_sikkerhed/arkitektur/krav_traceability.md`
- `Materiale/traeningsmester-2026-04-28/05_arkitektur_data_sikkerhed/arkitektur/systembeskrivelse.md`
- `Materiale/traeningsmester-2026-04-28/05_arkitektur_data_sikkerhed/arkitektur/designrationale.md`
- `Materiale/traeningsmester-2026-04-28/05_arkitektur_data_sikkerhed/data_og_sikkerhed/data_og_sikkerhed_rapportklar.md`
- `Materiale/traeningsmester-2026-04-28/05_arkitektur_data_sikkerhed/data_og_sikkerhed/sikkerhedsnotat.md`
- `Materiale/traeningsmester-2026-04-28/06_verifikation/verifikationsrapport.md`
- `Materiale/traeningsmester-2026-04-28/06_verifikation/quality_gate_review.md`

Når disse filer bruges, skal indholdet omsættes til rapporttekst som faglig analyse, ikke som dokumenthenvisninger.

## Rød tråd

Rapporten skal føre læseren fra et bredt problem til en præcis egenudviklet design- og implementeringscase:

1. **Indledning** etablerer problemet: digitale træningsapps kan understøtte fysisk aktivitet og træningsadfærd, men effekten afhænger af engagement, kvalitet, friktion og evnen til at håndtere realistiske afvigelser.
2. **Problemformulering og afgrænsning** oversætter problemet til rapportens hovedspørgsmål og placerer Træningsmester som egenudviklet artefakt frem for som produktpitch.
3. **Teoretisk og faglig ramme** giver de begreber, rapporten senere bruger til at analysere motivation, adfærdsændring, appkvalitet, progression, interaktionsdesign, datakvalitet og sikkerhed.
4. **Metode** forklarer, hvordan projektet undersøges: som egenudviklet design- og implementeringscase med kildesøgning, dokument-/artefaktanalyse, anonymiseret beta-feedback, bilagsmateriale og teknisk verifikation.
5. **Krav og use cases** omsætter problemformuleringen til funktionelle og ikke-funktionelle krav, hvor fleksibel progression, lav friktion og sikker dataadgang kan spores til konkrete flows.
6. **Systemarkitektur** viser, hvordan SwiftUI, AppState, repository-lag, Supabase, RLS, Edge Functions, watchOS og Live Activity tilsammen understøtter appens kerneproblem.
7. **Interaktionsdesign** analyserer de brugerflader og flows, der skal gøre plan, tracker, completion, feedback og næste handling forståelige i en faktisk træningssituation.
8. **Data, sikkerhed og interoperabilitet** redegør for datamodellen, sikkerhedsgrænserne og afgrænsningen mellem fitnessdata, HealthKit og egentlig klinisk interoperabilitet.
9. **Implementering** forklarer de vigtigste implementeringsvalg, der realiserer fleksibel progression og feedback uden at gøre kapitlet til en filgennemgang.
10. **Test og verifikation** dokumenterer build, tests, screenshots, diagrammer og kendte begrænsninger som teknisk evidens for den udviklede app.
11. **Evaluering og brugerindsigt** bruger anonymiseret beta-feedback til at vurdere friktion, forståelighed, behov og designimplikationer.
12. **Diskussion** samler styrker, begrænsninger, evidensniveau, generaliserbarhed, sikkerhed og fremtidigt arbejde.
13. **Konklusion** svarer direkte på problemformuleringen og afgrænser, hvad projektet har vist, og hvad det ikke har dokumenteret.

Den røde tråd skal være: **fra brugerens realistiske træningsadfærd til et systemdesign, der gør afvigelser håndterbare uden at gøre dem til nederlag.**

## Evidenspolitik

| Evidenstype | Brug i rapporten | Må ikke bruges til |
| --- | --- | --- |
| App-/trackerstudier | Samlet evidensspor om digitale interventioner, appkvalitet, selvmonitorering, feedback og wearables. | Direkte bevis for, at Træningsmester forbedrer motivation, adherence eller sundhedseffekt. |
| Træningsfaglige kilder | Fagligt grundlag for programstruktur, progression, autoregulering, deload og fleksibel justering. | Dokumentation for appens effekt eller brugeraccept. |
| Teori om motivation og adfærdsændring | Begreber til at forklare autonom motivation, engagement, frafald, feedback og adfærdsdesign. | Påstande om at en bestemt UI-funktion alene skaber varig adfærdsændring. |
| Kursusmateriale | Metodisk og faglig støtte til design, metode, databehandling, etik, evaluering, interoperabilitet og procesmodellering. | Empirisk effektbevis for Træningsmester. |
| Tekniske primærkilder | Dokumentation for platformvalg, RLS, API-sikkerhed, Live Activity, Watch Connectivity, HealthKit og databeskyttelse. | Sundhedsfaglig effekt eller brugerudbytte. |
| Beta-feedback | Anonymiseret design- og brugerindsigt om friktion, behov, forståelighed og iteration. | Statistisk generalisering, klinisk effekt eller dokumenteret langtidsadherence. |
| Tests og bilag | Verifikation af implementering, build, udvalgte flows, datamodel, sikkerhedsdesign og UI-dokumentation. | Fuld produktionsmodenhed, komplet sikkerhedsbevis eller uafhængig clean CI-verifikation. |

### Formuleringsstandard

- Skriv: "studier peger på", "kan understøtte", "giver et fagligt grundlag for", "i den udviklede app undersøges".
- Undgå: "Træningsmester beviser", "appen øger adherence", "brugerne bliver motiverede", "sikkerheden er fuldt dokumenteret".
- Når en påstand handler om effekt, skal den knyttes til litteraturen generelt.
- Når en påstand handler om Træningsmester, skal den knyttes til designrationale, implementering, bilag eller anonymiseret feedback.

## Kapitel 1: Indledning

### Kapitelmål

Indledningen skal gøre det klart, hvorfor problemet er relevant, og hvorfor en digital træningsapp er et rimeligt, men ikke trivielt, udviklingsartefakt. Den skal introducere spændingen mellem planlagt træning og faktisk træningsadfærd: brugere springer pas over, træner uden fuld logging, ændrer belastning, mister overblik eller oplever friktion i appen. Indledningen skal ende i et behov for et system, der understøtter progression og feedback uden at straffe afvigelser.

### Hovedpointe

Digitale træningsapps kan være relevante for fysisk aktivitet og træningsadfærd, men deres værdi afhænger ikke kun af at vise planer og registrere data. De skal også understøtte autonom motivation, effektivt engagement, lav friktion og fleksibel progression, fordi realistisk træning sjældent følger en perfekt lineær plan.

### Delargumenter i anbefalet rækkefølge

1. **Fysisk aktivitet og træningsadfærd er ikke kun et spørgsmål om information.** Brugeren skal kunne fastholde motivation og opleve autonomi, kompetence og mening i forløbet.
   Primære kilder: cite:teixeira2012_sdt_exercise, cite:yardley2016_effective_engagement_dbci.

2. **Digitale interventioner har potentiale, men engagement og frafald er centrale problemer.** Brug af apps og trackere kan understøtte aktivitet, men lav vedvarende brug, friktion og appkvalitet begrænser effekten.
   Primære kilder: cite:eysenbach2005_law_of_attrition, cite:laranjo2021_apps_trackers_meta, cite:romeo2019_smartphone_apps_pa_meta, cite:brickwood2019_wearable_trackers_meta.

3. **Træningsapps skal vurderes kritisk som apps, ikke kun som sundhedsinterventioner.** Kvalitet, funktionalitet, engagement, selvmonitorering, feedback og adfærdsændringskomponenter har betydning for, om appen reelt understøtter brugerens adfærd.
   Primære kilder: cite:bondaronek2018_quality_pa_apps, cite:kebede2018_evidence_informed_pa_apps, cite:stoyanov2015_mobile_app_rating_scale, cite:middelweerd2014_apps_physical_activity.

4. **Styrketræning kræver progression og justering.** Et træningsprogram er ikke kun en kalender; det rummer valg om volumen, intensitet, øvelser, progression, deload og regulering efter faktisk performance.
   Primære kilder: cite:acsm2009_progression_models, cite:currier2026_acsm_resistance_training, cite:greig2020_autoregulation_resistance_training, cite:larsen2021_autoregulation_systematic_review.

5. **Den udviklede app er relevant, fordi den samler disse problemer i ét systemdesign.** Træningsmester undersøges som projektets egen app, hvor plan, tracker, completion, feedback, watchOS/Live Activity og datamodel skal understøtte fleksibel progression frem for kun perfekt registrering.
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

Indledningen skal afslutte med, at denne problematik kræver en præcis problemformulering og en klar afgrænsning af den udviklede app. Overgangen bør pege på, at rapporten ikke undersøger "om appen virker" i klinisk eller statistisk forstand, men hvordan et konkret design- og implementeringsarbejde kan understøtte de relevante mekanismer.

### Acceptkriterier for første version

- Læseren forstår problemet uden at kende Træningsmester på forhånd.
- Indledningen bruger mindst tre kildegrupper: motivation/engagement, app-/tracker-evidens og træningsprogression.
- Træningsmester introduceres kort som egenudviklet artefakt, ikke som produktpræsentation.
- Ingen interne arbejdsfiler, mapper eller lokale processer omtales.
- Claims om effekt er forsigtige og koblet til litteratur, ikke til appens egen dokumentation.

## Kapitel 2: Problemformulering og afgrænsning

### Kapitelmål

Kapitlet skal låse rapportens undersøgende ramme. Det skal præsentere hovedspørgsmålet, forklare hvorfor det er afgrænset til design og implementering, og placere Træningsmester som den app, der er udviklet i bachelorprojektet. Kapitlet skal også gøre det tydeligt, hvilke dele af appen der er centrale for problemformuleringen, og hvilke der kun er støttefunktioner.

### Hovedpointe

Rapportens problem er ikke at bygge flest mulige funktioner, men at undersøge hvordan digital programstruktur, progression og feedback kan designes, så brugeren kan håndtere realistiske afvigelser uden datatab, unødig friktion eller demotiverende feedback.

### Delargumenter i anbefalet rækkefølge

1. **Problemformulering.** Indsæt hovedspørgsmålet ordret og kort begrund, at det kombinerer sundhedsadfærd, interaktionsdesign og softwareimplementering.
2. **Underspørgsmål.** Brug fire underspørgsmål:
   - Hvordan modelleres plan, workout, trackerlog, completion-events og cycle runtime, så faktisk træningsadfærd kan afvige fra den lineære plan uden datatab?
   - Hvordan kan UI og interaktionsdesign reducere friktion under træning, herunder tracker-off flow, watchOS og Live Activity?
   - Hvordan kan Supabase, RLS, typed repositories og Edge Functions understøtte fleksible brugerflows uden at eksponere privilegerede credentials?
   - Hvordan kan beta-feedback, screenshots, buildlogs, tests og diagrammer bruges som evidens for designvalg og implementering?
3. **Afgrænsning af appen.** Forklar at Træningsmester er bachelorprojektets egen native SwiftUI-app med Supabase-backend, watchOS, Live Activity og server-side funktioner, men at disse kun behandles i det omfang de belyser hovedspørgsmålet.
4. **Faglig afgrænsning.** Afgræns fra klinisk effektstudie, kommerciel produktlancering, fuld sikkerhedscertificering og national sundhedsdata-/FHIR-integration.
5. **Bidrag.** Formuler bidraget som en dokumenteret design- og implementeringsmodel for fleksibel progression og feedback, understøttet af bilag, kilder og teknisk verifikation.

### Primære citation keys

- Problemets adfærdsmæssige begrundelse: cite:teixeira2012_sdt_exercise, cite:eysenbach2005_law_of_attrition, cite:yardley2016_effective_engagement_dbci.
- App- og trackerbaggrund: cite:laranjo2021_apps_trackers_meta, cite:romeo2019_smartphone_apps_pa_meta, cite:brickwood2019_wearable_trackers_meta.
- Træningsfaglig afgrænsning: cite:acsm2009_progression_models, cite:currier2026_acsm_resistance_training, cite:greig2020_autoregulation_resistance_training.
- Databeskyttelse og sikkerhed som afgrænsning af den udviklede app: cite:europeanparliament2016_gdpr, cite:owasp2024_masvs, cite:supabase_rls_docs.

### Relevante kursusspor

- 88370 Bachelorprojekt: rapporten skal være problemstyret, dokumenteret og kritisk.
- 80540 Software Development for Digital Health: krav, use cases, arkitektur, database, SQL og test som teknisk metode.
- 77437 IT-projektledelse: afgrænsningskontrol, risiko, udgivelsesparathed og undgåelse af ukontrolleret omfangsudvidelse.
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

Kapitlet skal afslutte med, at problemformuleringen kræver en tværfaglig ramme. Den næste del skal derfor etablere begreberne for motivation, digital adfærdsændring, appkvalitet, træningsprogression, interaktionsdesign og datakvalitet.

### Acceptkriterier for første version

- Hovedspørgsmålet står ordret og tydeligt.
- Afgrænsningen gør Træningsmester til undersøgelsesartefakt, ikke produktmål.
- De fire underspørgsmål matcher senere kapitler og bilag.
- Afgrænsningerne er eksplicitte nok til at forhindre overpåstande.
- Kapitlet forbereder teorikapitlet uden at begynde at analysere alle tekniske detaljer.

## Kapitel 3: Teoretisk og faglig ramme

### Kapitelmål

Kapitlet skal give rapporten et samlet begrebsapparat. Det skal ikke være en løs litteraturgennemgang, men en ramme der forklarer, hvilke faglige begreber der senere bruges til at vurdere Træningsmesters design og implementering.

### Hovedpointe

Træningsmester skal forstås i krydsfeltet mellem motivation, adfærdsdesign, appkvalitet, træningsprogression, interaktionsdesign og data-/sikkerhedsarkitektur. Et godt digitalt træningssystem skal både understøtte adfærd, træningsfaglig progression og teknisk pålidelighed.

### Delargumenter i anbefalet rækkefølge

#### 3.1 Motivation, adherence og effektivt engagement

Fokus: autonom motivation, behovsstøtte, frafald, digitalt engagement og forskellen mellem skærmtid og målrettet brug.

Primære kilder: cite:teixeira2012_sdt_exercise, cite:eysenbach2005_law_of_attrition, cite:yardley2016_effective_engagement_dbci.

Brug i senere kapitler: begrunder hvorfor feedback, completion og fleksibel afvigelseshåndtering skal vurderes som motivationsstøtte, ikke kun som datalogik.

#### 3.2 Adfærdsændring, feedback og persuasive systems

Fokus: COM-B, Behaviour Change Wheel, BCT Taxonomy, selvmonitorering, feedback, påmindelser, mål, handleplanlægning, tilpasning og systemtroværdighed.

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

Fokus: datakvalitet, kontekstuel databrug, relationel model, DCR/BPMN, interoperabilitetsniveauer, RLS, service-role-grænse, GDPR og mobilsikkerhed.

Primære kilder: cite:mohammed2025_five_facets_data_quality, cite:vanderalst2009_declarative_workflows, cite:benson2016_principles_health_interoperability, cite:zajac2026_data_quality_interoperability, cite:ku2026_dcr_bpmn_modeling, cite:owasp2024_masvs, cite:europeanparliament2016_gdpr, cite:supabase_rls_docs.

Brug i senere kapitler: gør det muligt at diskutere completion-events, trackerlog, RLS, HealthKit-afgrænsning og Edge Functions som faglige designvalg, ikke kun implementeringsdetaljer.

### Primære citation keys

- Motivation og engagement: cite:teixeira2012_sdt_exercise, cite:eysenbach2005_law_of_attrition, cite:yardley2016_effective_engagement_dbci.
- Adfærdsændring og feedback: cite:michie2011_behaviour_change_wheel, cite:michie2013_bct_taxonomy_v1, cite:oinaskukkonen2009_persuasive_systems_design, cite:nahumshani2018_jitai_mobile_health.
- Appkvalitet, apps og wearables: cite:laranjo2021_apps_trackers_meta, cite:romeo2019_smartphone_apps_pa_meta, cite:brickwood2019_wearable_trackers_meta, cite:bondaronek2018_quality_pa_apps, cite:kebede2018_evidence_informed_pa_apps, cite:stoyanov2015_mobile_app_rating_scale.
- Træningsprogression og autoregulering: cite:acsm2009_progression_models, cite:currier2026_acsm_resistance_training, cite:greig2020_autoregulation_resistance_training, cite:larsen2021_autoregulation_systematic_review.
- Interaktionsdesign, data og sikkerhed: cite:hornbaek2024_brugerundersoegelser, cite:hornbaek2024_prototyper, cite:hornbaek2024_evaluering, cite:mohammed2025_five_facets_data_quality, cite:benson2016_principles_health_interoperability, cite:owasp2024_masvs, cite:supabase_rls_docs.

### Relevante kursusspor

- 72545 Interaktionsdesign: brugerforståelse, prototyper, evaluering og tænkehøjt.
- 79772 Kvantitative og kvalitative undersøgelsesmetoder: metodeposition, interview/spørgeskema, digitale metoder, etik og analyse.
- 89332 Sundhedsdata og interoperabilitet: datakvalitet, DCR/BPMN, interoperabilitet, FHIR/HL7-afgrænsning.
- 80540 Software Development for Digital Health: krav, use cases, systemarkitektur, database og test som softwarefaglig ramme. Må kun bruges direkte, hvis præcise citebare kursuskilder senere verificeres; ellers som intern strukturinspiration.
- 77437 IT-projektledelse: afgrænsning, risici og modenhed. Må kun bruges direkte, hvis præcise citebare kursuskilder senere verificeres; ellers som intern strukturinspiration.

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

Metodekapitlet skal forklare, hvordan rapporten undersøger problemformuleringen. Det skal gøre læseren tryg ved, at projektet ikke foregiver at være et klinisk effektstudie, men er en egenudviklet design- og implementeringscase med flere typer evidens: litteratur, kursusgrundlag, artefakter, bilag, anonymiseret feedback og teknisk verifikation.

### Hovedpointe

Metoden er en problemstyret kombination af scoping-kildesøgning, analyse af den egenudviklede design-/implementeringscase, dokument- og artefaktanalyse, anonymiseret beta-feedback og teknisk verifikation. Metoden er egnet til at vurdere designvalg og implementeringskvalitet, men ikke til at konkludere statistisk effekt på motivation eller adherence.

### Delargumenter i anbefalet rækkefølge

#### 4.1 Design- og implementeringscase

Forklar at Træningsmester undersøges som projektets konkrete artefakt, hvor appens arkitektur, datamodel, UI, feedbackflows og verifikation bruges til at belyse problemformuleringen.

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

### Primære citation keys

- Kildesøgningsmetode: cite:rethlefsen2021_prisma_s, cite:mcgowan2016_press_guideline_statement.
- Kursus- og metodegrundlag: cite:hornbaek2024_brugerundersoegelser, cite:hornbaek2024_prototyper, cite:hornbaek2024_evaluering, cite:gjoedsboel2025_metoder_videnskabsteori, cite:gjoedsboel_grundtvig2025_interview, cite:grundtvig2025_analyse_data, cite:grundtvig2025_digitale_metoder, cite:clotworthy2025_persondata_datasikkerhed, cite:clotworthy2025_etik_kvalitet_forskning.
- Datakvalitet og interoperabilitet: cite:zajac2026_data_quality_interoperability, cite:ku2026_dcr_bpmn_modeling.
- Teknisk verifikation og sikkerhed: cite:owasp2024_masvs, cite:supabase_rls_docs, cite:supabase_securing_api_docs, cite:apple_swiftui_docs, cite:apple_activitykit_live_data_docs, cite:apple_watchconnectivity_docs.

### Relevante kursusspor

- 79772 Metode: videnskabsteori, interview/spørgeskema, digitale metoder, etik, analyse og databehandling.
- 72545 Interaktionsdesign: brugerundersøgelser, prototyper og evaluering.
- 89332 Sundhedsdata og interoperabilitet: datakvalitet, DCR/BPMN og interoperabilitetsafgrænsning.
- 80540 Software Development for Digital Health: intern metodeinspiration for krav, use cases, database, SQL og test. Direkte citation kræver verificeret citation key; ellers bruges de synlige bilag og tekniske kilder.

### Relevante bilag og synlige henvisninger

- Kildesøgning: label:tab:kildesoegning-platforme, label:tab:kildesoegning-appspor, label:tab:kildesoegning-progression-data-metode.
- Kursusmateriale: label:tab:kursusmateriale-gennemgang.
- Materiale- og artefaktgrundlag: label:tab:tm-bilag-materialegennemgang, label:fig:tm-system-context, label:tab:tm-container-architecture.
- App, data og sikkerhed: label:fig:tm-ios-home-ready, label:fig:tm-ios-tracker-active, label:fig:tm-data-model-er, label:fig:tm-tracker-completion-summary, label:tab:tm-use-cases, label:tab:tm-krav-traceability, label:tab:tm-rls-matrix.
- Beta og verifikation: label:tab:tm-testflight-timeline, label:tab:tm-beta-feedback, label:tab:tm-test-traceability.

### Hvad kapitlet ikke må påstå

- At projektet er et randomiseret studie eller et systematisk review.
- At beta-feedback er repræsentativt eller statistisk generaliserbart.
- At alle tests er kørt i clean CI.
- At Supabase/admin/tværbruger-sikkerhed er fuldt integrationstestet.
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

## Kapitel 5: Krav og use cases

### Kapitelmål

Kapitlet skal vise, hvordan problemformuleringen omsættes til konkrete brugerhandlinger, funktionelle krav og ikke-funktionelle krav. Det skal gøre det tydeligt, at kravene ikke er en neutral featureliste, men en sporbar operationalisering af fleksibel progression, motivation, lav friktion, feedback, datakvalitet og sikker adgang.

### Hovedpointe

Træningsmesters centrale krav handler om at understøtte en realistisk træningsrejse: brugeren skal kunne planlægge træning, gennemføre den med eller uden detaljeret logging, få en forståelig næste handling og gøre det inden for en sikker, brugerbundet datamodel.

### Delargumenter i anbefalet rækkefølge

1. **Kravene skal udspringe af problemformuleringen.** Start med at forklare, at kravene udledes af behovet for fleksibel progression, feedback og håndtering af afvigelser. Brug use cases som bindeled mellem teori/metode og systemdesign.
   Primære kilder: cite:michie2011_behaviour_change_wheel, cite:yardley2016_effective_engagement_dbci, cite:acsm2009_progression_models.

2. **Kerneuse cases samler plan, udførelse og feedback.** Fremhæv UC-03, UC-04, UC-06 og UC-08 som hovedspor: programstruktur, træningsdag/øvelser, tracker/completion og træningscyklus.
   Synlige bilag: label:tab:tm-use-cases, label:tab:tm-krav-traceability.

3. **Afvigelser fra planen skal være legitime flows.** Forklar at tracker-off completion og completion-events gør gennemført træning synlig, selv når brugeren ikke logger alle sæt. Dette er vigtigt for motivation og historik, men det reducerer også datadetaljen.
   Synlige bilag: label:fig:tm-tracker-completion-summary, label:tab:tm-tracker-flow-bpmn.

4. **Lav friktion kræver flere interaktionsflader.** WatchOS og Live Activity skal behandles som støtte til træningssituationen, hvor telefoninteraktion kan være upraktisk.
   Primære kilder: cite:apple_activitykit_live_data_docs, cite:apple_watchconnectivity_docs.
   Synlige bilag: label:fig:tm-watch-sync-sequence, label:fig:tm-live-activity-idempotency-sequence.

5. **Sikkerhed er et ikke-funktionelt krav, ikke en eftertanke.** Knyt NF-01, NF-02 og NF-08 til RLS, anon key, Edge Functions og fravær af service-role i klienten.
   Primære kilder: cite:owasp2024_masvs, cite:supabase_rls_docs, cite:supabase_securing_api_docs.
   Synlige bilag: label:fig:tm-security-boundary-summary, label:tab:tm-rls-matrix.

6. **Kravsporbarhed gør senere verifikation mulig.** Slut med at kravtabellen bliver udgangspunkt for arkitektur, implementering, test og diskussion.
   Synlige bilag: label:tab:tm-krav-traceability, label:tab:tm-test-traceability.

### Primære citation keys

- Adfærds- og motivationskrav: cite:michie2011_behaviour_change_wheel, cite:michie2013_bct_taxonomy_v1, cite:yardley2016_effective_engagement_dbci.
- Træningsfaglige krav: cite:acsm2009_progression_models, cite:currier2026_acsm_resistance_training, cite:greig2020_autoregulation_resistance_training.
- Sikkerheds- og platformskrav: cite:owasp2024_masvs, cite:supabase_rls_docs, cite:supabase_securing_api_docs, cite:apple_activitykit_live_data_docs, cite:apple_watchconnectivity_docs.

### Relevante kursusspor

- 80540 Software Development for Digital Health: krav, use cases, database og test som softwarefaglig struktur. Brug kun direkte citation, hvis citation key er verificeret; ellers bruges de synlige tabeller.
- 72545 Interaktionsdesign: use cases og brugerrejser som oversættelse fra brugerbehov til design.
- 77437 IT-projektledelse: afgrænsningskontrol og prioritering af krav.
- 89332 Sundhedsdata og interoperabilitet: krav til datakvalitet, adgang og afgrænsning af dataudveksling.

### Relevante bilag og synlige henvisninger

- Use cases: label:tab:tm-use-cases.
- Kravsporbarhed: label:tab:tm-krav-traceability.
- Tracker- og completionproces: label:tab:tm-tracker-flow-bpmn, label:fig:tm-tracker-completion-summary.
- Sikkerhedskrav: label:fig:tm-security-boundary-summary, label:tab:tm-authorization-dcr, label:tab:tm-rls-matrix.
- Verifikationsspor: label:tab:tm-test-traceability.

### Hvad kapitlet ikke må påstå

- At alle krav er lige vigtige for problemformuleringen.
- At kravlisten i sig selv dokumenterer brugeraccept eller sundhedseffekt.
- At watchOS, Live Activity, import, admin eller trænerfunktioner er hovedformål frem for støttefunktioner.
- At sikkerhed er fuldt bevist, fordi kravene beskriver en sikkerhedsmodel.

### Overgang til næste kapitel

Kapitlet skal afslutte med, at kravene stiller krav til en arkitektur, hvor brugerflade, state, datamodel, backend og platformservices kan arbejde sammen. Det leder til systemarkitekturen.

### Acceptkriterier for første version

- Use cases og krav kobles direkte til problemformuleringen.
- UC-06, UC-08, F-08, F-09, F-13, F-15, NF-01, NF-02 og NF-08 fremstår som særligt rapportcentrale.
- Der henvises til synlige tabeller i bilaget, ikke til interne dokumenter.
- Kapitlet skelner mellem funktionelle krav, ikke-funktionelle krav og evidens for, at de er implementeret.

## Kapitel 6: Systemarkitektur

### Kapitelmål

Kapitlet skal forklare Træningsmesters overordnede arkitektur som svar på kravene: native SwiftUI-klient, global applikationsstate, typed domain/repository-lag, Supabase backend, RLS/RPC, Edge Functions, watchOS companion og Live Activity. Arkitekturen skal præsenteres som et middel til fleksibel progression, lav friktion og sikker databehandling.

### Hovedpointe

Arkitekturen adskiller brugerflade, applikationsstate, domænemodeller, dataadgang og backendautorisation, så appen kan håndtere planlagt træning, faktisk træning, afvigelser og næste handling uden at lade UI'et blive den sikkerhedsmæssige eller datamæssige sandhed.

### Delargumenter i anbefalet rækkefølge

1. **Systemkonteksten placerer appen i et økosystem.** Forklar forholdet mellem iOS, watchOS, Live Activity, Supabase og Apple-services.
   Synlige bilag: label:fig:tm-system-context, label:tab:tm-container-architecture.

2. **Lagdelingen reducerer kobling mellem UI og backend.** Beskriv presentation, AppState, domain models, repositories, integration/platform og database/RLS på konceptuelt niveau.
   Primære kilder: cite:apple_swiftui_docs, cite:supabase_rls_docs.

3. **Repository-laget og AppState giver en samlet bruger- og sessionskontekst.** Forklar hvorfor auth, profiltilstand, aktiv plan, trackerstatus, abonnementsstatus og runtime state skal koordineres.
   Synlige bilag: label:tab:tm-container-architecture, label:tab:tm-sql-fields.

4. **Backend er sikkerhedsgrænse.** Forklar at RLS, helper functions, RPC og Edge Functions er autoritative, mens klienten er et typed og brugerrettet lag.
   Primære kilder: cite:owasp2024_masvs, cite:supabase_rls_docs, cite:supabase_securing_api_docs.
   Synlige bilag: label:fig:tm-security-boundary-summary, label:tab:tm-authorization-dcr, label:tab:tm-rls-matrix.

5. **WatchOS og Live Activity er arkitektoniske friktionsgreb.** Beskriv dem som parallelle træningsflader, der deler session og backendkontrakter med hovedappen.
   Primære kilder: cite:apple_activitykit_live_data_docs, cite:apple_hig_live_activities, cite:apple_watchconnectivity_docs.
   Synlige bilag: label:fig:tm-watch-sync-sequence, label:fig:tm-live-activity-idempotency-sequence.

6. **Arkitekturen forbereder data- og implementeringskapitlerne.** Slut med at arkitekturen kun kan vurderes fuldt, når datamodellen, sikkerheden og implementeringen gennemgås.

### Primære citation keys

- Platform og UI: cite:apple_swiftui_docs, cite:apple_activitykit_live_data_docs, cite:apple_hig_live_activities, cite:apple_watchconnectivity_docs.
- Backend og sikkerhed: cite:supabase_rls_docs, cite:supabase_securing_api_docs, cite:owasp2024_masvs.
- Proces og data: cite:vanderalst2009_declarative_workflows, cite:mohammed2025_five_facets_data_quality.

### Relevante kursusspor

- 80540 Software Development for Digital Health: lagdeling, use cases, databasedesign og test.
- 89332 Sundhedsdata og interoperabilitet: datakvalitet, procesmodellering og systemafgrænsning.
- 77437 IT-projektledelse: afvejninger, afgrænsning, udgivelsesparathed og teknisk risiko.

### Relevante bilag og synlige henvisninger

- Systemkontekst: label:fig:tm-system-context.
- Komponentoverblik: label:tab:tm-container-architecture.
- Datamodel: label:fig:tm-data-model-er, label:fig:tm-data-model-er-left, label:fig:tm-data-model-er-middle, label:fig:tm-data-model-er-right.
- Sikkerhedsgrænse: label:fig:tm-security-boundary-summary, label:tab:tm-authorization-dcr, label:tab:tm-rls-matrix.
- Watch/Live Activity: label:fig:tm-watch-sync-sequence, label:fig:tm-live-activity-idempotency-sequence.
- Import/AI-grænse: label:fig:tm-import-ai-edge-boundary.

### Hvad kapitlet ikke må påstå

- At arkitekturen i sig selv dokumenterer sundhedseffekt.
- At UI'et eller klienten er den endelige sikkerhedsgrænse.
- At watchOS/Live Activity er fuldt runtime-dokumenteret visuelt, hvis bilaget kun dokumenterer arkitektur og build.
- At Edge Functions løser alle sikkerhedsrisici uden integrationstest og deployment-review.

### Overgang til næste kapitel

Arkitekturkapitlet skal afslutte med, at systemets tekniske struktur skal oversættes til konkrete brugerflader. Det leder til interaktionsdesign.

### Acceptkriterier for første version

- Arkitekturen forklares med systemkontekst og komponentoverblik, ikke som en liste over kodefiler.
- AppState, repository-lag, RLS og Edge Functions får hver en tydelig rolle.
- WatchOS og Live Activity bindes til lav friktion under træning.
- Kapitlet forbereder data/sikkerhed og implementering uden at gentage dem fuldt.

## Kapitel 7: Interaktionsdesign

### Kapitelmål

Kapitlet skal analysere appens centrale brugerflader og flows ud fra brugerens træningssituation: start af træning, aktiv tracker, tracker-off completion, næste handling, øvelsessøgning, historik, indstillinger, watchOS og Live Activity. Fokus er, hvordan designet kan reducere friktion og understøtte motivation uden at overtage træningsadfærden.

### Hovedpointe

Træningsmesters interaktionsdesign skal gøre det nemt at komme fra intention til handling, gennemføre træning og forstå næste skridt. Designet skal samtidig rumme ufuldstændig logging og afvigelser fra planen som normale tilstande frem for fejl.

### Delargumenter i anbefalet rækkefølge

1. **Træningssituationen stiller særlige krav til UI.** Brugeren er fysisk aktiv, skifter øvelser, holder pauser og har begrænset opmærksomhed. Derfor er hurtige statussignaler og få nødvendige handlinger centrale.
   Primære kilder: cite:hornbaek2024_brugerundersoegelser, cite:hornbaek2024_prototyper, cite:hornbaek2024_evaluering.

2. **Home-skærmen skal fungere som næste-handling-flade.** Analyser hvordan Home viser aktuel træningshandling, stale session, completion delay og næste træning.
   Synlige bilag: label:fig:tm-ios-home-stale-session, label:fig:tm-ios-home-ready, label:fig:tm-ios-home-completion-delay, label:fig:tm-ios-home-next-training, label:fig:tm-ios-home-current-qa.

3. **Trackerflowet balancerer detaljeret datalogging og lav friktion.** Diskuter aktiv tracker, tracker-off og completion som en designbalance mellem datakvalitet og realistisk brug.
   Primære kilder: cite:stoyanov2015_mobile_app_rating_scale, cite:kebede2018_evidence_informed_pa_apps, cite:michie2013_bct_taxonomy_v1.
   Synlige bilag: label:fig:tm-ios-tracker-active, label:fig:tm-tracker-completion-summary, label:tab:tm-tracker-flow-bpmn.

4. **Øvelseskatalog, match og historik understøtter forståelse og feedback.** Brug skærmene til at forklare inspiration, søgning, overblik og tilbageblik, men undgå at gøre kapitlet til en tour af appen.
   Synlige bilag: label:fig:tm-ios-programmer, label:fig:tm-ios-oevelser, label:fig:tm-ios-match-card, label:fig:tm-ios-historik.

5. **WatchOS og Live Activity reducerer behovet for fuld appåbning.** Knyt dem til lav friktion og status under træning, men beskriv dokumentationen som arkitektur/build, ikke runtime screenshot-evidens.
   Primære kilder: cite:apple_hig_live_activities, cite:apple_activitykit_live_data_docs, cite:apple_watchconnectivity_docs.
   Synlige bilag: label:fig:tm-watch-sync-sequence, label:fig:tm-live-activity-idempotency-sequence.

6. **Beta-feedback bruges som designkorrektion.** Forklar hvordan feedback om søgning, enheder, TestFlight-friktion, katalogkvalitet og watch kan omsættes til designprioriteringer.
   Primære metodekilder: cite:gjoedsboel_grundtvig2025_interview, cite:grundtvig2025_analyse_data.
   Synlige bilag: label:tab:tm-beta-feedback.

### Primære citation keys

- Interaktionsdesign: cite:hornbaek2024_brugerundersoegelser, cite:hornbaek2024_prototyper, cite:hornbaek2024_evaluering, cite:hornbaek2024_taenkehoejt_eksperimenter.
- Appkvalitet og engagement: cite:stoyanov2015_mobile_app_rating_scale, cite:yardley2016_effective_engagement_dbci, cite:kebede2018_evidence_informed_pa_apps.
- Feedback og adfærd: cite:michie2013_bct_taxonomy_v1, cite:oinaskukkonen2009_persuasive_systems_design, cite:nahumshani2018_jitai_mobile_health.
- Platform: cite:apple_hig_live_activities, cite:apple_activitykit_live_data_docs, cite:apple_watchconnectivity_docs.

### Relevante kursusspor

- 72545 Interaktionsdesign: brugerundersøgelser, prototyper, evaluering og tænkehøjt.
- 79772 Metode: kvalitativ analyse af feedback og begrænsninger ved convenience samples.
- 77437 IT-projektledelse: prioritering af feedback og håndtering af releasefriktion.

### Relevante bilag og synlige henvisninger

- App-screenshots: label:fig:tm-ios-home-ready, label:fig:tm-ios-programmer, label:fig:tm-ios-oevelser, label:fig:tm-ios-match-card, label:fig:tm-ios-indstillinger, label:fig:tm-ios-historik, label:fig:tm-ios-tracker-active.
- Completion og næste handling: label:fig:tm-ios-home-completion-delay, label:fig:tm-ios-home-next-training, label:fig:tm-tracker-completion-summary.
- Beta-feedback: label:tab:tm-beta-feedback, label:tab:tm-testflight-timeline.

### Hvad kapitlet ikke må påstå

- At designet dokumenteret øger motivation eller adherence.
- At en positiv betaobservation beviser god usability for alle brugere.
- At flere skærme eller flere platforme automatisk betyder bedre engagement.
- At TestFlight-friktion kan adskilles helt fra appens samlede brugeroplevelse.

### Overgang til næste kapitel

Interaktionsdesignet viser, hvad brugeren møder. Næste kapitel skal vise, hvilke data, sikkerhedsregler og interoperabilitetsafgrænsninger der gør disse flows mulige.

### Acceptkriterier for første version

- Kapitlet analyserer udvalgte flows frem for at beskrive alle skærme.
- Friktion, feedback, completion og næste handling er gennemgående begreber.
- Beta-feedback bruges som anonymiseret designindsigt.
- WatchOS/Live Activity beskrives forsigtigt ud fra den dokumentation, der faktisk findes i bilaget.

## Kapitel 8: Data, sikkerhed og interoperabilitet

### Kapitelmål

Kapitlet skal forklare datamodellen, sikkerhedsmodellen og platformintegrationerne som en del af sundheds- og informatikfagligheden. Det skal vise, hvordan plan, workout, trackerlog, completion-events, settings, cyklusdata, RLS og Edge Functions hænger sammen, og hvor appen afgrænses fra klinisk interoperabilitet.

### Hovedpointe

Træningsmesters dataarkitektur understøtter fleksibel progression ved at adskille planlagt træning, faktisk logging, completion og runtime-progression. Sikkerheden bygger på klientsikre nøgler, bruger-session, RLS og server-side funktioner, mens HealthKit og øvrig interoperabilitet behandles som afgrænsede platformintegrationer.

### Delargumenter i anbefalet rækkefølge

1. **Datamodellen afspejler problemfeltet.** Plan, workout, workout_exercises, trackerlog, completion-events og cycle runtime er separate, fordi planlagt træning og faktisk træning ikke altid er det samme.
   Primære kilder: cite:mohammed2025_five_facets_data_quality, cite:acsm2009_progression_models.
   Synlige bilag: label:fig:tm-data-model-er, label:fig:tm-data-model-er-left, label:fig:tm-data-model-er-middle, label:fig:tm-data-model-er-right.

2. **Completion-events beskytter både motivation og historik.** Afsluttet træning kan registreres uden detaljeret trackerlog, men tradeoffet er mindre granularitet.
   Synlige bilag: label:fig:tm-tracker-completion-summary, label:tab:tm-sql-fields.

3. **RLS er den primære adgangskontrol.** Forklar own-row, relationel adgang, admin/træner/import-flow og hvorfor klientguards ikke er nok alene.
   Primære kilder: cite:supabase_rls_docs, cite:supabase_securing_api_docs, cite:owasp2024_masvs.
   Synlige bilag: label:fig:tm-security-boundary-summary, label:tab:tm-authorization-dcr, label:tab:tm-rls-matrix.

4. **Idempotency og immutable felter reducerer datarisici under træning.** Live Activity, watch og retryede writes kan skabe dobbeltlogging; `client_action_id` og completion-modellen er centrale modtræk.
   Synlige bilag: label:fig:tm-live-activity-idempotency-sequence, label:fig:tm-watch-sync-sequence, label:tab:tm-sql-fields.

5. **Edge Functions flytter privilegerede flows ud af klienten.** Admin, trainer-client, import, AI og billing skal forklares som server-side flows med brugerens bearer token som adgangsforudsætning.
   Primære kilder: cite:owasp2024_masvs, cite:supabase_securing_api_docs.
   Synlige bilag: label:fig:tm-import-ai-edge-boundary.

6. **Interoperabilitet er afgrænset og platformnær.** HealthKit kan beskrives som brugeraktiveret fitnessdata og ikke som klinisk journalintegration. DCR/BPMN og interoperabilitetslitteratur bruges til at placere afgrænsningen.
   Primære kilder: cite:apple_healthkit_docs, cite:benson2016_principles_health_interoperability, cite:zajac2026_data_quality_interoperability, cite:ku2026_dcr_bpmn_modeling, cite:vanderalst2009_declarative_workflows.

### Primære citation keys

- Datakvalitet og interoperabilitet: cite:mohammed2025_five_facets_data_quality, cite:zajac2026_data_quality_interoperability, cite:benson2016_principles_health_interoperability.
- Procesmodellering: cite:vanderalst2009_declarative_workflows, cite:ku2026_dcr_bpmn_modeling.
- Sikkerhed og privacy: cite:europeanparliament2016_gdpr, cite:owasp2024_masvs, cite:supabase_rls_docs, cite:supabase_securing_api_docs.
- Platformintegration: cite:apple_healthkit_docs, cite:apple_watchconnectivity_docs, cite:apple_activitykit_live_data_docs.

### Relevante kursusspor

- 89332 Sundhedsdata og interoperabilitet: datakvalitet, DCR/BPMN, interoperabilitet, FHIR/HL7-afgrænsning.
- 80540 Software Development for Digital Health: SQL, database, RLS og test.
- 79772 Metode: persondata, etik, databehandling og kvalitet.

### Relevante bilag og synlige henvisninger

- ER-diagram og udsnit: label:fig:tm-data-model-er, label:fig:tm-data-model-er-left, label:fig:tm-data-model-er-middle, label:fig:tm-data-model-er-right.
- SQL-domæner og felter: label:tab:tm-sql-domain-overblik, label:tab:tm-sql-fields.
- Sikkerhed og autorisation: label:fig:tm-security-boundary-summary, label:tab:tm-authorization-dcr, label:tab:tm-rls-matrix.
- Watch, Live Activity og import: label:fig:tm-watch-sync-sequence, label:fig:tm-live-activity-idempotency-sequence, label:fig:tm-import-ai-edge-boundary.

### Hvad kapitlet ikke må påstå

- At appen er en klinisk sundhedsplatform eller journalintegration.
- At FHIR/HL7 er implementeret, hvis det kun bruges som afgrænsende teori.
- At HealthKit-data gemmes bredt i Supabase, hvis dokumentationen kun viser begrænset brugeraktiveret brug.
- At RLS-dokumentation er det samme som fuldt penetrationstestet sikkerhed.
- At GDPR-overholdelse er endeligt bevist uden juridisk review.

### Overgang til næste kapitel

Data- og sikkerhedskapitlet skal afslutte med, at modellen nu kan kobles til de konkrete implementeringsvalg, der gør appens flows mulige.

### Acceptkriterier for første version

- Kapitlet forklarer datamodellen problemstyret og med ER-bilag.
- RLS, Edge Functions og klientsikre nøgler er tydeligt adskilt.
- HealthKit og interoperabilitet er præcist afgrænset.
- Rest-risici og begrænsninger omtales åbent.

## Kapitel 9: Implementering

### Kapitelmål

Kapitlet skal beskrive de centrale implementeringsvalg, der realiserer krav, arkitektur, interaktionsdesign og datamodel. Det skal ikke være en kronologisk fil- eller kodegennemgang, men en problemstyret forklaring af hvordan de vigtigste flows er bygget.

### Hovedpointe

Implementeringen realiserer rapportens kerne ved at samle programstruktur, trackerlog, completion-events, cycle runtime, watchOS, Live Activity og server-side funktioner i en model, hvor brugerens næste træningshandling kan beregnes ud fra faktisk adfærd frem for kun en lineær plan.

### Delargumenter i anbefalet rækkefølge

1. **Bootstrap, session og repository setup er fundamentet.** Beskriv hvordan appen først etablerer miljø, auth og repositories, før brugerbundne data hentes.
   Primære kilder: cite:apple_swiftui_docs, cite:supabase_rls_docs.
   Synlige bilag: label:fig:tm-system-context, label:tab:tm-container-architecture.

2. **Program- og workoutstrukturen giver den planlagte ramme.** Forklar hvordan programmer, workouts og øvelser skaber strukturen for træning.
   Synlige bilag: label:fig:tm-data-model-er-left, label:tab:tm-use-cases, label:tab:tm-krav-traceability.

3. **Tracker og completion løser afvigelsesproblemet.** Udfold implementeringsideen: trackerlog er detaljeret udførelse, completion-events er gennemført træning, og begge kan påvirke Home, historik og progression.
   Primære kilder: cite:michie2013_bct_taxonomy_v1, cite:greig2020_autoregulation_resistance_training.
   Synlige bilag: label:fig:tm-ios-tracker-active, label:fig:tm-tracker-completion-summary, label:fig:tm-data-model-er-middle.

4. **Training cycle runtime adskiller avanceret progression fra simpel planindekslogik.** Forklar at en aktiv cyklus kan prioritere næste workout over klassisk lineær planlogik.
   Primære kilder: cite:currier2026_acsm_resistance_training, cite:larsen2021_autoregulation_systematic_review.
   Synlige bilag: label:fig:tm-data-model-er-right, label:tab:tm-sql-domain-overblik.

5. **WatchOS og Live Activity genbruger sikker sessions- og datakontrakt.** Forklar hvordan ekstra flader understøtter hurtig logging/status uden at bryde sikkerhedsmodellen.
   Primære kilder: cite:apple_activitykit_live_data_docs, cite:apple_watchconnectivity_docs.
   Synlige bilag: label:fig:tm-watch-sync-sequence, label:fig:tm-live-activity-idempotency-sequence.

6. **Edge Functions afgrænser privilegerede og eksterne flows.** Admin, træner, import, AI og billing skal kun behandles i det omfang de understøtter appafgrænsning, sikkerhed og datakvalitet.
   Primære kilder: cite:supabase_securing_api_docs, cite:owasp2024_masvs.
   Synlige bilag: label:fig:tm-import-ai-edge-boundary, label:tab:tm-authorization-dcr.

### Primære citation keys

- Platform og backend: cite:apple_swiftui_docs, cite:apple_activitykit_live_data_docs, cite:apple_watchconnectivity_docs, cite:supabase_rls_docs, cite:supabase_securing_api_docs.
- Træningslogik: cite:acsm2009_progression_models, cite:currier2026_acsm_resistance_training, cite:greig2020_autoregulation_resistance_training, cite:larsen2021_autoregulation_systematic_review.
- Feedback og adfærdsændring: cite:michie2013_bct_taxonomy_v1, cite:oinaskukkonen2009_persuasive_systems_design.

### Relevante kursusspor

- 80540 Software Development for Digital Health: implementeringsarkitektur, database, test og traceability.
- 72545 Interaktionsdesign: implementering af flows, der reducerer brugerfriktion.
- 89332 Sundhedsdata og interoperabilitet: datamodel, datakvalitet og systemafgrænsning.

### Relevante bilag og synlige henvisninger

- Arkitektur: label:fig:tm-system-context, label:tab:tm-container-architecture.
- UI og tracker: label:fig:tm-ios-home-ready, label:fig:tm-ios-tracker-active, label:fig:tm-ios-home-completion-delay, label:fig:tm-ios-home-next-training.
- Data og completion: label:fig:tm-data-model-er, label:fig:tm-tracker-completion-summary, label:tab:tm-sql-fields.
- Platform og server-side: label:fig:tm-watch-sync-sequence, label:fig:tm-live-activity-idempotency-sequence, label:fig:tm-import-ai-edge-boundary.

### Hvad kapitlet ikke må påstå

- At kapitlet dokumenterer hele kodebasen.
- At implementeringen er fuldt produktionsmoden uden de kendte verifikationsbegrænsninger.
- At AI/import, admin eller billing er centrale for sundhedsfaglig effekt.
- At alle edge cases er testet på tværs af alle brugerroller.

### Overgang til næste kapitel

Implementeringskapitlet skal afslutte med, at de beskrevne valg skal vurderes gennem test og verifikation. Det leder direkte til verifikationskapitlet.

### Acceptkriterier for første version

- Kapitlet forklarer implementering via 4-6 hovedflows, ikke via filnavne.
- Tracker/completion/cycle runtime står som det centrale implementeringsbidrag.
- WatchOS, Live Activity og Edge Functions er tydeligt afgrænsede støtteelementer.
- Kapitlet peger frem mod test uden at overpåstå modenhed.

## Kapitel 10: Test og verifikation

### Kapitelmål

Kapitlet skal dokumentere, hvad der er verificeret, hvordan resultaterne kan bruges i rapporten, og hvilke begrænsninger der stadig gælder. Det skal være teknisk ærligt og tydeligt adskille build/test-evidens fra bruger- og effekt-evidens.

### Hovedpointe

Verifikationen giver rimelig dokumentation for, at den beskrevne egenudviklede app kan bygges, og at centrale domæne-/payload-/tracker-/cycle-/Live Activity-logikker er testet. Den dokumenterer ikke fuld produktionsklarhed, clean CI, komplet sikkerhedsbevis eller statistisk brugerudbytte.

### Delargumenter i anbefalet rækkefølge

1. **Verifikationens rolle i rapporten skal afgrænses.** Forklar at test bruges til at underbygge implementeringsstatus og traceability, ikke til at bevise motivation eller sundhedseffekt.
   Primære kilder: cite:owasp2024_masvs, cite:yardley2016_effective_engagement_dbci.

2. **Buildstatus dokumenterer target-dækning.** iOS Debug, watchOS og Live Activity build kan bruges som evidens for, at de tekniske spor eksisterer og kan bygges i freeze-state.
   Synlige bilag: label:tab:tm-test-traceability.

3. **Unit tests styrker domæne- og payloadclaims.** Fremhæv unit test-dækning som stærkere evidens for encoding, progress logic, tracker, cycle og Live Activity projection end for fulde brugerflows.

4. **Integrationstests er begrænsede.** Integrationsteststatus skal bruges forsigtigt, fordi nogle admin/ikke-admin- og tværbruger-scenarier kræver dedikerede testlegitimationsoplysninger.
   Synlige bilag: label:tab:tm-test-traceability, label:tab:tm-rls-matrix.

5. **Screenshots og diagrammer verificerer dokumenterede brugerflader og strukturer.** De 13 iOS-screenshots og diagrammer dokumenterer aktuel UI og arkitektur, men ikke watchOS/Live Activity runtime visuelt.
   Synlige bilag: label:tab:tm-bilag-materialegennemgang, label:fig:tm-ios-home-ready, label:fig:tm-ios-tracker-active, label:fig:tm-system-context.

6. **Kendte gaps skal bruges aktivt i diskussionen.** Clean checkout, fuld Supabase/admin-test, Deno/Edge Function tests og runtime screenshots skal fremgå som begrænsninger, ikke skjules.

### Primære citation keys

- Sikkerhed og mobilverifikation: cite:owasp2024_masvs, cite:supabase_rls_docs, cite:supabase_securing_api_docs.
- Metodisk afgrænsning: cite:rethlefsen2021_prisma_s, cite:mcgowan2016_press_guideline_statement, cite:yardley2016_effective_engagement_dbci.

### Relevante kursusspor

- 80540 Software Development for Digital Health: test, build, database og traceability som teknisk dokumentation.
- 79772 Metode: skelnen mellem dokumentation, observation og generaliserbar evidens.
- 77437 IT-projektledelse: udgivelsesparathed, rest-risici og afgrænsning.

### Relevante bilag og synlige henvisninger

- Verifikationsspor: label:tab:tm-test-traceability.
- Kravsporbarhed: label:tab:tm-krav-traceability.
- Materialegennemgang: label:tab:tm-bilag-materialegennemgang.
- Sikkerhed: label:fig:tm-security-boundary-summary, label:tab:tm-rls-matrix.
- UI/diagrammer: label:fig:tm-ios-home-ready, label:fig:tm-ios-tracker-active, label:fig:tm-system-context.

### Hvad kapitlet ikke må påstå

- At appen er testet i clean CI, hvis dokumentationen er fra lokal freeze-state.
- At integrationstestene dækker alle admin-, træner- og tværbruger-scenarier.
- At watchOS og Live Activity er runtime-verificeret visuelt, hvis der ikke findes synlige runtime screenshots.
- At unit tests dokumenterer brugeraccept eller sundhedseffekt.
- At Edge Function helper tests er kørt, hvis de ikke er det.

### Overgang til næste kapitel

Testkapitlet skal afslutte med, at teknisk verifikation ikke siger alt om brugerens oplevelse. Derfor følger en evaluering af anonymiseret beta-feedback og brugerindsigt.

### Acceptkriterier for første version

- Kapitlet skelner klart mellem build, unit tests, integrationstests, screenshots og diagrammer.
- Kendte gaps er eksplicitte.
- Test bruges som støtte for implementeringsclaims, ikke effektclaims.
- Kapitlet forbereder diskussionen med klare begrænsninger.

## Kapitel 11: Evaluering og brugerindsigt

### Kapitelmål

Kapitlet skal analysere anonymiseret beta-feedback, TestFlight-tidslinje og udvalgte brugerindsigter som design- og procesdata. Det skal forklare, hvad materialet kan sige om friktion, forståelighed, platformbias, øvelseskatalog, enheder, watch og onboarding, og hvad det ikke kan sige om effekt.

### Hovedpointe

Beta-feedbacken giver konkrete indikationer på friktion og brugerbehov, som er relevante for design og prioritering. Den kan understøtte refleksion over Træningsmesters løsning, men den er ikke repræsentativ, ikke statistisk og ikke et effektstudie.

### Delargumenter i anbefalet rækkefølge

1. **Evalueringen er kvalitativ og anonymiseret.** Beskriv feedback som convenience sample og tematisk brugerindsigt.
   Primære kilder: cite:gjoedsboel_grundtvig2025_interview, cite:grundtvig2025_digitale_metoder, cite:grundtvig2025_analyse_data, cite:clotworthy2025_etik_kvalitet_forskning.

2. **TestFlight-tidslinjen dokumenterer iteration, ikke effekt.** Brug buildperioden til at vise iterativ udvikling, men undgå at tolke hyppige builds som bedre brugerudbytte.
   Synlige bilag: label:tab:tm-testflight-timeline.

3. **Friktion opstod både i og omkring appen.** TestFlight-link, Apple review, opdateringer, søgning og øvelseskatalog viser, at digital adherence også påvirkes af distributions- og onboardingfriktion.
   Primære kilder: cite:eysenbach2005_law_of_attrition, cite:yardley2016_effective_engagement_dbci.

4. **Søgning, katalogkvalitet og medieindhold er datakvalitetsproblemer.** Feedback om øvelser, dubletter, rigtige videoer, synonymer og kg/lbs skal kobles til datakvalitet, appkvalitet og interaktionsdesign.
   Primære kilder: cite:stoyanov2015_mobile_app_rating_scale, cite:mohammed2025_five_facets_data_quality.
   Synlige bilag: label:tab:tm-beta-feedback, label:fig:tm-ios-oevelser, label:fig:tm-ios-match-card.

5. **Watch og Live Activity fremstår som relevante lav-friktionsspor, men dokumentationen er begrænset.** Brug betaobservationssporet som designindikation, ikke som robust effektbevis.
   Primære kilder: cite:brickwood2019_wearable_trackers_meta, cite:apple_hig_live_activities.
   Synlige bilag: label:tab:tm-beta-feedback, label:fig:tm-watch-sync-sequence, label:fig:tm-live-activity-idempotency-sequence.

6. **Feedbacken skal omsættes til prioriteringer og diskussionspunkter.** Afslut med de vigtigste implikationer: bedre beta-onboarding, søgning/synonymer, kataloggovernance, enhedsunderstøttelse, noter og robust watch/session sync.

### Primære citation keys

- Kvalitativ metode og etik: cite:gjoedsboel_grundtvig2025_interview, cite:grundtvig2025_digitale_metoder, cite:grundtvig2025_analyse_data, cite:clotworthy2025_etik_kvalitet_forskning, cite:clotworthy2025_persondata_datasikkerhed.
- Engagement og appkvalitet: cite:eysenbach2005_law_of_attrition, cite:yardley2016_effective_engagement_dbci, cite:stoyanov2015_mobile_app_rating_scale.
- Wearables og appspor: cite:brickwood2019_wearable_trackers_meta, cite:laranjo2021_apps_trackers_meta.

### Relevante kursusspor

- 79772 Metode: interview, digitale metoder, analyse af data, etik og persondata.
- 72545 Interaktionsdesign: evaluering og prototyper.
- 77437 IT-projektledelse: iteration, udgivelsesfriktion og prioritering.

### Relevante bilag og synlige henvisninger

- Betaobservationer: label:tab:tm-beta-feedback.
- TestFlight-tidslinje: label:tab:tm-testflight-timeline.
- Appskærme knyttet til feedback: label:fig:tm-ios-oevelser, label:fig:tm-ios-match-card, label:fig:tm-ios-tracker-active, label:fig:tm-ios-indstillinger.
- Verifikationsbegrænsninger: label:tab:tm-test-traceability.

### Hvad kapitlet ikke må påstå

- At beta-feedbacken er repræsentativ.
- At brugernes motivation eller adherence er statistisk forbedret.
- At direkte private citater kan anvendes uden eksplicit samtykke.
- At TestFlight-builds er det samme som systematisk evaluering.
- At feedbacken alene beviser, at et designvalg er korrekt.

### Overgang til næste kapitel

Kapitlet skal afslutte med, at brugerindsigt og teknisk verifikation samlet giver grundlag for en kritisk diskussion af styrker, begrænsninger og videre arbejde.

### Acceptkriterier for første version

- Evalueringen er tydeligt kvalitativ og anonymiseret.
- Feedbacktemaer kobles til konkrete design- og datakonsekvenser.
- Platformbias og convenience sample nævnes.
- Kapitlet skelner mellem observation, fortolkning og designimplikation.

## Kapitel 12: Diskussion

### Kapitelmål

Diskussionen skal samle rapportens teori, metode, krav, arkitektur, implementering, verifikation og brugerindsigt i en kritisk vurdering. Den skal ikke genfortælle kapitlerne, men vurdere hvad arbejdet med den udviklede app viser om fleksibel progression, motivation, feedback og afvigelseshåndtering i en digital træningsapp.

### Hovedpointe

Træningsmester viser, at fleksibel progression kan understøttes gennem design- og implementeringsvalg, hvor plan, faktisk udførelse, completion og næste handling adskilles. Den udviklede app dokumenterer en plausibel og teknisk gennemarbejdet løsning, men ikke en empirisk bevist effekt på motivation, adherence eller sundhed.

### Delargumenter i anbefalet rækkefølge

1. **Styrke: afvigelser behandles som systemtilstande.** Diskuter tracker-off completion, completion-events og cycle runtime som svar på realistisk træningsadfærd.
   Primære kilder: cite:teixeira2012_sdt_exercise, cite:yardley2016_effective_engagement_dbci, cite:greig2020_autoregulation_resistance_training.
   Synlige bilag: label:fig:tm-tracker-completion-summary, label:tab:tm-tracker-flow-bpmn.

2. **Tradeoff: lav friktion kan svække datagranularitet.** Når brugeren kan afslutte uden detaljeret logging, fastholdes historik og næste handling, men datakvaliteten bliver mindre detaljeret.
   Primære kilder: cite:mohammed2025_five_facets_data_quality, cite:stoyanov2015_mobile_app_rating_scale.

3. **App- og tracker-evidens støtter relevansen, men ikke den konkrete effekt.** Brug meta-analyser og appkvalitetsstudier som bredt evidensspor; undgå direkte overførsel til Træningsmester.
   Primære kilder: cite:laranjo2021_apps_trackers_meta, cite:romeo2019_smartphone_apps_pa_meta, cite:brickwood2019_wearable_trackers_meta, cite:metzendorf2024_mhealth_obesity_cochrane.

4. **Sikkerhedsarkitekturen er stærk som design, men begrænset som verificeret bevis.** RLS, Edge Functions og klientsikre nøgler er rigtige designgreb, men fuld tværbruger-/admin-verifikation og deployment-gennemgang mangler.
   Primære kilder: cite:owasp2024_masvs, cite:europeanparliament2016_gdpr, cite:supabase_rls_docs.
   Synlige bilag: label:fig:tm-security-boundary-summary, label:tab:tm-rls-matrix, label:tab:tm-test-traceability.

5. **Beta-feedback styrker designforståelsen, men har lav generaliserbarhed.** Diskuter convenience sample, iOS-bias, installationsfriktion, anonymisering og fravær af langtidsmåling.
   Primære kilder: cite:grundtvig2025_analyse_data, cite:clotworthy2025_etik_kvalitet_forskning.
   Synlige bilag: label:tab:tm-beta-feedback, label:tab:tm-testflight-timeline.

6. **Fremtidigt arbejde skal følge evidensniveauet.** Foreslå næste skridt: mere systematisk usabilitytest, længere beta, bedre watch/Live Activity runtime-dokumentation, tværbruger-sikkerhedstest, datakvalitetsmålinger, og eventuelt senere effektstudie.

### Primære citation keys

- Motivation/adherence: cite:teixeira2012_sdt_exercise, cite:eysenbach2005_law_of_attrition, cite:yardley2016_effective_engagement_dbci.
- App-/tracker-evidens: cite:laranjo2021_apps_trackers_meta, cite:romeo2019_smartphone_apps_pa_meta, cite:brickwood2019_wearable_trackers_meta, cite:metzendorf2024_mhealth_obesity_cochrane, cite:thorsen2022_interwalk_app_rct.
- Træningsprogression: cite:acsm2009_progression_models, cite:currier2026_acsm_resistance_training, cite:greig2020_autoregulation_resistance_training, cite:larsen2021_autoregulation_systematic_review.
- Sikkerhed og data: cite:mohammed2025_five_facets_data_quality, cite:owasp2024_masvs, cite:europeanparliament2016_gdpr, cite:supabase_rls_docs.
- Metode og etik: cite:grundtvig2025_analyse_data, cite:clotworthy2025_etik_kvalitet_forskning.

### Relevante kursusspor

- 88370 Bachelorprojekt: kritisk syntese og besvarelse af problemformulering.
- 79772 Metode: metodekritik, generaliserbarhed, etik og datagrundlag.
- 89332 Sundhedsdata og interoperabilitet: datakvalitet, sikkerhed og afgrænsning.
- 77437 IT-projektledelse: rest-risici, udgivelsesparathed og videre arbejde.

### Relevante bilag og synlige henvisninger

- Kerneflow: label:fig:tm-tracker-completion-summary, label:tab:tm-tracker-flow-bpmn.
- Krav og verifikation: label:tab:tm-krav-traceability, label:tab:tm-test-traceability.
- Sikkerhed: label:fig:tm-security-boundary-summary, label:tab:tm-rls-matrix.
- Beta: label:tab:tm-beta-feedback, label:tab:tm-testflight-timeline.
- Kildesøgning: label:tab:kildesoegning-platforme, label:tab:kildesoegning-appspor, label:tab:kildesoegning-progression-data-metode.

### Hvad kapitlet ikke må påstå

- At den udviklede app beviser effekt på motivation, adherence eller fysisk aktivitet.
- At alle brugertyper er repræsenteret i beta-feedbacken.
- At sikkerhedsmodellen er endeligt certificeret eller penetrationstestet.
- At fleksibel completion altid er bedre end detaljeret logging.
- At en teknisk fungerende app automatisk skaber varig adfærdsændring.

### Overgang til næste kapitel

Diskussionen skal munde ud i en konklusion, der svarer præcist på hovedspørgsmålet uden at tilføje nye resultater eller nye kilder.

### Acceptkriterier for første version

- Diskussionen er kritisk og syntetiserende, ikke refererende.
- Styrker og begrænsninger behandles balanceret.
- Evidensniveauet holdes klart hele vejen.
- Fremtidigt arbejde følger direkte af dokumenterede gaps.

## Kapitel 13: Konklusion

### Kapitelmål

Konklusionen skal svare kort og præcist på problemformuleringen. Den skal samle rapportens bidrag, nævne de vigtigste begrænsninger og pege på næste skridt uden at introducere nye analyser.

### Hovedpointe

En digital træningsapp kan designes og implementeres til at understøtte fleksibel progression og motivation ved at adskille plan, faktisk udførelse, completion og næste handling, reducere friktion i træningssituationen og placere sikker dataadgang i backend. Træningsmester dokumenterer dette som bachelorprojektets egenudviklede design- og implementeringscase, men ikke som klinisk eller statistisk effektstudie.

### Delargumenter i anbefalet rækkefølge

1. **Svar direkte på hovedspørgsmålet.** Brug formuleringen "Projektet viser, at..." eller "Arbejdet med Træningsmester peger på, at..." frem for absolutte effektpåstande.
2. **Fremhæv de centrale designgreb.** Programstruktur, tracker-on/off, completion-events, cycle runtime, Home/næste handling, watchOS/Live Activity og RLS/Edge Functions.
3. **Fremhæv det tværfaglige bidrag.** Koblingen mellem træningsfaglig progression, motivation/adherence, interaktionsdesign, datakvalitet og softwarearkitektur.
4. **Afgræns evidensen.** Ingen dokumenteret langtidsadherence, ingen klinisk effektmåling, begrænset beta, delvis teknisk verifikation.
5. **Peg på næste skridt.** Systematisk usabilitytest, længere beta, flere platforme, runtime-dokumentation, sikkerhedstest og senere effektstudie.

### Primære citation keys

Konklusionen bør normalt ikke introducere nye kilder. Hvis der bruges citations, skal de være få og opsamlende:

- cite:teixeira2012_sdt_exercise
- cite:yardley2016_effective_engagement_dbci
- cite:laranjo2021_apps_trackers_meta
- cite:acsm2009_progression_models
- cite:owasp2024_masvs

### Relevante kursusspor

- 88370 Bachelorprojekt: præcis besvarelse, kritisk afgrænsning og ingen nye resultater i konklusionen.

### Relevante bilag og synlige henvisninger

Konklusionen bør som udgangspunkt ikke have mange bilagshenvisninger. Hvis den henviser, bør det kun være til helt centrale opsamlende bilag:

- Kerneflow: label:fig:tm-tracker-completion-summary.
- Krav/verifikation: label:tab:tm-krav-traceability, label:tab:tm-test-traceability.
- Beta: label:tab:tm-beta-feedback.

### Hvad kapitlet ikke må påstå

- At Træningsmester beviser forbedret motivation, adherence eller sundhed.
- At appen er færdigvalideret, certificeret eller produktionsmoden i alle henseender.
- At beta-feedbacken er repræsentativ.
- At nye argumenter eller kilder introduceres først i konklusionen.

### Overgang til næste kapitel

Ingen egentlig overgang. Konklusionen skal afslutte rapporten og efterfølges kun af referencer og bilag.

### Acceptkriterier for første version

- Konklusionen svarer direkte på hovedspørgsmålet.
- Den skelner klart mellem design-/implementeringsbidrag og effektbevis.
- Den er kortere og skarpere end diskussionen.
- Den introducerer ingen nye påstande, figurer eller kilder.

## Kildepakker til skrivearbejdet

| Påstandstype | Førstevalg af citation keys |
| --- | --- |
| Autonom motivation og fysisk aktivitet | cite:teixeira2012_sdt_exercise |
| Digital frafaldsproblematik | cite:eysenbach2005_law_of_attrition |
| Effektivt engagement | cite:yardley2016_effective_engagement_dbci |
| Adfærdsændringsframework | cite:michie2011_behaviour_change_wheel, cite:michie2013_bct_taxonomy_v1 |
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
| Krav og use cases | cite:michie2011_behaviour_change_wheel, cite:yardley2016_effective_engagement_dbci, cite:acsm2009_progression_models, cite:owasp2024_masvs |
| Systemarkitektur og implementering | cite:apple_swiftui_docs, cite:supabase_rls_docs, cite:supabase_securing_api_docs, cite:apple_activitykit_live_data_docs, cite:apple_watchconnectivity_docs |
| Evaluering og brugerindsigt | cite:gjoedsboel_grundtvig2025_interview, cite:grundtvig2025_digitale_metoder, cite:grundtvig2025_analyse_data, cite:clotworthy2025_etik_kvalitet_forskning |
| Diskussion og evidensafgrænsning | cite:laranjo2021_apps_trackers_meta, cite:romeo2019_smartphone_apps_pa_meta, cite:brickwood2019_wearable_trackers_meta, cite:teixeira2012_sdt_exercise, cite:yardley2016_effective_engagement_dbci |

## Bilagspakker til skrivearbejdet

| Rapportbrug | Synlige labels |
| --- | --- |
| Appens hovedflows | label:fig:tm-ios-home-ready, label:fig:tm-ios-programmer, label:fig:tm-ios-tracker-active, label:fig:tm-ios-home-current-qa |
| Completion og næste handling | label:fig:tm-ios-home-completion-delay, label:fig:tm-ios-home-next-training, label:fig:tm-tracker-completion-summary |
| System og arkitektur | label:fig:tm-system-context, label:tab:tm-container-architecture |
| Datamodel | label:fig:tm-data-model-er, label:fig:tm-data-model-er-left, label:fig:tm-data-model-er-middle, label:fig:tm-data-model-er-right, label:tab:tm-sql-domain-overblik, label:tab:tm-sql-fields |
| Krav og use cases | label:tab:tm-use-cases, label:tab:tm-krav-traceability |
| Proces og progression | label:tab:tm-tracker-flow-bpmn, label:fig:tm-tracker-completion-summary |
| Sikkerhed og RLS | label:fig:tm-security-boundary-summary, label:tab:tm-authorization-dcr, label:tab:tm-rls-matrix |
| Watch og Live Activity | label:fig:tm-watch-sync-sequence, label:fig:tm-live-activity-idempotency-sequence |
| Import/AI-afgrænsning | label:fig:tm-import-ai-edge-boundary |
| Beta og verifikation | label:tab:tm-testflight-timeline, label:tab:tm-beta-feedback, label:tab:tm-test-traceability |
| Kildesøgning og kursusgrundlag | label:tab:kildesoegning-platforme, label:tab:kildesoegning-appspor, label:tab:kildesoegning-progression-data-metode, label:tab:kursusmateriale-gennemgang |

## Før næste skriveiteration

1. Læs denne fil sammen med `referencer.md`, `kildesoegning.tex` og `billedbilag.tex`.
2. Skriv rapporten i den rækkefølge, matrixen angiver: fra Indledning til Konklusion.
3. Brug citation keys direkte i LaTeX som `\cite{...}`.
4. Brug bilagshenvisninger med `\ref{...}` eller `Figur~\ref{...}`/`Tabel~\ref{...}` i rapporten.
5. Kontrollér efter skrivning, at rapportens synlige tekst ikke omtaler interne filer, mapper, lokale referencebiblioteker eller arbejdsgange.
6. Kør XeLaTeX/LuaLaTeX-kompilering, tjek citationer, tjek figur-/tabelhenvisninger og scan PDF-tekst for interne arbejdsreferencer.
