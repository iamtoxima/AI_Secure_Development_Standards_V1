---
name: release-verification
description: Evidence-based staging/production/app-store release readiness, security verification, scans, smoke tests, backups, rollback, and go/no-go gates. Use near a real release or major high-risk change.
---


# Release Verification

## Evidence

Do not mark a release/security item complete without evidence.

Evidence may include:

- test result
- migration ID
- deployment/version ID
- Git commit
- signed build
- provider configuration verification
- security scan
- backup/restore result
- named approval

Reopen evidence when related code, configuration, schema, provider, or infrastructure changes.

## Security and Supply Chain

Select applicable checks, such as:

- dependency audit/SCA
- secret scanning including Git history/release artifacts
- static/code security scanning
- staging dynamic web/API testing
- mobile binary analysis
- role/object authorization testing
- upload abuse testing
- webhook replay testing
- race-condition/state-transition testing
- independent penetration test for high-risk products

## Operational Readiness

Verify when relevant:

- monitoring
- alerts
- provider health
- backups
- restore
- rollback
- queue/dead-letter behavior
- cron/job health
- reconciliation
- incident ownership

## Launch

Deadlines do not override unresolved launch-blocking security, payment, privacy, data-integrity, or rollback controls.

Deferred risky features should remain disabled/inaccessible.
