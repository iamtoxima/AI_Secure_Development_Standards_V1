---
name: performance
description: Performance, bounded resource usage, caching, concurrency, large I/O, expensive computation, scaling, and cost controls. Use when a task affects resource-heavy or repeatable operations.
---


# Performance and Resource Bounds

## Bounds

For user-controlled or expensive operations:

- cap request/body size;
- cap uploads;
- cap pagination;
- cap query complexity where relevant;
- bound generated output;
- use timeouts;
- limit concurrency when necessary;
- apply quotas/budgets to expensive third-party or AI operations;
- reject excessive work early.

Do not rely solely on `Content-Length` when the server can enforce a streaming/read limit.

Bound upstream/provider response reads when practical.

Stream large files rather than buffering whole files in memory.

## Caching

Only add caching when a concrete repeated/expensive operation justifies it.

For each cache define:

- what is cached;
- key/scope;
- TTL or expiration;
- invalidation trigger;
- privacy/user-specific behavior.

Do not publicly cache secrets, tokens, highly sensitive private records, or privileged responses.

Use existing cache infrastructure before introducing a new platform.

## Optimization

Measure or identify the actual bottleneck before broad optimization.

Do not perform unrelated performance refactors.
