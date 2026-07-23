---
name: Originate an ACH payment
description: Create an outgoing ACH credit or debit with idempotency, then track or cancel it.
api: openapi/customers-bank-ach-openapi.json
operations: [post-outgoing-credit, post-outgoing-debit, get-outgoing-id, post-outgoing-id-cancel, post-outgoing-id-reverse]
---

# Originate an ACH payment

## Steps

1. **Authenticate** — obtain a Bearer token (see customers-bank-authenticate-and-list-accounts).
2. **Generate an idempotency key** — a fresh UUID v4 for this payment.
3. **Create the payment** — `post-outgoing-credit` (`POST /ach/v1/outgoing/credit`) or
   `post-outgoing-debit` (`POST /ach/v1/outgoing/debit`). Send the `x-idempotency-key` header.
4. **Track it** — `get-outgoing-id` (`GET /ach/v1/outgoing/{id}`); watch webhook events
   `ach.outgoing-initiated` → `ach.outgoing-completed` / `ach.outgoing-returned`.
5. **Cancel or reverse if needed** — `post-outgoing-id-cancel` (`POST /ach/v1/outgoing/{id}/cancel`)
   or `post-outgoing-id-reverse` (`POST /ach/v1/outgoing/{id}/reverse`), each with a new idempotency key.

## Rules
- POST requires `x-idempotency-key` (UUID v4). Retrying the SAME key returns the original result;
  a different payload on the same key → 422; concurrent retry → 409. Keys are retained 48h.
- Subscribe to `ach.*` webhooks (HMAC-SHA256 verified) for async status.
