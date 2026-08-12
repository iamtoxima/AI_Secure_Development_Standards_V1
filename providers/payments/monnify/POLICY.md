# Monnify Security Policy Baseline

Status: Provider-specific baseline  
Verified against official Monnify documentation: 2026-08-12

## Current Monnify Baseline

At the verification date, Monnify's webhook documentation states:

- webhook requests use the `monnify-signature` header in production;
- the documented production signature mechanism uses HMAC-SHA512 with the client
  secret and request body;
- signature validation must occur before trusting/acting on the event;
- Monnify documents a webhook source IP address for allowlisting;
- the signature header is documented as production behavior and may not be
  present in sandbox.

## Important

- IP allowlisting is defense in depth, not a replacement for signature
  verification in production.
- Sandbox behavior must never be copied blindly into production security logic.
- Payment success must still be correlated with the expected internal
  transaction/order and trusted server state.
- Duplicate events and retry behavior must be handled idempotently.

## Release Gate

Before release verify current official documentation for:

- webhook signature algorithm/header;
- canonical/raw-body handling;
- webhook source IPs;
- sandbox vs production differences;
- transaction verification;
- refunds/disbursements/settlements used by the product.

## Official Source

- https://developers.monnify.com/docs/webhooks

Do not hardcode the provider IP from this stored snapshot without live
verification.
