# Paystone (paystone)

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

Paystone is a Canadian payment processing and customer-engagement company headquartered in London, Ontario, positioning itself as one of the country's largest bank-independent payment processors. It sells card-present terminals, online checkout and hosted payment pages, virtual terminals, invoicing, and recurring billing to Canadian SMBs, and layers loyalty, gift-card, and reputation-marketing products on top of the payment rails. Paystone owns DataCandy, a long-standing Canadian gift-card and loyalty platform — and it is DataCandy that carries Paystone's public, self-serve, documented API surface.

Paystone's core card-acquiring and payment-gateway processing is delivered as a merchant product rather than a publicly self-serve developer API. The honest developer story here is the DataCandy gift-and-loyalty platform API, not a public payments/acquiring API.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/paystone/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/paystone/refs/heads/main/apis.yml)

## Tags

- Payments
- Canada
- Payment Processing
- Acquiring
- Gift Cards
- Loyalty
- Subscriptions
- Billing
- Merchant Services

## Timestamps

- **Created:** 2026-07-24
- **Modified:** 2026-07-24

## APIs

### Paystone DataCandy API

The public, documented REST API for Paystone's DataCandy gift-card and loyalty platform, built on API Platform (Hydra/JSON-LD) and served from `api.paystone.com`. It exposes 28 documented paths across 14 resource groups — client and merchant management, contacts, gift/loyalty/prepaid/promo account types, loyalty and prepaid transactions, rewards and items, member and balance portals, user management, and webhook management. All endpoints require a JWT bearer token. An interactive Swagger UI is published at `api.paystone.com/docs`, and a machine-readable OpenAPI 3.1 export is downloadable from the same host.

- **Human URL:** [https://api.paystone.com/docs](https://api.paystone.com/docs)
- **Base URL:** `https://api.paystone.com`

#### Tags

- Gift Cards
- Loyalty
- Prepaid
- Merchant Management
- Webhooks

#### Properties

- [OpenAPI](openapi/paystone-datacandy-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://api.paystone.com/docs)
- [API Reference](https://api.paystone.com/docs)

## Common Properties

- [Website](https://www.paystone.com/)
- [Developer Portal](https://api.paystone.com/docs)
- [Documentation](https://api.paystone.com/docs)
- [API Reference](https://api.paystone.com/docs)
- [Pricing](https://www.paystone.com/pricing)
- [Blog](https://www.paystone.com/resources)
- [Help Center](https://help.paystone.com/)
- [Status Page](https://status.paystone.com)
- [Login](https://hub.paystone.com/login)
- [Sign Up](https://start.paystone.com/sign-up)
- [Terms of Service](https://www.paystone.com/legal)
- [Privacy Policy](https://www.paystone.com/legal)
- [GitHub Organization](https://github.com/Paystone)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
