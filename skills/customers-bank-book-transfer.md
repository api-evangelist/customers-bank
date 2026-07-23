---
name: Create and approve a book transfer
description: Move funds between accounts with an internal book transfer, including the approval flow.
api: openapi/customers-bank-transfers-openapi.json
operations: [post, get-id, post-id-approve, post-id-decline]
---

# Create and approve a book transfer

## Steps

1. **Authenticate** — obtain a Bearer token.
2. **Generate an idempotency key** — UUID v4.
3. **Create the transfer** — `post` on the Transfers API (`POST /transfers/v1/`) with the
   `x-idempotency-key` header and the source/destination accounts and amount.
4. **Check status** — `get-id` (`GET /transfers/v1/{id}`). A transfer may emit
   `transfers.book-requires-approval`.
5. **Approve or decline** — `post-id-approve` (`POST /transfers/v1/{id}/approve`) or
   `post-id-decline` (`POST /transfers/v1/{id}/decline`).
6. **Confirm completion** — watch `transfers.book-completed` (or `transfers.book-declined`).

## Rules
- POST requires `x-idempotency-key`; GET/PUT/DELETE do not.
- Errors are RFC 9457 `application/problem+json`.
