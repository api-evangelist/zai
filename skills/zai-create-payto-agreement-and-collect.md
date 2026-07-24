---
name: Create a PayTo agreement and collect a payment
description: Validate then create a PayTo mandate over the NPP, and initiate a real-time debit against it on Zai's PayTo API.
api: openapi/zai-payto.json
operations: [validateAgreement, createAgreement, initiatePaymentRequest, getInitiatePaymentStatus, getAgreementDetails]
---

# Create a PayTo agreement and collect a payment (Zai PayTo API)

PayTo is the NPP's digital alternative to direct debit. Base URL:
`https://au-0000.api.assemblypay.com/payto/` (live) /
`https://sandbox.au-0000.api.assemblypay.com/payto/`. Auth is a bearer JWT.

## Steps
1. Validate the agreement first — `validateAgreement`. This resolves the
   debtor's PayID and confirms NPP/PayTo reachability, returning an agreement
   `uuid`. Share the resolved PayID details with the payer for confirmation.
2. Create the agreement within 5 minutes of a successful validation —
   `createAgreement`. AUPM agreements become ACTIVE only after debtor
   authorisation (default 5-day window); MGCR (migrated) agreements are ACTIVE
   immediately but cannot be debited until 5 calendar days pass.
3. Initiate a payment against an ACTIVE agreement — `initiatePaymentRequest`.
   Status progresses PENDING_PAYMENT_INITIATION → PAYMENT_INITIATED →
   PAYMENT_INITIATION_COMPLETED (or _REJECTED).
4. Poll status — `getInitiatePaymentStatus` (single request) — on rejection for a
   valid business reason (e.g. insufficient funds) retry up to 5 times within 24h;
   the `payment_request_uuid` stays constant across retries, `instruction_id`
   changes.
5. Inspect the agreement any time — `getAgreementDetails` by `uuid`.

## Conventions & errors
- Errors return `{"errors":[{"error_code":"PAYT-ERR-XXXX","error_message":"..."}]}`.
  The full coded registry is errors/zai-error-codes.yml (e.g. PAYT-ERR-2513 =
  exceeded max retry attempts, PAYT-ERR-2518 = migrated-agreement > $5,000 AUD).
- Initiate the last scheduled payment a few days before `validity_end_date` so
  retries stay within the agreement window.
- Subscribe to `payto_agreements` / `payto_payments` webhooks
  (asyncapi/zai-webhooks.yml) instead of tight polling.
