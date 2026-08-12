# Starter Prompt

Use this with an AI coding agent together with the URL of this standards repository.

```text
I want to build or improve a software project.

Before writing application code, read this standards repository:

<PASTE_STANDARDS_REPOSITORY_URL>

This repository is an AI-first engineering and security policy source.

First determine whether my project is new or existing.

Discuss the project with me and ask only the necessary unanswered questions, progressively, so you understand:
- the product and MVP;
- users and roles;
- platforms;
- core flows;
- technical stack or constraints;
- authentication and authorization;
- data and privacy;
- database/storage;
- payments/webhooks;
- uploads;
- chat/messaging;
- notifications;
- third-party providers;
- AI/LLM features;
- deployment/environments;
- reliability, retries, and failure behavior.

Do not start building the application until there is enough context to proceed safely.

Do not force every standard onto the project.
Classify capabilities as Active, Planned, Deferred, Not applicable, or Unknown.
Select only the standards and Skills that actually apply.

Before substantial code changes:
- verify or initialize local Git safely;
- never create a nested Git repository;
- preserve existing uncommitted work;
- create a safe .gitignore;
- use local commits as recovery checkpoints when appropriate.

Create the project-local context and standards described by the repository, including:
- a small AGENTS.md for universal rules;
- docs/PROJECT_PROFILE.md;
- docs/PROJECT_CAPABILITIES.md;
- docs/DOCUMENTATION_INDEX.md;
- docs/PRODUCT_DECISION_LOG.md;
- docs/CHANGE_IMPACT_MAP.md;
- other project documents only when applicable;
- .ai/STANDARDS_MANIFEST.md;
- .ai/SKILL_CATALOG.md;
- .ai/standards-library/ containing the dormant reusable standards;
- .agents/skills/ containing only currently relevant active Skills.

Record the source repository and source revision in the manifest.

After bootstrap, normal development should use the project-local AGENTS.md, docs, active Skills, and dormant local standards library instead of repeatedly rereading the remote repository.

Product decisions are allowed to change later.
When I change a decision or add/remove a feature, update every affected canonical document, decision record, capability status, active Skill, security control, test, and implementation plan in the same task.

If a future capability requires an inactive Skill, activate the local dormant copy instead of asking me to paste this repository URL again.

Do not invent infrastructure merely because a standard mentions it.
Do not weaken mandatory security requirements silently.

Before implementation begins, show me a concise Project Profile, capability classification, selected Skills, deferred/not-applicable Skills, open questions/blockers, and the documents you plan to create/update.
```

### Additional validation behavior

During implementation and testing, do not ignore small reproducible bugs found in the same affected feature merely because I did not mention them.

Fix them automatically when the intended behavior is clear, the change is localized and low risk, then retest and report the extra fix.

Do not silently expand into unrelated cleanup or architecture work.

If you discover a security vulnerability in the code path you are creating, modifying, or validating, fix it when contained; otherwise stop unsafe shipment of that surface and explain the required remediation.

### External policy and compliance

Determine whether this project is affected by:
- payment-provider requirements;
- Google Play or Apple App Store policies;
- privacy/consumer/financial rules in the user's operating markets;
- PCI or other payment-data standards;
- OWASP/NIST security baselines.

Use the local policy modules as baselines, but verify time-sensitive
requirements against current official first-party sources before implementation
or release.

Do not claim legal, regulatory, app-store, PCI, or provider compliance without
real evidence.

If legal/licensing interpretation is materially uncertain, flag it for
qualified human review rather than inventing a conclusion.

### Context routing after bootstrap

Create `.ai/TASK_ROUTER.md` from the repository template.

During normal development, use it together with:
- `docs/DOCUMENTATION_INDEX.md`;
- `docs/PROJECT_CAPABILITIES.md`;
- active `.agents/skills/`.

Do not read all project documents or all Skills for every task.
Load only the context relevant to the affected capability/surface and expand only when necessary.
