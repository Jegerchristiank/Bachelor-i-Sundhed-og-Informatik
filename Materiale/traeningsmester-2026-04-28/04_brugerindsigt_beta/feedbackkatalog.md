# Feedbackkatalog

Dato: 2026-04-28  
Kildegrundlag: anonymiserede temaer fra Messenger, TestFlight-tidslinje, Facebook-rekrutteringssignal og public beta-rapport. Rådata ligger privat. Personer omtales som `P01`, `P02` osv. uden navnenøgle i public repo.

## Kodet Observationsmatrix

| ID | Kilde | Tema | Anonymiseret observation | Evidensstyrke | Designimplikation | Rapportbrug |
| --- | --- | --- | --- | --- | --- | --- |
| B01 | Messenger | `FRIKTION` | Lock screen/Live Activity blev bekræftet som fungerende i praktisk brug. | Middel | Prioritér pausetimer, næste sæt og hurtig status uden fuld appåbning. | Interaktionsdesign og evaluering. |
| B02 | Messenger | `MEDIEKVALITET` | Dialogen pegede på ønske om rigtige øvelsesvideoer frem for generiske/AI-klip. | Middel | Øvelsesmedier skal være troværdige og kropsligt genkendelige. | Designrationale for medie-pipeline. |
| B03 | Messenger | `KATALOG` | Et stærkt katalog kræver adgang til udstyr og personer, der kan udføre svære øvelser korrekt. | Middel | Kataloget er både data-, indholds- og governanceproblem, ikke kun UI. | Diskussion af scope og videre arbejde. |
| B04 | Messenger | `BETA_PROCESS` | Tester tilbød praktisk hjælp til øvelsesvideoer og udstyr. | Lav-middel | Beta-test kan fungere som co-design og indholdsvalidering. | Metodeafsnit om brugerinddragelse. |
| B05 | TestFlight | `BETA_PROCESS` | Build 4-12 blev distribueret i perioden 2026-03-31 til 2026-04-25. | Høj for distribution, lav for effekt | Dokumenterer iterationstempo, men ikke brugerudbytte alene. | Projektledelse og verifikation. |
| B06 | Facebook | `REKRUTTERING` | Facebook fitnessgrupper blev brugt/undersøgt som kanal til bredere beta-rekruttering. | Lav i public materiale | Skal redigeres manuelt, hvis opslag skal bruges som bilag. | Rekrutteringsmetode og bias. |
| B07 | Spørgeramme | `SAMTYKKE` | Spørgerammen dækkede brug, værdi, friktion, betalingsvillighed, prioriteringer og anonymiseret brug af svar. | Middel | Giver struktur til semistruktureret evaluering. | Metode og etik. |
| B08 | Apparkitektur + feedback | `ADHERENCE` | Feedback om lav friktion bør sammenholdes med tracker-off completion, watch og Live Activity. | Indirekte, trianguleret | Systemet bør acceptere ufuldstændig logging som gyldig træning. | Diskussion af hovedproblem. |
| B09 | Messenger | `ONBOARDING` | Oktober 2025-prototypen krævede manuelle hjemmeskærm-/browsertrin, før brugeren fik en app-lignende oplevelse. | Middel | TestFlight og native distribution reducerer noget friktion, men onboarding skal stadig forklare installation og første load. | Metode, betaudvikling og brugerbarrierer. |
| B10 | Messenger | `REKRUTTERING` | Marts 2026-genaktivering krævede iPhone, hvilket udelukkede mindst én interesseret deltager. | Middel | Betaresultater skal beskrives som iOS-biased convenience sample. | Metodekritik. |
| B11 | Messenger | `INSTALL_FRIKTION` | 2026-03-30 opstod forvirring om TestFlight-link, build-status og manuel opdatering. | Middel-høj | Beta-onboarding skal vise build/version og give klare fallback-instruktioner. | TestFlight-onboarding og proces. |
| B12 | Messenger | `KATALOG` | P01 pegede tidligt på, at fritekstoprettelse uden katalogstyring kan skabe dubletter og lav datakvalitet. | Høj kvalitativ | Personlige øvelser og offentligt katalog bør adskilles med review-flow. | Designrationale for admin-governance. |
| B13 | Messenger | `SØGNING` | P02 kunne ikke finde almindelige øvelser/varianter, selv om de enten fandtes under andet navn eller manglede i kataloget. | Høj kvalitativ | Søgning skal understøtte synonymer, varianter og øvelsesfamilier. | UX-evaluering og katalogkrav. |
| B14 | Messenger | `FEJL` | Søgning virkede forskelligt i øvelsesmenu og programdag-flow. | Høj kvalitativ | Samme søgelogik bør genbruges på tværs af flows. | Implementeringsvalg og regressionstest. |
| B15 | Messenger | `ENHEDER` | P02 ønskede kg/lbs, fordi visse træningsmaskiner bruger lbs. | Høj kvalitativ | Vægtenhed bør kunne sættes globalt og pr. øvelse med konvertering i logs/historik. | Situated feedback og designrespons. |
| B16 | Messenger | `WATCH` | Apple Watch blev præsenteret som lav-friktionsflade til træning uden telefon, men med tidlig stabilitetsforbehold. | Middel | Watch skal prioriteres til oversigt, hurtig logging og robust session-sync. | Multiplatform design og evaluering. |
| B17 | Messenger | `ITERATION` | Releasebeskeder koblede feedback til nye funktioner som supersæt, flere øvelser, drag-and-drop, social login og reduceret visuel støj. | Middel-høj | Messenger og TestFlight dokumenterer korte feedback-/release-cyklusser. | Projektledelse og designproces. |
| B18 | Messenger | `NOTER` | Råudtrækket viste et selvstændigt ønske om noter til teknik, udstyr eller sædeindstilling på den enkelte øvelse, så konteksten kan genbruges næste gang. | Middel | Øvelsesnoter bør behandles som træningskontekst, ikke kun fritekst; de kan reducere gentagen hukommelsesfriktion i tracker og programdag. | UX-evaluering og roadmap. |

