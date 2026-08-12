# Release Preparation Workflow

Use before staging, production, app-store distribution, or a major security-sensitive release.

## Principle

Release readiness is evidence-based.

Do not mark a control complete because code appears correct.

## Review

Select only checks relevant to the product:

- release scope
- environment separation
- secrets
- auth/authorization
- database permissions
- APIs
- payments/webhooks
- uploads/storage
- messaging/chat
- background jobs
- notifications
- mobile hardening
- web hardening
- privacy/data lifecycle
- monitoring/audit
- dependency/supply chain
- backups/restore
- rollback
- smoke tests

## Evidence

Evidence may include:

- passing automated test
- manual verification result
- security scan
- migration ID
- deployment/version ID
- Git commit
- signed mobile build
- configuration screenshot/reference
- provider verification
- backup restore drill
- named human approval

If a later change affects a verified area, reopen that readiness item.

## High-Risk Releases

For high-risk auth, payment, KYC, admin, private-file, or AI-tooling changes, consider independent security review or penetration testing appropriate to the product.

Do not claim a launch is safe solely because an AI reviewed it.
