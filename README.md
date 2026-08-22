# Customers Bank (customers-bank)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Customers Bank is a Pennsylvania state-chartered, FDIC-insured full-service commercial bank and the principal subsidiary of Customers Bancorp, Inc. (NYSE: CUBI), a super-regional bank holding company (~$22B in assets) headquartered in West Reading, Pennsylvania. Alongside traditional commercial and consumer banking, it runs a national embedded-banking / Banking-as-a-Service platform that exposes a first-party, OAuth2-secured REST API surface to fintech and corporate partners through a public ReadMe developer portal at [cubiapi.readme.io](https://cubiapi.readme.io), including a hosted Model Context Protocol (MCP) server for AI agents.

This is proprietary, partner-gated integration infrastructure — not an FDX or CFPB Section 1033 consumer-permissioned data-sharing API. No FDX-conformant or Section 1033 data-access endpoint is publicly documented. The surface is sandbox-first (`cubi-sandbox-api.customersbank.com`), secured by OAuth2 client-credentials with HMAC-signed webhooks.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/customers-bank/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/customers-bank/refs/heads/main/apis.yml)

## Tags

- Financial Services
- Banking
- United States
- Banking-as-a-Service
- Embedded Finance
- Payments
- Commercial Banking

## Timestamps

- **Created:** 2026-07-23
- **Modified:** 2026-07-23

## APIs

Ten first-party product APIs are documented on the developer portal and harvested here as verbatim OpenAPI 3.0.1 specifications (173 documented paths total). All share the sandbox host `https://cubi-sandbox-api.customersbank.com` and OAuth2 client-credentials auth issued by the Security API.

### Customers Bank Accounts API

List accounts, retrieve account and subaccount detail, search transactions, manage tags and account entitlements, and download account data.

- **Human URL:** [https://cubiapi.readme.io/docs/accounts-3](https://cubiapi.readme.io/docs/accounts-3)
- **Base URL:** `https://cubi-sandbox-api.customersbank.com/accounts/v1`
- [OpenAPI](openapi/customers-bank-accounts-openapi.json)

### Customers Bank ACH API

ACH payment origination and management.

- **Human URL:** [https://cubiapi.readme.io/reference](https://cubiapi.readme.io/reference)
- **Base URL:** `https://cubi-sandbox-api.customersbank.com/ach/v1`
- [OpenAPI](openapi/customers-bank-ach-openapi.json)

### Customers Bank Consumer Lending API

Create and search loan applications, retrieve program (policy) details, and originate, fund, complete and cancel loans.

- **Human URL:** [https://cubiapi.readme.io/docs/loan-application](https://cubiapi.readme.io/docs/loan-application)
- **Base URL:** `https://cubi-sandbox-api.customersbank.com/consumerlending/v1`
- [OpenAPI](openapi/customers-bank-consumerlending-openapi.json)

### Customers Bank Instant Payments API

Real-time payment origination and management.

- **Human URL:** [https://cubiapi.readme.io/reference](https://cubiapi.readme.io/reference)
- **Base URL:** `https://cubi-sandbox-api.customersbank.com/InstantPayments/v1`
- [OpenAPI](openapi/customers-bank-instantpayments-openapi.json)

### Customers Bank IT Operations API

Reference data: bank lookups (ABA, BIC), correspondent (SSI) instructions across payment rails, and WebPubSub client access.

- **Human URL:** [https://cubiapi.readme.io/reference](https://cubiapi.readme.io/reference)
- **Base URL:** `https://cubi-sandbox-api.customersbank.com/itoperations/v1`
- [OpenAPI](openapi/customers-bank-itoperations-openapi.json)

### Customers Bank Partners API

Manage partners, users, customers, messages, API credentials and client credentials (M2M application registration).

- **Human URL:** [https://cubiapi.readme.io/docs/partners-1](https://cubiapi.readme.io/docs/partners-1)
- **Base URL:** `https://cubi-sandbox-api.customersbank.com/partners/v1`
- [OpenAPI](openapi/customers-bank-partners-openapi.json)

### Customers Bank Security API

Issues bearer access tokens via the OAuth2 client-credentials grant for machine-to-machine access to all platform APIs.

- **Human URL:** [https://cubiapi.readme.io/docs/authenticate-1](https://cubiapi.readme.io/docs/authenticate-1)
- **Base URL:** `https://cubi-sandbox-api.customersbank.com/security/v1`
- [OpenAPI](openapi/customers-bank-security-openapi.json)

### Customers Bank Transfers API

Book transfers, address-book payee management and approvals, account-link settings, instant-transfer approvals, and account entitlements.

- **Human URL:** [https://cubiapi.readme.io/docs/book-transfers](https://cubiapi.readme.io/docs/book-transfers)
- **Base URL:** `https://cubi-sandbox-api.customersbank.com/transfers/v1`
- [OpenAPI](openapi/customers-bank-transfers-openapi.json)

### Customers Bank Webhooks API

Subscribe to platform event types, deliver HMAC-signed event payloads, and manage webhook IP allowlists.

- **Human URL:** [https://cubiapi.readme.io/docs/webhooks-1](https://cubiapi.readme.io/docs/webhooks-1)
- **Base URL:** `https://cubi-sandbox-api.customersbank.com/webhooks/v1`
- [OpenAPI](openapi/customers-bank-webhooks-openapi.json)

### Customers Bank Wires API

Originate and manage incoming and outgoing wire transfers (v2), retrieve purpose and reference-data codes, and manage wire account entitlements.

- **Human URL:** [https://cubiapi.readme.io/docs/outgoing-wires](https://cubiapi.readme.io/docs/outgoing-wires)
- **Base URL:** `https://cubi-sandbox-api.customersbank.com/Wires/v2`
- [OpenAPI](openapi/customers-bank-wires-openapi.json)

## Common Properties

- [Website](https://www.customersbank.com)
- [Developer Portal](https://cubiapi.readme.io)
- [Documentation](https://cubiapi.readme.io/docs/getting-started)
- [MCP Server](https://cubiapi.readme.io/mcp)
- [GitHub Organization](https://github.com/CustomersBank)
- [LinkedIn](https://www.linkedin.com/company/customers-bank)
- [Privacy Policy](https://www.customersbank.com/privacy-policy/)
- [Terms of Service](https://www.customersbank.com/terms-of-use/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
