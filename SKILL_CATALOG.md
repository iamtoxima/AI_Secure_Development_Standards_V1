# Skill Catalog

This catalog helps an AI agent decide which Skills to activate.

Do not activate all Skills by default.

| Skill | Activate when | Usually not needed when |
|---|---|---|
| architecture | Adding/changing major subsystem, provider, framework, data boundary, service, or architectural pattern | Localized implementation inside established architecture |
| security | Any project with users, external input, private data, privileged operations, or network-facing behavior | Extremely limited offline prototypes with no meaningful trust boundary |
| database | SQL/NoSQL/database schema, ORM, RLS/policies, migrations, repositories, query work | No persistent database |
| resilience | External dependencies, retries, queues, jobs, distributed workflows, timeouts, money/state transitions | Purely local deterministic UI-only changes |
| performance | Expensive computation, large data, caching, concurrency, large I/O, AI spend, scaling concerns | Lightweight changes without performance implications |
| dependencies | Adding/upgrading/replacing packages or reviewing supply-chain risk | No dependency changes |
| api-security | APIs, server actions, RPC, network request/response contracts, CORS, external response handling | No network/API boundary |
| file-security | Uploads, downloads, filesystem paths, object storage, generated files, private media | No file/storage functionality |
| payments-webhooks | Payments, refunds, subscriptions, escrow, financial entitlements, provider webhooks | No money/payment/event-delivery flow |
| notifications | Email, SMS, push, bulk messaging, delivery jobs, notification preferences | No notification capability |
| chat-security | Direct messaging, group chat, comments with private interaction, moderation-sensitive messaging | No user-to-user messaging |
| ai-security | LLM, RAG, agents, tool calling, AI-accessible data/actions | No AI/LLM capability |
| mobile-security | iOS, Android, Flutter, React Native, Kotlin, Swift mobile applications | Web/backend-only project |
| web-security | Browser-facing web UI, websites, web apps, admin portals | Native-only app with no web surface |
| environment-deployment | Local/staging/production separation, CI/CD, hosting, release configuration | Early non-deployed prototype |
| observability-audit | Production services, security-sensitive actions, incident debugging, operational monitoring | Tiny throwaway prototype |
| feature-lifecycle | Feature flags, staged rollout, deferred/incomplete risky features, kill switches | Very simple feature with no rollout risk |
| release-verification | Staging/production release, app-store build, major security/payment/KYC release | Early implementation work not approaching a release |
| privacy-data-governance | Personal/sensitive data, deletion/export/retention, consent, regulated or high-trust domains | No personal/sensitive data |

| policy-compliance | External provider/app-store/law/regulatory/security-standard applicability or release verification | No external policy dependency |

## Activation Rule

Activate the minimum set that fully covers the work.

If a new feature later requires another Skill:

1. use the local dormant copy from `.ai/standards-library/`;
2. activate it under `.agents/skills/`;
3. update `.ai/STANDARDS_MANIFEST.md`;
4. update `docs/PROJECT_CAPABILITIES.md`;
5. update affected canonical documentation and tests.

Do not reactivate a remote repository merely because the project grows.
