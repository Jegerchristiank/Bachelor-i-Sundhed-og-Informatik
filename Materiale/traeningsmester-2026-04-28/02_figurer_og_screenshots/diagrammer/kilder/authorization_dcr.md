# DCR-tekst: autorisation og dataadgang

Dette er en tekstuel DCR-kilde, der kan omsættes til DCR-graf. Den beskriver sikkerhedsregler ud fra repoets faktiske arkitektur: anon-klient, Supabase Auth, RLS, RPC og Edge Functions.

## Events

- `LoadAppEnvironment`
- `RejectInvalidEnvironment`
- `CreateAnonSupabaseClient`
- `AuthenticateUser`
- `ResolveSession`
- `ReadOwnData`
- `WriteOwnData`
- `ReadSharedPlan`
- `WriteSharedPlanIfCanEdit`
- `CallTrainerClientFunction`
- `CallAdminFunction`
- `ValidateAdminServerSide`
- `RejectAdminOperation`
- `CallImportFunction`
- `UseServiceRoleInsideFunction`
- `PersistAuditEvent`
- `WriteTrackerLog`
- `WriteLiveActivityTrackerLog`
- `DeduplicateClientAction`
- `DenyCrossUserAccess`

## Conditions

- `CreateAnonSupabaseClient` requires `LoadAppEnvironment`.
- `RejectInvalidEnvironment` is a response to `LoadAppEnvironment` if key is placeholder or service_role.
- `AuthenticateUser` requires `CreateAnonSupabaseClient`.
- `ResolveSession` requires `AuthenticateUser`.
- `ReadOwnData` requires `ResolveSession`.
- `WriteOwnData` requires `ResolveSession`.
- `ReadSharedPlan` requires `ResolveSession`.
- `WriteSharedPlanIfCanEdit` requires `ResolveSession`.
- `CallTrainerClientFunction` requires `ResolveSession`.
- `CallAdminFunction` requires `ResolveSession`.
- `ValidateAdminServerSide` requires `CallAdminFunction`.
- `UseServiceRoleInsideFunction` requires `CallTrainerClientFunction` or `CallAdminFunction` or `CallImportFunction`.
- `WriteTrackerLog` requires `ResolveSession`.
- `WriteLiveActivityTrackerLog` requires `ResolveSession` and `DeduplicateClientAction`.

## Responses

- After `CallAdminFunction`, `ValidateAdminServerSide` must occur.
- If `ValidateAdminServerSide` fails, `RejectAdminOperation` must occur.
- After privileged admin/trainer mutation, `PersistAuditEvent` should occur.
- If RLS ownership/shared-access checks fail, `DenyCrossUserAccess` must occur.
- For Live Activity writes, `DeduplicateClientAction` should occur before persisting trackerlog.

## Exclusions

- `RejectInvalidEnvironment` excludes `CreateAnonSupabaseClient`.
- `RejectAdminOperation` excludes privileged admin mutation.
- `DenyCrossUserAccess` excludes the requested read/write operation.

## Security notes

- Service-role credentials are never a client-side event.
- `UseServiceRoleInsideFunction` is only legal inside Supabase Edge Function runtime.
- RLS and `auth.uid()` are the primary authorization boundary for user-bound tables.
- Admin UI state is never sufficient; server-side validation is mandatory.

