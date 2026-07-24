---
name: Issue a Virtual Account and register a PayID
description: Create an NPP Virtual Account for a wallet and register a PayID so a platform can receive real-time account-to-account pay-ins on Zai.
api: openapi/zai-virtual-accounts-payid.json
operations: [createVirtualAccount, registerPayID, getPayID, showVirtualAccount, updatePayIdStatus]
---

# Issue a Virtual Account and register a PayID (Zai Virtual Accounts & PayIDs API)

Give each wallet a uniquely addressable NPP account so inbound real-time
payments auto-reconcile. Base URL: `https://au-0000.api.assemblypay.com`
(live) / `https://sandbox.au-0000.api.assemblypay.com`.

## Steps
1. Create a Virtual Account for a wallet — `createVirtualAccount` with the
   `wallet_account` id. Returns the BSB/account-number pair for that virtual
   account.
2. (Optional) Register a PayID against the virtual account — `registerPayID`
   (email / phone / ABN alias).
3. Confirm activation — `getPayID` / `showVirtualAccount`. PayIDs go through a
   status activation the caller should confirm before advertising them.
4. Manage lifecycle — `updatePayIdStatus` (activate/disable) and the virtual
   account status update as needed.

## Conventions & errors
- Inbound funds arriving at the virtual account/PayID surface as `transactions`
  on the owning wallet; subscribe to `virtual_accounts` / `pay_ids` webhooks
  (asyncapi/zai-webhooks.yml).
- Errors follow the Assembly custom envelope; 404 = unknown resource, 409 =
  conflicting status change (errors/zai-problem-types.yml).
- This API surface has no OAuth scopes; authorise with the platform bearer token
  (authentication/zai-authentication.yml).
