# Launch Readiness

A box may be checked only when evidence exists.

Reopen an item if related code, configuration, schema, provider, environment, or infrastructure changes.

## Scope

- [ ] Launch scope is approved.
- [ ] Deferred risky features are inaccessible/disabled.
- [ ] Release candidate is tied to a Git commit/build/deployment version.

## Environments

- [ ] Production/staging separation is appropriate.
- [ ] Production has no development CORS/debug overrides.
- [ ] Production credentials and endpoints are correct.
- [ ] Rollback is documented.

## Secrets

- [ ] No private secrets in client code, Git history, docs, or public artifacts.
- [ ] Required production secrets exist in correct environment.
- [ ] Former/test credentials are revoked when appropriate.

## Security

- [ ] Authentication/authorization negative tests pass.
- [ ] Dependency/security scans have no unaccepted launch-blocking findings.
- [ ] Sensitive logging/redaction is verified.
- [ ] Abuse/rate limits are verified where required.

## Data

- [ ] Backups exist where required.
- [ ] Restore procedure is verified for critical data.
- [ ] Retention/deletion behavior is documented.

## Payments / Webhooks

If applicable:

- [ ] Signatures verified.
- [ ] Provider events deduplicated.
- [ ] Financial state changes are idempotent.
- [ ] Reconciliation/runbook tested.
- [ ] Refund/escrow paths verified before activation.

## Files

If applicable:

- [ ] Sensitive buckets/storage are private.
- [ ] Upload authorization/type/size/content validation verified.
- [ ] High-risk scanning/quarantine behavior verified.
- [ ] Private downloads recheck authorization.

## Jobs / Notifications

If applicable:

- [ ] Queue retries/deduplication/failure handling tested.
- [ ] Scheduled jobs are idempotent.
- [ ] Sensitive data is absent from notifications.

## Mobile / Web

Use the relevant platform Skill and record release evidence.

## Operations

- [ ] Monitoring/alerts exist for critical paths.
- [ ] Provider health is checked.
- [ ] Smoke tests pass.
- [ ] Incident/rollback ownership is clear.

## Approval / Blockers

Open launch blockers:

- 

Evidence references:

-

## External Policy Verification

- [ ] Applicable app-store rules were reverified against current official policy.
- [ ] Applicable payment-provider security requirements were reverified.
- [ ] Applicable jurisdiction/privacy/consumer/financial requirements were reviewed.
- [ ] Required legal/compliance questions have human sign-off where necessary.
- [ ] App-store privacy/data disclosures match actual current behavior.
- [ ] Payment method is permitted for the product type/distribution channel.
- [ ] No external-policy item is marked Verified solely from a stored repository snapshot.
