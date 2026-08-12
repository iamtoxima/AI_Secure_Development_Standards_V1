# Failure Modes and Runbook

For each critical dependency/workflow define user experience, detection, and recovery.

| Failure | User impact | App behavior | Detection | Retry/Recovery | Dangerous retry? |
|---|---|---|---|---|---|
| | | | | | |

## Incident Triage

1. Identify affected capability.
2. Capture request/correlation ID if available.
3. Check relevant logs/metrics.
4. Check provider/dependency health.
5. Determine rollback, retry, disable, or manual-review action.
6. Preserve user state/input where practical.

## User-Facing Rules

- No raw stack traces.
- No SQL/provider internals.
- Give actionable retry guidance for transient failures.
- Do not falsely report success.
- Non-critical notification failures should not invalidate completed core actions.

## Retry Policy

- Define retryable errors.
- Define maximum attempts/backoff.
- Define idempotency key/state.
- Define dead-letter/manual review behavior.
