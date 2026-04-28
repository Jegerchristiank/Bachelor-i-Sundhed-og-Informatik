# Edge Function-Overblik

Kilde: `supabase/functions/*/index.ts` pr. 2026-04-28.

| Function | Primært ansvar | Hvorfor klienten ikke gør det direkte |
| --- | --- | --- |
| `admin-control-center` | Server-valideret admin bruger-CRUD og aktivitetsfeed | Kræver service-role/admin guard |
| `trainer-client-manage` | Træner-klient relationer, invites og klientoperationer | Kræver tværbruger-validering |
| `program-review-analyze` | AI-analyse af træningsprogram | OpenAI/service secrets må ikke ligge i appen |
| `program-plan-questionnaire` | AI-støttet plan/spørgeskema | Samme secret- og kontrolhensyn |
| `program-import-normalize` | Normalisering af gammel programstruktur | Backend kan validere og auditere import |
| `history-import-normalize` | Normalisering af historiske træningslogs | Reducerer risiko ved bulk-import |
| `training-import-manage` | Importjob-orchestrering, preview og commit | Jobstatus og brugeradgang styres server-side |
| `billing-create-checkout-session` | Web checkout/session helper | Betalingsserverflow må ikke ligge i klient |
| `billing-confirm-checkout-session` | Bekræftelse af checkout/session | Server-side validering før app-state opdateres |

## Rapportvinkel

Edge Functions udgør systemets sikkerheds- og interoperabilitetslag for de flows, hvor appen enten skal tale med eksterne services, bruge højere privilegier eller validere tværbrugeradgang.

