---
name: Onboard a DataCandy client and its first merchant
description: Provision a new DataCandy client (gift/loyalty program), add a merchant location under it, and mark onboarding complete.
api: openapi/paystone-datacandy-openapi.yml
operations: [api_v1clients_post, api_v1clients_accessKeymerchants_post, api_v1clients_idcomplete_post]
---

# Onboard a DataCandy client and its first merchant

Use this skill to stand up a new gift/loyalty program on the DataCandy platform.

## Auth
All calls require a JWT bearer token: `Authorization: Bearer <jwt>`. A 401 means the token is missing/invalid; a 403 means the token role is insufficient.

## Steps

1. **Create the client** — `POST /v1/clients` (`api_v1clients_post`).
   - Send `application/ld+json`.
   - Required: `name`, `hostname`, `country`, `timeZone`, `currency`, `languages`, `programs`, `companyInfo`.
   - For loyalty clients also send `accumulationRatioNumerator`, `accumulationRatioDenominator`, `debitRatioNumerator`, `debitRatioDenominator`.
   - For Moneris portfolios also send `configureEgift`, `configureEloyalty`, `configureMemberPortal`, `giftCardsRestrictedWhereActivated`, `enableSboEmailAndSms`.
   - On `201`, capture the client's `accessKey` and numeric `id`. On `422`, read `violations[]` for field-level fixes.

2. **Add a merchant** — `POST /v1/clients/{accessKey}/merchants` (`api_v1clients_accessKeymerchants_post`) using the `accessKey` from step 1. Store an `externalReference` so you can later look the merchant up by it.

3. **Complete onboarding** — `POST /v1/clients/{id}/complete` (`api_v1clients_idcomplete_post`) with the numeric client `id`. This records `completedOn`; the client is then active and can process transactions.

## Conventions & errors
- Pagination is page-number (`page`, `itemsPerPage`, max 30); collections are Hydra (`hydra:member`, `hydra:totalItems`).
- Updates use `PATCH` with `application/merge-patch+json`.
- Errors are RFC 9457 `application/problem+json`; validation errors are `422` with a `violations[]` array. See `errors/paystone-problem-types.yml`.
