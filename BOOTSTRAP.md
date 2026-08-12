# Bootstrap Protocol

This is the primary entry workflow for an AI agent applying this repository to a software project.

## Rule Zero

Do not implement application features until sufficient project context exists.

The purpose of bootstrap is to turn an ambiguous product idea or an undocumented existing project into a safe working context for AI-assisted development.

## Phase 1: Determine Project Mode

Choose exactly one:

- **New project:** meaningful application code does not yet exist.
- **Existing project:** application code, infrastructure, schema, or production behavior already exists.

Then follow the matching workflow in `workflows/`.

## Phase 2: Progressive Discovery

Ask questions in small rounds. Skip questions already answered.

### Round A: Product

Establish:

- What problem is being solved?
- Who uses the product?
- What is the MVP?
- What is explicitly out of scope?
- What does success look like?

### Round B: Users and Flows

Establish when relevant:

- User roles
- Authentication requirements
- Authorization boundaries
- Core user journeys
- Admin/operations roles
- Sensitive actions
- Payments
- Uploads
- Messaging/chat
- Notifications
- Location
- AI/LLM features

### Round C: Technical Direction

Establish or inspect:

- Platform: web, mobile, desktop, API/backend, hybrid
- Frontend technology
- Backend technology
- Database
- Authentication provider
- Storage
- External APIs/providers
- Deployment environments
- Existing architecture constraints

Do not force a technology decision when the user has not chosen one. Present a small number of justified options when a choice is genuinely required.

### Round D: Security and Data

Establish:

- Sensitive/private data types
- User ownership model
- Roles/permissions
- Financial or irreversible actions
- Regulatory/privacy considerations known to the user
- Retention/deletion expectations
- Administrative capabilities
- Abuse-sensitive endpoints
- High-risk integrations

### Round E: Reliability and Operations

Establish:

- Expected scale if relevant
- What operations may be retried
- External provider failures
- Offline/network expectations
- Background jobs
- Monitoring expectations
- Rollback expectations
- Release/deployment approach

## Phase 3: Build the Project Context

Create or update:

- `docs/PROJECT_PROFILE.md`
- `docs/PROJECT_CAPABILITIES.md`
- `docs/DOCUMENTATION_INDEX.md`
- `docs/PRODUCT_DECISION_LOG.md`
- `docs/CHANGE_IMPACT_MAP.md`

Create other templates only if applicable.

For a substantial new product, usually consider:

- PRD
- TRD / technical architecture
- UI/UX specification or design reference
- app/user flow
- data model
- implementation plan

Security-sensitive products may additionally need:

- security requirements
- API contract
- secrets/environment policy
- failure-mode runbook
- logging/audit specification
- test plan
- launch readiness checklist

Do not create irrelevant documents merely to satisfy a checklist.

## Phase 4: Git Safety

Follow `core/VERSION_CONTROL.md`.

For a new project with no Git repository:

- initialize Git;
- create a suitable `.gitignore`;
- verify secrets and generated artifacts are excluded;
- create an initial local commit after the safe scaffold/context is ready.

For an existing project:

- inspect Git state first;
- never discard or overwrite uncommitted user work;
- do not create nested repositories;
- create a baseline checkpoint before substantial AI-driven modifications when safe.

## Phase 5: Select Standards

Read `SKILL_CATALOG.md`.

Classify capabilities as:

- Active
- Planned
- Deferred
- Not applicable
- Unknown

Activate only Skills needed for active functionality or immediate implementation work.

Do not activate Skills merely because a future idea is mentioned.

## Phase 6: Install Local Standards

Create:

```text
.ai/STANDARDS_MANIFEST.md
.ai/SKILL_CATALOG.md
.ai/standards-library/
.agents/skills/
```

### Dormant library

Copy the reusable standards/Skill library into `.ai/standards-library/`.

This directory is a future reference source and is not a coding-agent auto-load directory.

### Active Skills

Copy only currently applicable Skill folders into `.agents/skills/`.

### Manifest

Record:

- source repository
- source revision or commit when available
- installation date
- project mode
- active Skills
- inactive/deferred Skills
- local standards-library path

## Phase 7: Create Project AGENTS.md

Use `adapters/codex/AGENTS.template.md` as a basis when Codex is used.

Keep project `AGENTS.md` small.

Do not copy every specialized security rule into it.

Its purpose is to enforce:

- scoped investigation;
- minimal changes;
- reuse;
- Git safety;
- documentation synchronization;
- decision-change handling;
- relevant testing;
- Skill activation;
- concise completion reporting.

## Phase 8: Confirm Before Build

Before beginning implementation, summarize:

- project type
- stack
- roles
- active capabilities
- sensitive capabilities
- selected Skills
- deferred/not-applicable Skills
- unresolved blockers
- documents created/updated
- Git status

Do not repeat all repository instructions.

## Phase 9: Build in Milestones

Use `IMPLEMENTATION_PLAN.md`.

Prefer small milestones that can be:

1. implemented;
2. tested;
3. reviewed;
4. documented;
5. committed locally.

Do not treat one giant prompt as an implementation plan.

## Phase 10: Stop Depending on the Remote Repo

After bootstrap:

- use `AGENTS.md`;
- use active `.agents/skills/`;
- use `docs/`;
- use `.ai/standards-library/` for future feature activation.

Do not reread the remote standards repository during ordinary work.

Fetch/re-read the source standards repository only when:

- the user requests a standards update;
- a required standard is missing locally;
- the project manifest is damaged or incomplete;
- the project intentionally wants to sync with a newer standards release.

## Discovered Bug Behavior

Project-local instructions must preserve proactive validation behavior:

- allow small, related, clearly correct bug fixes discovered during implementation/testing;
- require retesting after those fixes;
- prevent unrelated scope creep;
- require security regressions in the affected surface to be fixed or explicitly blocked/escalated.

Use `core/DISCOVERED_BUG_POLICY.md` when generating the project-local `AGENTS.md`.

## Phase 5A: Resolve External Policy

After project capabilities are known, determine whether any external policy
modules apply.

Check:

- payment provider(s);
- Google Play / Apple App Store distribution;
- countries/jurisdictions;
- regulated business activity;
- personal/sensitive data;
- PCI/card-data scope;
- relevant OWASP/NIST baselines.

Use `compliance/POLICY_REGISTRY.md`.

Activate `policy-compliance` when a time-sensitive external rule materially
affects implementation or release.

Do not mark current compliance Verified from the stored snapshot alone.

## Phase 6A: Install Task Router

Create `.ai/TASK_ROUTER.md` from `templates/TASK_ROUTER.md`.

The router is a lightweight context-selection aid used after bootstrap.

Its purpose is to prevent two failure modes:

- reading too little and missing an applicable control;
- reading every document/Skill and wasting context/credits.

Project-specific routing may be added as the application grows.
