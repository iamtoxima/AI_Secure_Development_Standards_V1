---
name: resilience
description: Failure handling, retries, idempotency, queues, jobs, timeouts, distributed workflows, provider outages, and recovery. Use when work can fail, retry, redeliver, or partially complete.
---


# Resilience and Idempotency

## Idempotency

For operations that may be retried, redelivered, or submitted more than once:

- repeating the same logical operation must not unintentionally repeat irreversible state or side effects;
- use stable operation/event IDs or idempotency keys where appropriate;
- persist processed external event IDs when duplicate delivery is possible;
- use unique constraints and transactions where they strengthen correctness;
- check current trusted state before irreversible transitions.

Apply especially to:

- payments/refunds
- webhooks
- order/account provisioning
- entitlements
- queues/background jobs
- notifications where duplicate delivery matters
- scheduled jobs
- file cleanup/processing
- external API mutations

## Retry Safety

- Distinguish retryable from non-retryable failures.
- Use bounded retries with backoff where appropriate.
- Never retry indefinitely.
- Do not blindly retry irreversible operations.
- Preserve enough durable state to know whether work already succeeded.
- Define dead-letter/manual-review behavior where jobs can permanently fail.

## Failure Modes

For important external dependencies, define:

- user impact
- application behavior
- detection
- retry/recovery
- rollback/disable strategy

Non-critical provider failure should not block unrelated successful user actions.

## Partial Failure

Test workflows that update multiple systems for partial failure and recovery.

Prefer atomic database state changes where multiple related records must move together.
