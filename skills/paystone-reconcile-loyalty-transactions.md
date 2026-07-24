---
name: Reconcile loyalty and prepaid transactions
description: List and inspect DataCandy loyalty and prepaid transactions with merchant, date, operation, and commit-status filters for reconciliation.
api: openapi/paystone-datacandy-openapi.yml
operations: [api_loyalty-transactions_get_collection, api_loyalty-transactions_id_get, api_prepaid-transactions_get_collection, api_prepaid-transactions_id_get]
---

# Reconcile loyalty and prepaid transactions

Use this skill to pull transaction activity for reconciliation or reporting.

## Auth
All calls require a JWT bearer token: `Authorization: Bearer <jwt>`.

## Steps

1. **List loyalty transactions** — `GET /loyalty-transactions` (`api_loyalty-transactions_get_collection`). Filter with:
   - `merchant` / `merchant[]` — restrict to specific merchants.
   - `creationDate[after]`, `creationDate[before]`, `creationDate[strictly_after]`, `creationDate[strictly_before]` — date window.
   - `operation` — e.g. `accumulation`, `redeem`, `reward_earned` (see spec enum).
   - `commitStatus` — `committed` or `not_committed`.
   - `errorCode` / `errorCode[]` — filter by transaction error code.
   - `page` / `itemsPerPage` (max 30) for pagination.

2. **Inspect a transaction** — `GET /loyalty-transactions/{id}` (`api_loyalty-transactions_id_get`).

3. **Repeat for prepaid/gift** — `GET /prepaid-transactions` (`api_prepaid-transactions_get_collection`) and `GET /prepaid-transactions/{id}` (`api_prepaid-transactions_id_get`) with the same filter set.

## Conventions
- Collections are Hydra: read `hydra:member` and `hydra:totalItems`; page with `hydra:view`.
- Responses are `application/ld+json`.
- See `conventions/paystone-conventions.yml` and `errors/paystone-problem-types.yml`.
