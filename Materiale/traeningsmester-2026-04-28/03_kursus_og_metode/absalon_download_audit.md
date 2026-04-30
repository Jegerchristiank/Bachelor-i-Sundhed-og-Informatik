# Kursusmateriale Download-Audit

Dato: 2026-04-28  
Formål: dokumentere hvad der faktisk blev åbnet, hentet, tekstudtrukket og kvalitetstjekket fra Absalon-kurserne efter den udvidede research-run.

Rå kursusfiler ligger kun i privat råmappe under `[private-raw]/absalon/downloaded-files/`. Denne public fil gengiver kun metadata, korte parafraser og rapportrelevante koblinger.

## Status På Faktiske Downloads

| Kursus | Absalon-kilde | Faktisk downloadet | Verifikation | Rapportværdi |
| --- | --- | ---: | --- | --- |
| 72545 Interaktionsdesign | Canvas Files, 8 mapper besøgt | 50 filer / ca. 3,9 GB | `file` bekræfter PDF og MP4, tekst/metadata udtrukket | Meget høj til UX, brugerforståelse, prototyping, evaluering og UI-kontekster |
| 79772 Kvantitative og kvalitative undersøgelsesmetoder | Canvas Files | 24 filer / ca. 188 MB | PDF/DOCX/PPT/PPTX/PPT verificeret; 2 Canvas-rækker var 0-byte og må kun markeres som gap | Meget høj til metode, etik, samtykke, interview, spørgeskema og analyse |
| 88370 Kursus i Bachelorprojekt | Canvas Files + `unfiled` | 6 filer / ca. 1 MB | PDF/DOCX/RTF/HTML verificeret, tekst udtrukket | Høj til formelle krav, opgaveafgrænsning og rapportstruktur |
| 89332 Sundhedsdata og interoperabilitet | Canvas Files + `unfiled` | 23 filer / ca. 281 MB | PDF/DOCX/MP4/MOV verificeret, tekst/metadata udtrukket | Høj til DCR/BPMN, data quality, interoperabilitet, HL7/FHIR/SNOMED og CDS/AI |
| 80540 Software Development for Digital Health | Module-items, ikke Canvas Files | 28 module-items åbnet og metadata gemt; ikke rådownloadet | Downloadlinks findes kun uden `verifier`; shell-download returnerer login-HTML | Meget høj til krav, UML, arkitektur, SQL og test, men brug som metadata/lektionsaudit |
| 77437 IT-projektledelse | Module-items, ikke Canvas Files | 44 module-items åbnet og metadata gemt; ikke rådownloadet | Downloadlinks findes kun uden `verifier`; shell-download returnerer login-HTML | Høj til risiko, benefits, krav, WBS, governance og modenhed |

## Kvalitetstjek

- Verificerede Canvas Files blev hentet via klik i Absalon, så Canvas udstedte signed `verifier`-downloadlinks.
- Tidligere forsøg uden `verifier` gav login-HTML og er ikke brugt som evidens.
- `file` er kørt på downloadmapperne for at kontrollere, at materialet ikke er HTML-loginfejl.
- `pdftotext`, DOCX/PPTX XML-udtræk, `textutil` og `ffprobe` er brugt til privat tekst-/metadataudtræk.
- Kursusmaterialet er ikke kopieret ind i repoet, og lange citater fra slides, lærebogskapitler eller artikler må ikke bruges i public bilag.

## Faglige Fund Til Bacheloren

### Interaktionsdesign

Downloadet materiale dækker forelæsningsslides, eksemplariske opgaver, værktøjskasse, ældre eksamensopgaver, lærebogskapitler og streamede forelæsninger. De mest bachelorrelevante spor er:

- brugerforståelse og menneske-interaktion som ramme for træning i en fysisk, lav-opmærksomhedskontekst,
- brugerundersøgelser, observation og spørgeskema som metodisk bro til beta-feedback,
- design/prototyping som forklaring på migrationen fra FlutterFlow-parity til native SwiftUI,
- evaluation, tænke-højt og brugbarhedsproblemer som grundlag for kritisk, ikke-overpåstået evaluering,
- brugergrænsefladetyper som argument for app, watchOS og Live Activity som forskellige interaktionsflader.

### Undersøgelsesmetoder

Downloadet materiale dækker introduktion/metode, spørgeskema, deltagerobservation, etnografi, digitale metoder, interview/fænomenologi, databehandling, kvalitet, etik og analyse. Det bør bruges til at formulere:

