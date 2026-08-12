# Flutterwave Security Policy Baseline

Status: Provider-specific baseline  
Verified against official Flutterwave documentation: 2026-08-12

This module supplements the universal payment and resilience rules.

## Current Flutterwave Baseline

At the verification date, Flutterwave's current webhook documentation states:

- configure a secure secret hash;
- webhook authenticity is verified using the `flutterwave-signature` header;
- the current documented mechanism is HMAC-SHA256 over the raw body with the
  secret hash and Base64 output;
- discard webhook requests whose signature validation fails;
- before delivering value, re-query the transaction through trusted backend
  logic;
- verify critical transaction data including:
  - status;
  - amount;
  - currency;
  - `tx_ref`;
- do not rely solely on webhooks; design a recovery/reconciliation strategy for
  pending transactions;
- webhook handlers should respond quickly;
- long-running work should be moved out of the acknowledgement path;
- duplicate webhook delivery can occur, so event processing must be idempotent.

## Compatibility Warning

Older Flutterwave integration material may describe different webhook
authentication mechanisms. Do not implement from old blog posts, old SDK
examples, or stale stored prompts.

Verify the current official documentation for the API/version being integrated.

## Release Gate

Verify current:

- signature header and algorithm;
- raw-body requirements;
- transaction verification endpoint/fields;
- timeout/retry behavior;
- refund/transfer/subscription rules used by the product.

## Official Source

- https://developer.flutterwave.com/docs/webhooks
