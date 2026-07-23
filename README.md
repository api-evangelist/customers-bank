# Customers Bank (customers-bank)

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
