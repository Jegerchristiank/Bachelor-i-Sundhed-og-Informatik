# Referencer

Dato: 2026-04-29
Formaal: samlet referencebibliotek til bachelorrapporten om Traeningsmester.

Denne fil binder `referencer.bib`, lokale PDF'er i `referencer/` og de autoritative web-/DOI-links sammen. Laes den inden nye skrive- eller redigeringsiterationer, saa rapportens argumenter forbliver koblet til de rigtige BibTeX-noegler.

## Brug

- Brug `referencer.bib` som LaTeX/BibTeX-kildebibliotek.
- Brug BibTeX-noeglerne i tabellen, naar kilder citeres i `main.tex`.
- Brug lokale PDF'er som arbejds- og laesekopier, men lad DOI/udgiverside vaere den autoritative reference.
- Tilfoej nye kilder baade i `referencer.bib` og her, og gem kun PDF'er naar de er aabent tilgaengelige.
- Nedton claims om effekt, adherence og sikkerhed, hvis kilden kun dokumenterer designprincipper eller kortvarige interventioner.

## Kernespor

| Spor | Primære kilder | Brug i rapporten |
| --- | --- | --- |
| Motivation og adherence | `teixeira2012_sdt_exercise`, `eysenbach2005_law_of_attrition`, `yardley2016_effective_engagement_dbci` | Indledning, problemfelt, diskussion af demotivation/frafald og effektiv digital engagement. |
| Adfærdsdesign | `michie2011_behaviour_change_wheel`, `michie2013_bct_taxonomy_v1`, `oinaskukkonen2009_persuasive_systems_design` | Teoretisk ramme, krav, feedback loops og designprincipper. |
| mHealth, apps og wearables | `middelweerd2014_apps_physical_activity`, `schoeppe2016_app_interventions_review`, `lyons2014_bct_activity_monitors`, `martin2015_mactive`, `brickwood2019_wearable_trackers_meta`, `nahumshani2018_jitai_mobile_health` | Baggrund for app-baseret fysisk aktivitet, prompts, feedback, self-monitoring og just-in-time support. |
| Træningsprogrammering og fleksibel progression | `acsm2009_progression_models`, `currier2026_acsm_resistance_training`, `greig2020_autoregulation_resistance_training`, `larsen2021_autoregulation_systematic_review` | Progressionslogik, cyklusser, deload, afvigelser fra plan og tracker-off completion. |
| Teknisk platform, sikkerhed og privacy | `apple_swiftui_docs`, `apple_activitykit_live_data_docs`, `apple_hig_live_activities`, `apple_healthkit_docs`, `apple_watchconnectivity_docs`, `supabase_rls_docs`, `supabase_securing_api_docs`, `owasp2024_masvs`, `europeanparliament2016_gdpr` | Systemarkitektur, watchOS/Live Activity, HealthKit-afgrænsning, RLS, API-sikkerhed og databeskyttelse. |

## Kildeliste

