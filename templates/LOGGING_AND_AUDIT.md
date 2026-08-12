# Logging and Audit

## Operational Logs

Central logger:

Structured fields:

- timestamp
- level
- requestId/traceId
- actor/user ID when appropriate
- message
- metadata

## Redaction

Never log:

- passwords
- OTPs
- tokens
- authorization headers
- private keys/secrets
- full payment credentials
- unnecessary sensitive documents
- raw sensitive provider payloads

Define centralized recursive redaction and output bounds.

## Audit Events

| Event | Actor | Target | Metadata | Retention |
|---|---|---|---|---|
| | | | | |

Consider audit events for:

- admin login
- role changes
- financial state changes
- sensitive file access
- KYC/identity decisions
- destructive actions
- security configuration
- high-impact feature flags

## Request IDs

- generation:
- validation:
- propagation:
- user-visible behavior:

## Monitoring / Alerts

-
