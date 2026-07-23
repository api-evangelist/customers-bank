---
name: Authenticate and list accounts
description: Obtain an OAuth2 client-credentials Bearer token and list/inspect embedded-banking accounts.
api: openapi/customers-bank-security-openapi.json, openapi/customers-bank-accounts-openapi.json
operations: [post-oauth2-token, get, get-accountid, get-accountid-transactions]
---

# Authenticate and list accounts

Use this to bootstrap any Customers Bank integration: get a token, then read accounts.

## Steps

1. **Get an access token** — `post-oauth2-token` on the Security API
   (`POST /security/v1/oauth2/token`). Send `application/x-www-form-urlencoded` with
   `grant_type=client_credentials`, `client_Id`, and `client_Secret`. Cache the token for
   `expires_in` seconds (≈3600). Reuse it across all subsequent calls.
2. **Authorize every request** — set `Authorization: Bearer {access_token}` on all resource calls.
3. **List accounts** — `get` on the Accounts API (`GET /accounts/v1/`). Paginate with
   `paginateResults`, `page`, `perPage`, `sortOn`, `sortAscending`.
4. **Inspect one account** — `get-accountid` (`GET /accounts/v1/{accountId}`).
5. **Search transactions** — `get-accountid-transactions` (`GET /accounts/v1/{accountId}/transactions`).

## Rules
- Read operations (GET) do not need an idempotency key.
- 401 → token expired: re-run step 1. 403 → check IP allowlist / entitlements.
- Errors are RFC 9457 `application/problem+json` (see errors/customers-bank-problem-types.yml).
