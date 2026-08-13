# Task Context Router

Purpose: help AI coding agents load the smallest relevant context for a task.

Use this router after bootstrap. Do not treat it as permission to ignore direct dependencies or newly discovered risks.

| Task / Change | Primary Docs | Primary Skills / Policies | Extra Checks |
|---|---|---|---|
| UI/UX visual change | PRD, APP_FLOW, design docs | platform Skill if needed | accessibility/responsive checks |
| New screen/page | PRD, APP_FLOW, relevant feature spec | web-security or mobile-security as applicable | auth/state/error/loading behavior |
| Authentication | APP_FLOW, API_CONTRACT, SECURITY_REQUIREMENTS | security, api-security, mobile/web security | negative auth tests |
| Authorization/roles | SECURITY_REQUIREMENTS, API_CONTRACT, DATA_MODEL | security, api-security, database | wrong-role/cross-user tests |
| Database query/schema | DATA_MODEL, API_CONTRACT if exposed | database | migration/policy/index checks |
| API endpoint/contract | API_CONTRACT, error/UX docs if present | api-security, security | request/response validation, auth |
| Payments | PRD, API_CONTRACT, FAILURE_MODES, SECURITY_REQUIREMENTS | payments-webhooks, resilience, security, policy-compliance | provider live verification, idempotency, reconciliation |
| Payment provider change | TRD, ARCHITECTURE_DECISIONS, SECRETS_AND_ENVIRONMENT, FAILURE_MODES | payments-webhooks, resilience, policy-compliance, provider policy | live provider docs, sandbox/prod split |
| Uploads/files | DATA_MODEL, API_CONTRACT, storage docs | file-security, security | MIME/content, size, auth, cleanup |
| Chat/messaging | PRD, APP_FLOW, DATA_MODEL, API_CONTRACT | chat-security, security, notifications as applicable | moderation, privacy, retention, abuse |
| Notifications | TRD, FAILURE_MODES, SECRETS_AND_ENVIRONMENT | notifications, resilience | retries, idempotency, privacy |
| Background job/queue/cron | FAILURE_MODES, implementation plan | resilience, observability-audit | duplicate delivery, retry, partial failure |
| Logging/audit | LOGGING_AND_AUDIT | observability-audit, security | redaction, request IDs, sensitive data |
| Caching/performance | TRD, relevant feature/API docs | performance | TTL, invalidation, privacy, bounds |
| Dependency change | TRD if architectural | dependencies | audit, lockfile, maintenance status |
| AI/LLM feature | PRD, TRD, SECURITY_REQUIREMENTS, DATA_MODEL/API as relevant | ai-security, security, policy-compliance if external rules apply | tool auth, prompt injection, data minimization |
| Mobile release | TRD, LAUNCH_READINESS, SECRETS_AND_ENVIRONMENT | mobile-security, environment-deployment, release-verification, policy-compliance | Google Play / Apple live policy verification |
| Web release | TRD, LAUNCH_READINESS, SECRETS_AND_ENVIRONMENT | web-security, environment-deployment, release-verification | headers, TLS, production config |
| Google Play submission | PROJECT_PROFILE, PROJECT_CAPABILITIES, privacy/release docs | policy-compliance, mobile-security, release-verification | Data Safety, billing classification, account deletion, permissions |
| Apple App Store submission | PROJECT_PROFILE, PROJECT_CAPABILITIES, privacy/release docs | policy-compliance, mobile-security, release-verification | privacy details, IAP classification, account deletion |
| Nigeria privacy/data change | SECURITY_REQUIREMENTS, privacy/data docs | privacy-data-governance, policy-compliance | NDPC current requirements |
| Nigeria fintech/payment activity | PRD, TRD, payment flow | policy-compliance, payments-webhooks, security | CBN applicability + qualified review when uncertain |
| New feature/capability | PROJECT_CAPABILITIES, PRODUCT_DECISION_LOG, CHANGE_IMPACT_MAP | run `workflows/ADD_FEATURE.md` first | activate relevant dormant Skills |
| Small feature deferral or presentation-only capability change | PROJECT_CAPABILITIES, PRODUCT_DECISION_LOG | feature-lifecycle; run `workflows/DECISION_CHANGE.md` if a prior decision changed | load or update other docs only when their canonical truth changed |
| Changed product decision | PRODUCT_DECISION_LOG, PROJECT_CAPABILITIES, CHANGE_IMPACT_MAP | run `workflows/DECISION_CHANGE.md` first | update affected docs/Skills/tests |
| Bug found during testing | current affected docs only | current task Skills + discovered bug policy | fix related low-risk issue, retest |
| Release preparation | LAUNCH_READINESS, FAILURE_MODES, SECURITY_REQUIREMENTS, relevant product docs | release-verification + applicable Skills/policies | evidence-based gates |

## Routing Rules

- Start with the smallest relevant context.
- Do not read every document because a task is important.
- Do not activate unrelated Skills.
- Expand only when a direct dependency, failure, or security boundary requires it.
- When project-specific docs conflict with generic examples, use the project's current canonical decision unless doing so would weaken a mandatory security requirement.
- When a new capability appears, update routing context by updating:
  - `PROJECT_CAPABILITIES.md`;
  - `DOCUMENTATION_INDEX.md` if docs changed;
  - `.ai/STANDARDS_MANIFEST.md`;
  - active Skills.

## Fast Routing Examples

### "Make the profile page responsive"

Load:
- relevant UI/design context;
- profile flow if behavior is affected;
- mobile/web Skill only if needed.

Do not load:
- payment provider rules;
- PCI;
- Nigeria fintech;
- chat security;
- AI security.

### "Add Paystack subscription billing"

Load:
- PRD/payment requirements;
- API contract;
- failure modes;
- security requirements;
- payments-webhooks;
- resilience;
- policy-compliance;
- Paystack provider policy.

Also:
- classify app-store billing rules if the app is distributed through Google Play or Apple.

### "Add chat after MVP"

Run:
- `workflows/ADD_FEATURE.md`.

Then:
- ask only chat-specific missing questions;
- activate chat-security;
- update affected docs;
- implement and test.
