# Private Messenger Follow-Up Audit

Dato: 2026-04-28  
Kilde: private Messenger-snapshots i `[private-raw]/messenger/deeper-2026-04-28/private-thread-captures/`.

Denne public audit gengiver ingen navne, mailadresser, profilbilleder, chat-ID'er eller direkte beskedcitater. Private tråde er kun kodet som `MT-01` til `MT-06`.

## Hvad Der Blev Gennemgået

Efter brugerens kritik blev Messenger åbnet igen via browser-use, og de første synlige beta-relaterede private tråde i chatlisten blev fanget som private rå-screenshots/DOM-snapshots. Derudover blev beta-gruppetråden igen medtaget som referencepunkt.

| Scope | Råstatus | Public brug |
| --- | --- | --- |
| Private synlige DMs | 5 private tester-/interessenttråde fanget privat | Kun temaer: adgang, e-mail-invitation, interesse, set/reaction |
| Beta-gruppe | Gruppechat fanget igen som reference | Temaer sammenholdes med eksisterende Messenger-dybdeanalyse |
| Android beta-gruppe | Synlig som separat kanal i chatlisten | Noteres som rekrutterings-/platformsperspektiv, ikke feedbackkilde |

## Centrale Fund

De private synlige tråde dokumenterer først og fremmest beta-administration, ikke dyb evaluering:

- offentlig betaadgang blev ryddet op, fordi det var uklart hvem der havde hentet appen via link,
- flere personer blev bedt om at sende den e-mail, de ville bruge til betaadgang,
- gamle links blev omtalt som noget der skulle lukkes til fordel for direkte invitation,
- mindst én privat tråd viste positiv interesse i at være med,
- enkelte tråde viste kort respons eller reaktion, ikke detaljeret appkritik,
- en separat Android-beta-kontekst var synlig, hvilket understøtter platform-bias-afsnittet.

## Rapportkonsekvens

Private Messenger-tråde bør ikke beskrives som individuelle interviews. De er bedre dokumenteret som beta-logistik og rekrutteringsopfølgning.

Stærk formulering:

> Private Messenger-opfølgninger blev brugt til at rydde op i beta-adgang og invitere testere mere kontrolleret via e-mail, efter et offentligt link gjorde det svært at vide hvem der faktisk havde installeret appen.

Formulering der bør undgås:

> De private samtaler viser hvad hver beta-tester mente om appen.

## Metodisk Betydning

Denne opfølgning styrker bachelorens metodekritik. Den viser at betaen havde et reelt datastyringsproblem: et offentligt TestFlight-/beta-link giver lav friktion, men dårlig sporbarhed. Overgangen til e-mailinvitationer er derfor et projektledelses- og evalueringsvalg:

- bedre kontrol over hvem der er inviteret,
- bedre mulighed for pseudonymiseret testerstatus,
- mindre risiko for at forveksle "har modtaget link" med "har testet appen",
- tydeligere samtykke- og feedbackspor til rapporten.

## Åbne Gaps

- Ikke alle historiske private Messenger-tråde er garanteret gennemgået; scope er de synlige beta-relaterede tråde i chatlisten under denne run.
- Trådene indeholder potentiel PII, herunder e-mailadresser, og må ikke kopieres public.
- Der mangler stadig en separat privat deltagerliste, der kobler pseudonym, kanal, TestFlight-status, feedbackstatus og samtykke.
- Private tråde giver ikke nok grundlag til en kvantitativ beta-tester-rapport.
