---
name: Originate a consumer loan
description: Create a loan application, then originate, fund, and complete the loan.
api: openapi/customers-bank-consumerlending-openapi.json
operations: [post-application, get-application-id, get-program-id, post-loan-id-funding, post-loan-id-complete, post-loan-id-cancel]
---

# Originate a consumer loan

## Steps

1. **Authenticate** — obtain a Bearer token.
2. **Review the program** — `get-program-id` (`GET /consumerlending/v1/program/{id}`) for policy details.
3. **Create an application** — `post-application` (`POST /consumerlending/v1/application`) with an
   `x-idempotency-key`. Track it with `get-application-id` (`GET /consumerlending/v1/application/{id}`);
   watch `consumerlending.loanapplication-created` → `-received` → `-rejected`.
4. **Fund the loan** — `post-loan-id-funding` (`POST /consumerlending/v1/loan/{id}/funding`).
5. **Complete or cancel** — `post-loan-id-complete` (`POST /consumerlending/v1/loan/{id}/complete`)
   or `post-loan-id-cancel` (`POST /consumerlending/v1/loan/{id}/cancel`).

## Rules
- Every POST needs a unique `x-idempotency-key` (UUID v4, 48h retention).
- Subscribe to `consumerlending.*` webhooks for async application/loan status.
