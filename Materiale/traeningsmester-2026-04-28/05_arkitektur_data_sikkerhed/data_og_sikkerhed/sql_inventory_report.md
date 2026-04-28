# SQL Inventory Report

Dato: 2026-04-28  
Kilde: `SUPABASE_MASTER_SETUP.sql`

## Genererede Inventories

| Fil | Indhold | Linjer inkl. header |
| --- | --- | --- |
| `sql_object_inventory.csv` | Tabeller, views, functions og policies med linjenummer i master-setup | 228 |
| `rls_enable_force_inventory.csv` | Tabeller hvor RLS enable/force er registreret med linjenummer | 36 |

## Hovedobservationer

- Master-setup indeholder både schema, helper functions, views, RLS-politikker og katalog-/cyklusudvidelser.
- RLS enable/force er registreret for centrale brugerbundne tabeller, herunder programmer, workouts, workout exercises, trackerlog, completion events, settings, relationer og training import/cycle-relaterede tabeller i senere sektioner.
- SQL-sporet understøtter rapportens sikkerhedsclaim, men public materialet skal stadig skelne mellem "policy review udført" og "credential-baseret cross-user integrationstest udført".

## Brug I Rapporten

Brug CSV'erne som bilag eller intern kilde til at dokumentere, at datamodellen ikke kun er beskrevet i prosa. De giver sporbarhed fra rapportens datamodel-/sikkerhedsafsnit til konkrete linjer i master-setup.

