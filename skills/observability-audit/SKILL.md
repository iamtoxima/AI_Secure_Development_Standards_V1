---
name: observability-audit
description: Structured logging, request/correlation IDs, redaction, audit trails, sanitized client error reporting, monitoring, and incident-debugging controls.
---


# Logging, Observability, and Audit

## Structured Logs

Use the project's centralized logger.

Prefer fields such as:

- timestamp
- level
- request/trace ID
- user/actor ID when appropriate
- message
- structured metadata

Do not scatter production `console.log`/`print` statements.

## Request IDs

Where network APIs exist:

- generate or accept a validated request ID;
- return/propagate it;
- include it in related logs/audit events.

## Redaction

Never log:

- passwords
- OTPs
- session/access/refresh tokens
- authorization headers
- private keys
- service credentials
- full card data
- sensitive private documents
- unnecessary raw provider payloads

Centralized sanitization should handle nested structures.

Bound logged object depth, array length, and string length to prevent leaks and log/resource abuse.

Prefer stable IDs and normalized error codes over raw payload dumps.

## Audit vs Debug Logging

Audit logs answer who did what and when.

Consider auditing:

- admin authentication
- role/permission changes
- payment/refund/escrow state
- sensitive file access
- KYC/identity decisions
- destructive actions
- security settings
- high-impact feature flags
- dispute resolution

Audit records should be append-resistant/append-only where the architecture supports it.

## Client Error Reporting

If clients report runtime errors:

- sanitize before sending/storing;
- do not include raw secrets/private records;
- make reporting failure non-blocking to the user;
- deduplicate/fingerprint noisy recurring events where useful.