## Prioriteret Backlog Fra Feedback

| Prioritet | Forbedring | Begrundelse | Koblet appområde |
| --- | --- | --- | --- |
| P1 | Flere rigtige øvelsesvideoer | Øger tillid og forståelse i øvelseskataloget. | Øvelser, media upload, kataloggovernance |
| P1 | Styrk lock screen/Live Activity-stabilitet | Reducerer friktion under træning. | Tracker, Live Activity, timers |
| P1 | Gør tracker-off completion tydelig i UI/rapport | Understøtter adherence uden tvungen logging. | Home, Tracker, Historik |
| P1 | Ensret øvelsessøgning på tværs af flows | Beta viste forskel på søgning i øvelsesmenu og programdag. | Øvelser, Plans, `ExerciseSearchCatalog` |
| P1 | Admin-review for brugeroprettede offentlige øvelser | Reducerer dubletter og beskytter katalogkvalitet. | Øvelser, Admin, Supabase/RLS |
| P1 | Kg/lbs globalt og pr. øvelse | Matcher konkret centerudstyr og reducerer mental omregning. | Tracker, Historik, Settings |
| P2 | Dokumentér katalogdækning og mangler | Gør scope ærligt og prioriterbart. | Øvelser, Match, Admin review |
| P2 | Gør TestFlight-buildstatus tydelig i beta-kommunikation | Mindsker supportfriktion ved Apple review og manuelle opdateringer. | Beta-proces, release notes |
| P2 | Stabiliser watch-session og logging | Watch giver lav telefonfriktion, men må ikke skabe ny sync-friktion. | Watch, App Group/session sync |
| P2 | Tilføj/afklar øvelsesspecifikke noter | Beta-dialogen pegede på behov for at gemme teknik-, udstyrs- og indstillingskontekst pr. øvelse. | Tracker, Programdag, Historik |
| P2 | Udbyg samtykke-/testeroversigt privat | Styrker metode og etik uden at publicere persondata. | Beta-protokol |

## Metodisk Vurdering

Feedbacken er bedst egnet til kvalitativ triangulering: den kan forklare, hvorfor bestemte designvalg er relevante, men den kan ikke alene dokumentere effekt på motivation eller fastholdelse. I rapporten bør den derfor kobles med appens implementering, screenshots, testlogs og kravtraceability.
