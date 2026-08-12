# Test Plan

## Core Functional

- success path
- empty state
- validation failure
- network/provider failure

## Authentication / Authorization

When applicable:

- unauthenticated
- wrong role
- cross-user/object access
- revoked/expired session
- invalid state transition

## Abuse / Bounds

When applicable:

- oversized request
- pagination cap
- rate limit
- timeout
- duplicate/replayed event

## Payments / Webhooks

When applicable:

- valid signature
- invalid signature
- duplicate event
- provider mismatch
- amount/currency/reference mismatch
- failed payment
- refund
- idempotency
- partial failure

## Uploads

When applicable:

- size
- type
- MIME spoof
- magic bytes/signature
- traversal/object-key safety
- authorization
- abandoned cleanup
- scan failure/timeout
- large streaming

## Jobs / Queues

When applicable:

- retry
- duplicate delivery
- partial failure
- dead-letter/manual recovery
- idempotency

## Release

- dependency/security audits
- smoke tests
- rollback/restore
- mobile/web release-specific checks
