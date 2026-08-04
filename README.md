# Zai (zai)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
