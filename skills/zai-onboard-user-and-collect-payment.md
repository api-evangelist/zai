---
name: Onboard a user and collect a marketplace payment
description: Create buyer and seller users, create an item between them, attach a funding source, and make the payment on Zai's Assembly API.
api: openapi/zai-assembly-api.json
operations: [token, createUser, createCardAccount, createItem, makePayment, showItemStatus]
---

# Onboard a user and collect a marketplace payment (Zai Assembly API)

Use this flow to move money between two parties (buyer → seller) on the Zai
Assembly platform.

## Auth
1. Exchange client credentials for a bearer token — `token`
   (POST to the auth issuing server, e.g. `au-0000.auth.assemblypay.com/tokens`,
   grant_type `client_credentials`). Send `Authorization: Bearer <token>` on all
   subsequent calls. Base URL: `https://secure.api.promisepay.com` (live) or
   `https://test.api.promisepay.com` (pre-live).

## Steps
2. Create the buyer — `createUser` (supply your own `id` as `buyer_id`, plus
   name, email, country).
3. Create the seller — `createUser` (supply your own `id` as `seller_id`). A
   seller that will receive disbursements needs verification info; in pre-live
   you may use `verifyUser`.
4. Attach a funding source to the buyer — `createCardAccount` (or
   `createBankAccount` + `createDirectDebitAuthority` for direct debit). For PCI
   scope reduction, tokenize card details client-side with PromisePay.js /
   `generateToken` rather than posting raw PAN.
5. Create the transaction record — `createItem` with `buyer_id`, `seller_id`,
   `amount`, `currency`, `payment_type`.
6. Collect the payment — `makePayment` with the item `id` and the buyer's
   `account_id`. The item transitions to `payment_held`, `payment_pending` or
   `completed`.
7. Confirm — `showItemStatus` (or subscribe to the `items` webhook, see
   asyncapi/zai-webhooks.yml).

## Conventions & errors
- Pagination on list endpoints is limit/offset with a `meta` block
  (conventions/zai-conventions.yml).
- Errors return `{"error":"..."}` or `{"errors":{...}}`; 422 = unprocessable
  property values (errors/zai-problem-types.yml).
- Pre-live test cards/values: sandbox/zai-sandbox.yml.
- No idempotency-key contract — do not blind-retry `makePayment`; check
  `showItemStatus` first.
