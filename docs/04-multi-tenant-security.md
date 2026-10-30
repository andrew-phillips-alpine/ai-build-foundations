# Multi-Tenant Security

Rules for apps where several clients share one platform.

## The golden rule

Never trust a tenant ID from the request. The login proves who the user is, not which tenant they may act for. Verify membership before every data operation.

## Route authorisation: the only four patterns

Every API route states which pattern it uses in a comment at the top.

1. **Tenant-scoped (default):** verify the user, returning 401 if there is none. Take the tenant ID from the body, query or record, and verify membership, returning 403 if it fails. Filter every privileged query by that tenant.
2. **Admin:** an admin guard is the first line of the handler.
3. **Machine:** a cron secret or a verified webhook signature. Fail closed once the secret is configured.
4. **Public:** no auth by design. Rate limited, and listed in a public-routes register with the reason.

Never:

- Take identity from a header or request body field.
- Use a cached session for an authorisation decision. Re-verify the user.
- Read an admin flag from user-editable metadata.
- Run a privileged query without a tenant filter.

## Row-level security

Every table holding tenant data has:

- A `tenant_id` column.
- Row-level security enabled.
- An isolation policy limiting rows to tenants the user belongs to, on both read and write.
- An admin bypass and a service-role bypass for server-side jobs.

Never write a policy that allows everyone to read or insert.

## Testing

For each route, test that an anonymous request gets 401 and a member of another tenant gets 403.

## Auditing

The `route-auth-auditor` subagent in `claude/agents/` checks every route against these patterns and reports red flags with file and line.