- metodeafgrænsning: bacheloren er et design-/implementeringsprojekt med kvalitativ brugerindsigt,
- etikafsnit: anonymisering, samtykke, oplysningspligt og begrænsning af private Messenger/Facebook/mail-data,
- feedbackanalyse: temaer, ikke statistiske konklusioner, når datagrundlaget er lille,
- digitale metoder: TestFlight, screenshots, app-logs, repoartefakter og digitale beskeder som kilder.

### Bachelorprojektkurset

Downloadet materiale indeholder arbejdsbeskrivelse, FAQ og projektforslagsskabelon. Det kan bruges som intern checkliste for:

- problemstyret rapportstruktur,
- tydelig metode- og afgrænsningsbeskrivelse,
- bilagshygiejne og forskel på hovedtekst, dokumentation og rådata,
- eksplicit formulering af hvad bacheloren kan og ikke kan konkludere.

### Sundhedsdata Og Interoperabilitet

Downloadet materiale dækker methods of knowing/healthcare data, process management, guidelines/protocols, DCR/BPMN, data quality, EHR, coding data, HL7/FHIR/SNOMED, clinical decision support og AI. Det bør kobles til TræningsMester sådan:

- DCR/BPMN: modeller fleksibel træningsadherence, deload, afvigelser og completion-events,
- data quality: forklar hvorfor trackerlog, completion-events, cycle runtime og importdata skal holdes adskilt,
- interoperabilitet: afgræns appen fra klinisk EHR, men brug HL7/FHIR/SNOMED som perspektiv på standardiserede sundhedsdata,
- CDS/AI: forklar at AI-import og programanalyse går via Edge Functions, ikke direkte fra klienten.

### Software Development For Digital Health

Materialet er observeret som 28 module-items, herunder weekly PDFs og TA-materiale om OOP, SQL og database-application interaction. Fordi kurset ikke eksponerer almindelige Canvas Files-downloads med `verifier`, er råfilerne ikke hentet i denne run. Metadata er stadig rapportrelevant til:

- requirements engineering og traceability,
- UML use case-, klasse- og sekvensdiagrammer,
- systemarkitektur og lagdeling,
- database/SQL/relationsmodel,
- teststrategi og systems engineering.

### IT-Projektledelse

Materialet er observeret som 44 module-items, herunder seminarer om offentlige IT-projekter, risiko, benefits, krav, WBS, modenhed og Tinglysning-case. Download blev begrænset af samme module-item/no-verifier-problem som 80540. Brug det som metodekontekst til:

- projektdefinition og benefits,
- risikolog og release-gates,
- kravstyring og leveranceplan,
- modenhedsvurdering af appen som beta/releasekandidat,
- kritisk refleksion over scope og governance i et soloprojekt.

## Konkrete Rapportafsnit Dette Understøtter

| Rapportafsnit | Kursuskilder | TræningsMester-kobling |
| --- | --- | --- |
| Problem og metode | 79772, 88370 | Problemformulering, kvalitativ brugerindsigt, etisk databehandling |
| UX/design | 72545 | Tracker-off flow, lav friktion, watch, Live Activity, feedbacktemaer |
| Arkitektur og krav | 80540, 89332 | AppState, repositories, Supabase, Edge Functions, UML og dataflow |
| Data/sikkerhed | 80540, 89332 | ERD, SQL, RLS, profile_mode, admin guard, App Group/Live Activity |
| Projektledelse | 77437, 88370 | Scope, risiko, WBS, beta-distribution, releasegates |
| Evaluering | 72545, 79772 | TestFlight, Messenger/Facebook-feedback, screenshot-QA, testlogs |

## Åbne Gaps

- 80540 og 77437 bør stadig hentes manuelt fra Absalon, hvis rapporten skal bruge direkte slideindhold eller citérbare formuleringer. I denne run blev module-items åbnet og downloadlinks observeret, men programmatisk download uden browsercookies gav kun login-HTML.
- De to 0-byte filer i 79772 må ikke bruges som datakilde.
- Tekstudtræk fra gamle `.ppt`-filer er lavere kvalitet end PDF/PPTX/DOCX-udtræk og bør kun bruges vejledende.
- Videooptagelser er downloadet privat, men ikke transskriberet fuldt; brug primært slides/tekstfiler til rapportargumenter.
