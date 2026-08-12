# Paystack Security Policy Baseline

Status: Provider-specific baseline  
Verified against official Paystack documentation: 2026-08-12

This file supplements the universal `payments-webhooks` Skill. It does not
replace current Paystack documentation.

## Universal Requirements Still Apply

Always enforce:

- server-side trusted payment state;
- exact reference/order/customer/amount/currency/status matching;
- idempotent fulfillment;
- duplicate-event handling;
- atomic money-state transitions where appropriate;
- reconciliation;
- server-side secrets;
- bounded webhook handling;
- auditability of high-impact state.

## Current Paystack Baseline

At the verification date:

- initialize transactions from trusted backend logic where the architecture
  permits, rather than allowing the client to control privileged transaction
  details;
- a callback/redirect being visited does not prove payment;
- verify transaction state before delivering value;
- verify the transaction amount against the expected amount;
- take special care to prevent duplicate fulfillment;
- webhook requests include `x-paystack-signature`;
- the documented webhook signature mechanism is HMAC-SHA512 using the secret
  key;
- acknowledge valid webhook delivery promptly with HTTP 200;
- long-running follow-up work should not delay acknowledgement;
- failed live webhook delivery may be retried by Paystack, so processing must be
  idempotent;
- Paystack currently documents webhook source IPs as an additional origin
  control; treat IP allowlisting as defense in depth, not a substitute for
  cryptographic verification.

## Implementation Gate

Before implementing or releasing Paystack integration:

1. verify the current Paystack webhook signature algorithm/header;
2. verify current documented webhook retry/timeout behavior;
3. verify current webhook source IPs if using allowlisting;
4. verify transaction verification fields/status semantics;
5. verify refund/transfer/subscription rules for the exact product feature;
6. record the verification date.

## Official Sources

- https://paystack.com/docs/payments/webhooks/
- https://paystack.com/docs/payments/verify-payments/
- https://paystack.com/docs/payments/accept-payments/
- https://paystack.com/docs/api/transaction/

Do not hardcode provider IPs or provider behavior from this snapshot without
checking the current official documentation first.