| BibTeX-noegle | Kilde | Hvorfor den er relevant | Autoritativt link | Lokal PDF |
| --- | --- | --- | --- | --- |
| `teixeira2012_sdt_exercise` | Teixeira et al. (2012), SDT og fysisk aktivitet | Underbygger autonom motivation, behovsstøtte og vedvarende motion. | [DOI](https://doi.org/10.1186/1479-5868-9-78) / [PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC3441783/) | [PDF](referencer/teixeira2012_sdt_exercise.pdf) |
| `michie2011_behaviour_change_wheel` | Michie et al. (2011), Behaviour Change Wheel/COM-B | Giver en ramme for at analysere capability, opportunity og motivation bag træningsadfærd. | [DOI](https://doi.org/10.1186/1748-5908-6-42) | [PDF](referencer/michie2011_behaviour_change_wheel.pdf) |
| `michie2013_bct_taxonomy_v1` | Michie et al. (2013), BCT Taxonomy v1 | Bruges til at navngive appens self-monitoring, feedback, prompts, goals og action planning. | [DOI](https://doi.org/10.1007/s12160-013-9486-6) | [PDF](referencer/michie2013_bct_taxonomy_v1.pdf) |
| `eysenbach2005_law_of_attrition` | Eysenbach (2005), eHealth attrition | Relevant for frafald, lav vedvarende brug og hvorfor friktion i digitale interventioner betyder noget. | [DOI](https://doi.org/10.2196/jmir.7.1.e11) / [JMIR](https://www.jmir.org/2005/1/e11/) | [PDF](referencer/eysenbach2005_law_of_attrition.pdf) |
| `yardley2016_effective_engagement_dbci` | Yardley et al. (2016), effective engagement | Støtter pointen om, at engagement bør forstås som brug, der faktisk understøtter mål-adfærd, ikke bare skærmtid. | [DOI](https://doi.org/10.1016/j.amepre.2016.06.015) | [PDF](referencer/yardley2016_effective_engagement_dbci.pdf) |
| `nahumshani2018_jitai_mobile_health` | Nahum-Shani et al. (2018), JITAI i mHealth | Underbygger fleksibel, kontekstafhængig feedback og timing af støtte. | [DOI](https://doi.org/10.1007/s12160-016-9830-8) | [PDF](referencer/nahumshani2018_jitai_mobile_health.pdf) |
| `middelweerd2014_apps_physical_activity` | Middelweerd et al. (2014), fysisk aktivitetsapps | Viser hvilke BCT'er der typisk optræder i apps, især feedback, self-monitoring og goal setting. | [DOI](https://doi.org/10.1186/s12966-014-0097-9) | [PDF](referencer/middelweerd2014_apps_physical_activity.pdf) |
| `schoeppe2016_app_interventions_review` | Schoeppe et al. (2016), app-interventioner | Systematisk review af app-baserede interventioner for kost, fysisk aktivitet og stillesiddende adfærd. | [DOI](https://doi.org/10.1186/s12966-016-0454-y) | [PDF](referencer/schoeppe2016_app_interventions_review.pdf) |
| `lyons2014_bct_activity_monitors` | Lyons et al. (2014), activity monitors og BCT'er | Relevant for wearables/watchOS, feedback og måling som behavior-change komponent. | [DOI](https://doi.org/10.2196/jmir.3469) / [JMIR](https://www.jmir.org/2014/8/e192/) | [PDF](referencer/lyons2014_bct_activity_monitors.pdf) |
| `martin2015_mactive` | Martin et al. (2015), mActive RCT | Viser at tracking alene kan være utilstrækkeligt, mens automatiserede beskeder kan drive aktivitet. | [DOI](https://doi.org/10.1161/JAHA.115.002239) / [PubMed](https://pubmed.ncbi.nlm.nih.gov/26553211/) | Ikke gemt; direkte PDF-download var blokeret. |
| `brickwood2019_wearable_trackers_meta` | Brickwood et al. (2019), wearable trackers meta-analyse | Relevant for watchOS, tracker-feedback og monitorering som støtte til fysisk aktivitet. | [DOI](https://doi.org/10.2196/11819) / [JMIR](https://mhealth.jmir.org/2019/4/e11819/) | [PDF](referencer/brickwood2019_wearable_trackers_meta.pdf) |
| `acsm2009_progression_models` | ACSM (2009), progression models | Klassisk position stand for resistance-training variabler, progression og programstruktur. | [DOI](https://doi.org/10.1249/MSS.0b013e3181915670) / [PubMed](https://pubmed.ncbi.nlm.nih.gov/19204579/) | Ikke gemt; officiel åben PDF ikke identificeret. |
| `currier2026_acsm_resistance_training` | Currier et al. (2026), ACSM opdateret resistance-training position stand | Ny opdatering af ACSM's resistance-training prescription og derfor central for aktuelle træningsanbefalinger. | [DOI](https://doi.org/10.1249/MSS.0000000000003897) / [PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC12965823/) | Ikke gemt; PMC PDF-download krævede browserbaseret downloadflow. |
| `greig2020_autoregulation_resistance_training` | Greig et al. (2020), autoregulation in resistance training | Underbygger fleksibel justering efter performance, readiness og fatigue. | [DOI](https://doi.org/10.1007/s40279-020-01330-8) | [PDF](referencer/greig2020_autoregulation_resistance_training.pdf) |
| `larsen2021_autoregulation_systematic_review` | Larsen et al. (2021), autoregulation review | Systematisk review af subjektive og objektive autoreguleringsmetoder i styrketræning. | [DOI](https://doi.org/10.7717/peerj.10663) / [PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC7810043/) | Ikke gemt; direkte PDF-download returnerede ikke en PDF i terminalen. |
| `oinaskukkonen2009_persuasive_systems_design` | Oinas-Kukkonen & Harjumaa (2009), Persuasive Systems Design | Brugbar til at analysere feedback, reminders, tailoring og system credibility i appdesignet. | [DOI](https://doi.org/10.17705/1CAIS.02428) / [AIS eLibrary](https://aisel.aisnet.org/cais/vol24/iss1/28/) | [PDF](referencer/oinaskukkonen2009_persuasive_systems_design.pdf) |
| `apple_swiftui_docs` | Apple Developer Documentation, SwiftUI | Teknisk reference for native SwiftUI som appens UI- og state-model. | [Apple](https://developer.apple.com/documentation/SwiftUI) | Web-only. |
| `apple_activitykit_live_data_docs` | Apple Developer Documentation, ActivityKit Live Activities | Teknisk reference for Live Activity lifecycle og synkronisering. | [Apple](https://developer.apple.com/documentation/ActivityKit/displaying-live-data-with-live-activities) | Web-only. |
| `apple_hig_live_activities` | Apple Human Interface Guidelines, Live Activities | Designreference for glanceable aktivitet, Dynamic Island, Apple Watch og interaktive statusflader. | [Apple HIG](https://developer.apple.com/design/human-interface-guidelines/live-activities/) | Web-only. |
| `apple_healthkit_docs` | Apple Developer Documentation, HealthKit | Bruges til privacy- og permissionsafsnit, især hvis HealthKit-afgrænsning omtales. | [Apple](https://developer.apple.com/documentation/healthkit) | Web-only. |
| `apple_watchconnectivity_docs` | Apple Developer Documentation, Watch Connectivity | Teknisk reference for iOS-watchOS dataoverførsel. | [Apple](https://developer.apple.com/documentation/WatchConnectivity) | Web-only. |
| `supabase_rls_docs` | Supabase Docs, Row Level Security | Autoritativ teknisk kilde for RLS som sikkerhedsgrænse. | [Supabase](https://supabase.com/docs/guides/database/postgres/row-level-security) | Web-only. |
| `supabase_securing_api_docs` | Supabase Docs, Securing your API | Supplerer RLS-afsnittet med API-eksponering og public schema-risici. | [Supabase](https://supabase.com/docs/guides/api/securing-your-api) | Web-only. |
| `owasp2024_masvs` | OWASP MASVS 2.1.0 | Bruges som mobil sikkerhedsreference for app-/backend-grænser og verifikation. | [OWASP release](https://github.com/OWASP/masvs/releases/tag/v2.1.0) | [PDF](referencer/owasp2024_masvs_v2_1_0.pdf) |
| `europeanparliament2016_gdpr` | Regulation (EU) 2016/679, GDPR | Autoritativ juridisk kilde for persondata, privacy og databehandlingsafsnit. | [EUR-Lex](https://eur-lex.europa.eu/eli/reg/2016/679/oj) | [PDF](referencer/europeanparliament2016_gdpr.pdf) |

## PDF-status

Lokale PDF'er er gemt i `referencer/` med samme stem som BibTeX-noeglen. Fire kilder er bevidst uden lokal PDF: `martin2015_mactive`, `acsm2009_progression_models`, `currier2026_acsm_resistance_training` og `larsen2021_autoregulation_systematic_review`. De er stadig præcist registreret med DOI, PMID/PMCID hvor relevant og autoritativt link.
