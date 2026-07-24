---
name: Subscribe to DataCandy webhooks
description: Register an HTTPS callback to receive DataCandy contact and transaction (loyalty/prepaid) events, scoped to specific merchants and event types.
api: openapi/paystone-datacandy-openapi.yml
operations: [api_webhooks_post, api_webhooks_get_collection, api_webhooks_id_get, api_webhooks_id_patch]
---

# Subscribe to DataCandy webhooks

Use this skill to receive near-real-time events from the DataCandy platform.

## Auth
All calls require a JWT bearer token: `Authorization: Bearer <jwt>`.

## Steps

1. **Register the webhook** — `POST /webhooks` (`api_webhooks_post`) with:
   - `callbackUrl` — your HTTPS endpoint.
   - `secretToken` — optional shared secret; store it and use it to verify inbound calls.
   - `events` — the event types to subscribe to (see catalog below).
   - `merchants` — the merchant(s) to scope delivery to.
   - `active` — `true` to start delivery.

2. **Verify registration** — `GET /webhooks` (`api_webhooks_get_collection`) or `GET /webhooks/{id}` (`api_webhooks_id_get`) to confirm the subscription.

3. **Adjust later** — `PATCH /webhooks/{id}` (`api_webhooks_id_patch`, `application/merge-patch+json`) to change events, merchants, callback URL, or toggle `active`.

## Event catalog
- **Contact:** `contact.created`, `contact.modified`, `contact.unsubscribed`, `contact.anonymized`.
- **Loyalty transactions:** `loyalty.accumulation`, `loyalty.add`, `loyalty.redeem`, `loyalty.subtract`, `loyalty.reward_earned`, `loyalty.reward_redeem`, `loyalty.reward_expired`, `loyalty.balance_import`, `loyalty.complete_cancel`, `loyalty.partial_cancel`, `loyalty.item_cancel`.
- **Prepaid/gift transactions:** `prepaid.activation`, `prepaid.add`, `prepaid.increment`, `prepaid.redeem`, `prepaid.redeem_unlock`, `prepaid.subtract`, `prepaid.card_empty`, `prepaid.balance_import`, `prepaid.complete_cancel`, `prepaid.partial_cancel`, `prepaid.credit_note_activation`, `prepaid.credit_note_increment`.

Full catalog: `asyncapi/paystone-datacandy-webhooks.yml`.
