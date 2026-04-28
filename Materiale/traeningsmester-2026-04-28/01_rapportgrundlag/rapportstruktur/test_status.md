# Tabel: Test- Og Buildstatus

| Test/build | Resultat | Rapportnote |
| --- | --- | --- |
| iOS Debug build | Bestået | Klienten kan bygges med den aktuelle worktree |
| Unit tests | 556 bestået, 0 fejlet | Refresh på iOS 26.4 bestod efter én simulator-infra retry; dækker bl.a. DTO, payloads, progress, onboarding, settings, Live Activity og cykluslogik |
| Integration tests | 1 bestået, 4 skipped, 0 fejlet | Fuld auth/admin-test kræver Supabase test credentials |
| watchOS build | Bestået | Companion app og widget dependency byggede |
| Live Activity build | Bestået | Extension blev bygget og embedded i app target |
| Xcode MCP launch/screenshot | Bestået | App blev lanceret på `TM-iPhone-16-Pro-iOS26` iOS 26.4 med testkonto, og 13 aktuelle app-screenshots blev gemt |
| Edge Function helper tests | Ikke kørt | Deno manglede på maskinen |
