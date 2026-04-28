# Anonymiseret Beta-Testrapport

Dato: 2026-04-28  
Kilder: TestFlight metadata, Messenger access/captures i privat råmappe, Facebook search/access-check og scoped Gmail/KU webmail-søgninger. Rå navne, profilbilleder, chat-ID'er og mailadresser er ikke kopieret til repoet. Personer omtales som `P01`, `P02` osv.; der findes ingen public navnenøgle.

## Datagrundlag

| Kilde | Status | Public brug |
| --- | --- | --- |
| TestFlight | Build 4-12 observeret mellem 2026-03-31 og 2026-04-25 | Dokumenterer iterativ beta-distribution |
| Messenger beta-gruppe | Tilgængelig; rå screenshots/snapshots gemt privat | Bruges kun som anonymiserede temaer |
| Facebook rekruttering | Search/access-check gemt privat | Dokumenterer kanal til rekruttering efter redaktion |
| KU webmail | Scoped vejleder-/bachelorsøgning udført | Dokumenterer bacheloraccept/registrering i februar 2026 |
| Gmail | Scoped TestFlight-/vejledersøgninger | TestFlight-tidslinje og fravær af bachelortråde i Gmail |

## Beta-Tester Oversigt

De offentlige artefakter bruger ikke personnavne. Testere omtales som `P01`, `P02` osv. En fuld navneoversigt bør kun opbevares i privat råmateriale eller i en særskilt samtykkeoversigt.

| Pseudonym | Observeret rolle | Evidens | Rapportrelevant indsigt |
| --- | --- | --- | --- |
| P01 | Tidlig kritisk tester af prototype og øvelseskatalog | Messenger privat capture | Pegede på søgning, visuelle holdepunkter, dubletter og behov for admin-godkendelse af offentlige brugerøvelser |
| P02 | iOS-betatester med konkrete øvelses- og enhedsbehov | Messenger privat capture | Kunne ikke finde almindelige øvelser/varianter og foreslog kg/lbs-understøttelse |
| P03 | iOS-betatester med installations-/linkfriktion | Messenger privat capture | Viste at TestFlight-link, buildstatus og manuel opdatering kan skabe onboarding-friktion |
| P04 | Positiv betarespondent | Messenger privat capture | Giver lav-styrke signal om villighed til at teste efter TestFlight-godkendelse |
| P05 | Interesseret deltager uden iOS-enhed | Messenger privat capture | Dokumenterer platform-bias i iOS-betaen |
| Rekrutterede Facebook-brugere | Potentielle beta-testere | Facebook privat capture | Kanal til bredere fitnessmålgruppe, men kræver redigeret screenshot før public bilag |

## Temaer Fra Feedback Og Dialog

| Tema | Anonymiseret observation | Relevans for bachelor |
| --- | --- | --- |
| Motivation i selve træningssituationen | Lock screen/Live Activity blev testet og bekræftet som fungerende i praksis | Understøtter argumentet om lav friktion under workout og mindre behov for at åbne appen |
| Øvelsesforståelse | Dialogen viste tydeligt behov for rigtige øvelsesvideoer frem for generiske eller AI-genererede klip | Kobler appens designintention til interaktionsdesign og sundheds-/træningsdataformidling |
| Dækning af øvelseskatalog | Testerdialogen peger på udfordringen ved at filme mange øvelser og have adgang til korrekt udstyr | Understøtter prioritering af katalogkvalitet, søgning og media-pipeline |
| Træningscenter-samarbejde | Mail-/Messenger-sporet viser outreach og korrespondance om at kunne filme øvelsesvideoer i lokale centre | Bruges som projektledelses- og designrationale, men ikke som dokumentation for en færdig aftale |
| TestFlight onboarding | Testere skulle forstå TestFlight-app, beta-link, Apple review-status og manuel opdatering | Viser at beta-friktion også ligger uden for selve app-UI |
| Søgning på tværs af flows | En tester fandt forskel på øvelsessøgning i øvelsesmenu og programdag | Understøtter fælles søgelogik og regressionstest på tværs af features |
| Admin-governance | Tidlig feedback foreslog private øvelser adskilt fra offentligt katalog via godkendelse | Kobler brugerfeedback til datakvalitet, moderation og RLS/admin-flow |
| Kg/lbs | Et konkret centerproblem med maskiner i lbs blev omsat til enhedsunderstøttelse | Viser hurtig omsætning af situated feedback til implementeringsvalg |
| Apple Watch | Watch blev introduceret som telefonfri træningsflade, men med tidlig stabilitetsforbehold | Understøtter watch som lav-friktionsspor med krav om robust session-sync |
| Release-prioritering | Spørgerammen til testere spørger til savnet værdi, irritation, anbefalingskrav, betalingsvillighed og tre vigtigste forbedringer | Kan bruges som kvalitativ evaluering og prioriteringsgrundlag |
| Adherence og afvigelser | Appens tracker-off completion, cyklusprogression og historik skal læses sammen med feedback om faktisk brug og manglende brug | Giver en måde at analysere både aktiv brug og ikke-brug uden at tolke frafald som simpel fejl |

## Dybdeanalyse

Se `messenger_dybdeanalyse.md` for en mere detaljeret, anonymiseret analyse af Messenger-forløbet fra oktober 2025 til marts 2026. Den udvider denne rapport med kronologi, kodning og designimplikationer uden at gengive råbeskeder.

Supplerende traeningscenter- og videooptagelsesspor ligger i `traeningscenter_korrespondance.md`. Kodede observationer ligger i `feedbackkatalog.md` og `beta_observationsmatrix.csv`.

## Spørgeramme Til Rapportmetode

Den observerede spørgeramme er egnet som semistruktureret kvalitativ evaluering:

| Analysefelt | Spørgsmålstype | Kobling til rapport |
| --- | --- | --- |
| Faktisk brug | Om appen blev brugt til træning, browsing eller slet ikke | Adoption og barrierer |
| Værdi | Hvad brugeren brugte mest, og hvornår appen gav mest værdi | Use case-validitet |
| Friktion | Hvad irriterede eller gjorde appen langsommere | UI/UX og flowforbedringer |
| Betalingsvillighed | Om brugeren realistisk ville betale efter beta | Produkt-/premium-rationale |
| Prioritering | De tre vigtigste forbedringer før release | Roadmap og projektledelse |
| Samtykke | Om svar må bruges anonymiseret | Etisk og juridisk redaktionsspor |

## Begrænsninger

- Messenger/Facebook-materialet er kun delvist redaktionelt gennemgået i denne run. Rå screenshots ligger udenfor repoet.
- Antallet af faktiske beta-testere kan ikke fastslås endeligt ud fra de public artefakter alene; brug privat råmappe og samtykkeliste til en endelig optælling.
- Direkte citater bør kun bruges efter samtykke. Public bachelortekst bør som udgangspunkt parafrasere.
- Public materialet kan bruges til tema- og designanalyse, men ikke til en endelig navne-/samtykkeoversigt. Den bør forblive privat.
