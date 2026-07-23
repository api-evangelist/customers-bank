---
name: Subscribe to webhooks and verify HMAC
description: Discover event types, create a signed webhook subscription, and verify inbound HMAC signatures.
api: openapi/customers-bank-webhooks-openapi.json
operations: [get-eventtypes, post, get-id, post-id-disable, post-id-enable, get-eventhistory]
---

# Subscribe to webhooks and verify HMAC

## Steps

1. **Authenticate** — obtain a Bearer token.
2. **List event types** — `get-eventtypes` (`GET /webhooks/v1/EventTypes`). 61 event types exist across
   accounts, ach, wires, fednow, rtp, transfers, consumerlending, and partners domains
   (see asyncapi/customers-bank-webhooks.yml).
3. **Create a subscription** — `post` (`POST /webhooks/v1/`) with `eventTypeName`, `callbackUrl`,
   `secretText` (Base64-encoded), `description`, and an `X-Idempotency-Key`.
4. **Verify each callback** — reconstruct the HMAC-SHA256 signature from the callback body hash,
   `Authorization-Timestamp`, host, and path; compare to the `Authorization: HMAC-SHA256 Signature=`
   header. Reject on mismatch. (See /docs/hmac-signature-validation.)
5. **Operate** — `get-id`, `post-id-disable` / `post-id-enable`, and review delivery via
   `get-eventhistory` (`GET /webhooks/v1/EventHistory`).

## Rules
- Always verify the HMAC signature before trusting a callback.
- Restrict inbound callback traffic to the documented webhook IP allowlist.
