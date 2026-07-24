# Zai (zai)

Zai (hellozai.com, formerly Assembly Payments / Assembly) is an Australian payments and Payments-as-a-Service provider headquartered in Melbourne. It gives platforms, marketplaces and vertical software companies a programmable way to onboard users, hold funds in managed wallet accounts, collect pay-ins (card, direct debit, BPAY, PayID), and disburse multi-party pay-outs in a single transaction flow — layered with Australia's New Payments Platform rails via dedicated PayID and PayTo APIs.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/zai/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/zai/refs/heads/main/apis.yml)

## Tags

- Payments
- Australia
- Payment Gateway
- Payment Processing
- Marketplace Payments
- Payments-as-a-Service
- Real-Time Payments
- Account-to-Account
- Open Banking
- PayTo
- PayID
- NPP

## Timestamps

- **Created:** 2026-07-24
- **Modified:** 2026-07-24

## APIs

### Zai Assembly API

Core payments platform API — onboard users, manage wallet accounts, items, bank/card accounts, companies, fees, tokens, callbacks and batch transactions to collect pay-ins and disburse multi-party pay-outs. OpenAPI 3.0.0, version 2.3, 89 documented paths, OAuth2 client-credentials.

- **Human URL:** [https://developer.hellozai.com/reference/overview](https://developer.hellozai.com/reference/overview)
- **Base URL:** `https://secure.api.promisepay.com`
- [OpenAPI](openapi/zai-assembly-api.json)
- [Documentation](https://developer.hellozai.com/docs)
- [API Reference](https://developer.hellozai.com/reference/overview)

### Zai Virtual Accounts and PayIDs API

Create and manage Virtual Accounts and PayIDs on the New Payments Platform (NPP) for real-time account-to-account pay-ins to uniquely addressable virtual accounts. OpenAPI 3.0.0, version 0.12-external, 8 paths.

- **Human URL:** [https://developer.hellozai.com/reference/overview-va](https://developer.hellozai.com/reference/overview-va)
- **Base URL:** `https://au-0000.api.assemblypay.com`
- [OpenAPI](openapi/zai-virtual-accounts-payid.json)
- [API Reference](https://developer.hellozai.com/reference/overview-va)

### Zai PayTo API

Create and manage PayTo agreements (mandated real-time debits) and initiate payments against them over the NPP. OpenAPI 3.0.1, version 1.4-external, 10 paths, bearer-token auth.

- **Human URL:** [https://developer.hellozai.com/reference/overview-1](https://developer.hellozai.com/reference/overview-1)
- **Base URL:** `https://au-0000.api.assemblypay.com/payto/`
- [OpenAPI](openapi/zai-payto.json)
- [Documentation](https://developer.hellozai.com/docs/payto)
- [API Reference](https://developer.hellozai.com/reference/overview-1)

### Zai Asynchronous API

Submit long-running operations and retrieve their results without blocking, complementing the synchronous Assembly API. OpenAPI 3.0.0, version 1.0.0, 3 paths.

- **Human URL:** [https://developer.hellozai.com/reference/async-overview](https://developer.hellozai.com/reference/async-overview)
- **Base URL:** `https://tnq.api.assemblypay.com/`
- [OpenAPI](openapi/zai-async-api.json)
- [API Reference](https://developer.hellozai.com/reference/async-overview)

## Common Properties

- [Website](https://www.hellozai.com/)
- [Developer Portal](https://developer.hellozai.com/)
- [Documentation](https://developer.hellozai.com/docs)
- [Getting Started](https://developer.hellozai.com/docs/developer-checklist)
- [Webhooks](https://developer.hellozai.com/docs/webhooks)
- [Status Page](https://status.hellozai.com/)
- [Pricing](https://www.hellozai.com/pricing)
- [Blog](https://blog.hellozai.com/)
- [Support](https://support.hellozai.com/)
- [Sign Up / Dashboard](https://dashboard.hellozai.com/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
