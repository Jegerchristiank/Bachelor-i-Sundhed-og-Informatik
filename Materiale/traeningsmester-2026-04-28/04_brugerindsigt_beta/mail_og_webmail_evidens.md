# Mail- Og Webmail-Evidens

Dato: 2026-04-28  
Kilder: scoped Gmail-connector-søgninger og KU webmail via in-app browser. Rå mails, screenshots og DOM-udtræk ligger kun i privat råmappe. Public dokumentation bruger kun datoer, emner i redigeret form og korte parafraser.

## Scope

Der blev ikke lavet bred inbox-trawling. Søgningerne var afgrænset til:

- vejleder/bachelor/TræningsMester/TestFlight i Gmail,
- TestFlight- og Traeningsmester-relaterede mails i Gmail,
- træningsvideo-/målgruppekorrespondance i Gmail,
- træningscenter-/fitnesscenter-outreach i Gmail,
- Karsten Vrangbæk, bachelorprojekt og TræningsMester i KU webmail.

## Gmail

| Query-scope | Resultat | Rapportbrug |
| --- | --- | --- |
| Karsten Vrangbæk + bachelor/TræningsMester/TestFlight | Ingen relevante hits i den tilsluttede Gmail-konto | Underbygger, at vejlederkorrespondance primært skal findes i KU webmail |
| Traeningsmester/TestFlight efter 2026-03-01 | Invitation 2026-03-25 og builds 1.0 (5/6/8), 2.0 (1-12) frem til 2026-04-25 | TestFlight-tidslinje og projektledelsesafsnit |
| Xcode Cloud/Supabase i samme projektscope | Build-success 2026-04-20 og Supabase security-advisor 2026-04-21 | Verifikation, CI-spor og sikkerhedsrefleksion |
| Træningsvideo-korrespondance | Ekstern dialog 2026-04-28 om målgruppe og video-/indholdsproduktion | Kan bruges til målgruppeformulering og videre arbejde med øvelsesmedier |
| Træningscenter-/fitnesscenter-outreach | Test-/outreach-mail 2026-04-13 om at få lov til at filme øvelsesvideoer i et lokalt center | Brug som dokumentation for indholdsstrategi, stakeholder-afhængighed og privacy-overvejelser, ikke som bevis for en færdig centeraftale |

Den relevante målgruppeformulering fra træningsvideo-dialogen kan parafraseres sådan i rapporten: appen er rettet mod personer, der har svært ved at strukturere og fastholde træning, samt personlige trænere, der ønsker bedre overblik og synkronisering af klientprogrammer. Den samme dialog nævner automatisk progression og AI-generering/tilpasning som produktretning, men bør ikke bruges som forskningsdata om brugeradfærd.

Se også `traeningscenter_korrespondance.md` for den særskilte, anonymiserede opsummering af træningscenter-sporet.

## KU Webmail

| Query-scope | Resultat | Rapportbrug |
| --- | --- | --- |
| `Karsten Vrangbæk bachelor TræningsMester` | Ingen resultater | Viser at appnavn og vejledernavn ikke lå samlet i webmailresultatet |
| `Karsten Vrangbæk` | Resultater om bacheloraccept/registrering i februar 2026 samt ældre ESG-/valgfagskorrespondance | Bekræfter vejleder-/bacheloradministrativt spor, men ESG skal holdes metodisk adskilt |
| `bachelorprojekt` | Resultater om accept, kvitteringer, studieinformation og bachelorprojektkursus | Bruges som kontekst for formel bachelorramme |
| `TræningsMester OR Traeningsmester` | Ingen resultater i KU webmail-søgningen | Appspecifik korrespondance ligger ikke tydeligt i KU webmail-scope |

## Redaktionsnoter

- Personnavne fra Messenger-testere er ikke brugt i public materiale.
- Mailadresser, telefonnumre, adresseblokke, TestFlight-linkparametre, Apple-identifikatorer og mødelinks er ikke gengivet.
- Vejledernavnet er kun brugt, fordi brugeren eksplicit bad om at undersøge netop denne korrespondance, og fordi det er fagligt relevant for bachelorens formelle ramme.
- Public brug af mail/webmail skal være parafraseret og kildekritisk, ikke direkte citatbaseret.
- Træningscenter-sporet må ikke fremstilles som en indgået aftale, medmindre en senere redigeret kilde dokumenterer et konkret ja fra et center.
