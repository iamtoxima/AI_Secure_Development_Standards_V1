# Change Impact Map

Use this file when the user changes a decision or requests a new capability.

| Change | Check / Update |
|---|---|
| Product feature added/removed | PRD, PROJECT_CAPABILITIES, APP_FLOW, IMPLEMENTATION_PLAN, TEST_PLAN |
| User role added/changed | PRD, APP_FLOW, DATA_MODEL, API_CONTRACT, SECURITY_REQUIREMENTS, authorization tests |
| Auth change | APP_FLOW, API_CONTRACT, SECURITY_REQUIREMENTS, SECRETS_AND_ENVIRONMENT, TEST_PLAN |
| Database/schema change | DATA_MODEL, migrations, API_CONTRACT, security/policies, tests |
| API behavior change | API_CONTRACT, clients, ERROR/UX behavior if documented, security, tests |
| New provider | TRD, ARCHITECTURE_DECISIONS, SECRETS_AND_ENVIRONMENT, FAILURE_MODES, privacy/data flows |
| File uploads added | file-security Skill, DATA_MODEL, API_CONTRACT, storage policy, FAILURE_MODES, TEST_PLAN |
| Payments added | payments-webhooks + resilience Skills, DATA_MODEL, API_CONTRACT, SECURITY_REQUIREMENTS, FAILURE_MODES, logging/audit, tests |
| Chat added | chat-security Skill, DATA_MODEL, API_CONTRACT, APP_FLOW, privacy/moderation, notifications, rate limits, tests |
| Notifications added | notifications Skill, TRD, SECRETS_AND_ENVIRONMENT, FAILURE_MODES, background jobs, privacy, tests |
| AI/LLM added | ai-security Skill, TRD, SECURITY_REQUIREMENTS, data/tool permissions, threat model if used, tests |
| Mobile platform added | mobile-security Skill, TRD, release/testing, secrets/public config |
| Web surface added | web-security Skill, TRD, headers/session/CSP/CSRF/CORS as applicable |
| Sensitive data added | privacy-data-governance Skill, SECURITY_REQUIREMENTS, data model, retention/deletion, logging, storage |
| Deployment/environment change | TRD, SECRETS_AND_ENVIRONMENT, environment-deployment Skill, rollback, release checklist |
| Retry/queue/job added | resilience Skill, FAILURE_MODES, observability, idempotency tests |
| Admin capability added | SECURITY_REQUIREMENTS, authorization, audit logging, confirmation, release checks |
| Major dependency added | dependencies Skill, TRD if architectural, lockfile/audit |
| Security control changed | SECURITY_REQUIREMENTS, TEST_PLAN, LAUNCH_READINESS evidence |

| Payment gateway/provider added/changed | payments-webhooks, provider policy module, secrets/environment, API, failure modes, current provider verification, reconciliation tests |
| Google Play distribution added | mobile-security, Google Play policy module, privacy/data safety, account deletion, billing classification, permission review, release checklist |
| Apple App Store distribution added | mobile-security, Apple policy module, privacy details, account deletion, IAP/payment classification, review/release checklist |
| New country/market added | privacy/data governance, jurisdiction policy module, terms/privacy/consumer review, current legal verification |
| Lending/credit added in Nigeria | Nigeria digital-lending module, privacy, consumer protection, payment/fintech applicability, qualified compliance review |

## Rule

This table is a routing aid, not a mandate to update every listed file blindly. Update only the documents actually affected.
