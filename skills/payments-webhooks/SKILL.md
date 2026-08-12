---
name: payments-webhooks
description: Payments, refunds, subscriptions, escrow, financial entitlements, payment-provider callbacks/webhooks, reconciliation, and money-state integrity. Use only when financial/payment workflows exist.
---


# Payments and Webhooks

## Source of Truth

- A browser/mobile success screen, redirect, screenshot, or client claim never proves payment.
- Verify payment through trusted server-side provider mechanisms.
- Verify webhook authenticity using the provider's documented cryptographic mechanism.
- Where appropriate, re-query the provider before applying high-impact financial state.
- Validate expected order/customer/reference/amount/currency/status.

## Idempotency and Atomicity

- Treat provider events as potentially duplicated.
- Store provider event IDs or equivalent deduplication keys.
- Apply payment state changes idempotently.
- Use transactions/atomic state application when multiple related records must change together.
- Prevent duplicate charges, credits, refunds, entitlements, and escrow releases.

## Refunds and Reversals

- Do not mark a refund complete solely because a client initiated it.
- Verify provider completion.
- Apply related state consistently and atomically where practical.

## Webhook Flooding

- Rate-limit/abuse-protect webhook endpoints without preventing legitimate provider retries.
- Verify signatures before trusting payload data.
- Bound webhook body size before expensive handling where practical.

## Reconciliation

For production financial systems, define:

- transaction reconciliation;
- mismatch handling;
- provider outage behavior;
- ownership of exceptions.

## High-Risk Controls

Keep incomplete refund/escrow/financial functionality inaccessible or feature-flagged until its readiness gates pass.

## Provider-Specific Rules

Universal payment rules are mandatory, but provider implementation details may
change.

When a specific gateway is used:

1. consult its local provider module;
2. verify current official provider documentation before implementation/release;
3. verify webhook signature/header/algorithm and raw-body requirements;
4. verify transaction status/amount/currency/reference semantics;
5. verify retries/timeouts;
6. verify refunds/transfers/subscriptions actually used by the product.

Do not copy provider-specific cryptographic details from stale examples.
