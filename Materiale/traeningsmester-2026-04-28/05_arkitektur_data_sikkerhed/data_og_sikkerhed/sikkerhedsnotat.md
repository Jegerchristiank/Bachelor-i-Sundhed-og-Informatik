# Sikkerhedsnotat

Dato: 2026-04-28

## Centrale Beslutninger

- Klienten bruger kun Supabase anon/publishable key.
- `AppEnvironment` validerer miljø ved opstart og afviser service-role tokens.
- RLS er primær adgangskontrol for brugerdata.
- Admin, trainer-client, import, AI og billing håndteres via Edge Functions eller SQL/RPC.
- Watch og Live Activity bruger eksisterende bruger-session/snapshot, ikke service-role.
- Tracker- og completion-writes er idempotente via `client_action_id`.

## Risici Og Kontroller

| Risiko | Kontrol | Rest-risiko |
| --- | --- | --- |
| Service-role i app binary | `AppEnvironment` role-dekoder og key-validering | Kræver release-review af xcconfig/Info.plist |
| Cross-user dataadgang | RLS, helper functions og typed repositories | Integration credentials manglede for fuld cross-user test |
| Admin UI bypass | Edge Function + SQL admin guard | Admin integration tests skipped uden admin credentials |
| Live Activity duplicate writes | `client_action_id` unique index | Afhænger af korrekt snapshot/session |
| Import af privat historik | Jobmodel og preview/commit flow | Kræver brugersamtykke og redaktion i rapport |
| Social/mail screenshots i repo | Rådata holdes udenfor repo | Final visuel PII-gennemgang før push kræves |

## Verificeret I Denne Run

- iOS Debug build: bestået.
- watchOS build: bestået.
- Live Activity build: bestået.
- Unit tests: 556 tests, 0 failures.
- Integration tests: 5 tests, 0 failures, 4 skipped pga. manglende Supabase test credentials.
- Deno/Edge Function helper tests: ikke kørt, fordi Deno ikke var installeret.

## Rapportbrug

Notatet kan bruges i afsnit om sikkerhed, dataminimering og softwarearkitektur. Det vigtigste argument er, at sikkerhedsgrænsen ligger i backend/RLS, mens SwiftUI-klienten er et typed, client-safe lag.

