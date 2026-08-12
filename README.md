# AI Secure Development Standards

Version: 1.0.0

A reusable, AI-first software engineering and security standards repository for people building software with AI coding agents.

It is designed for:

- Mobile apps
- Web apps
- Websites
- APIs and backend services
- Desktop apps
- SaaS products
- Marketplaces
- Fintech/payment products
- AI/LLM-powered products
- Internal tools
- Other software projects

The repository is not a framework, starter application, or mandatory technology stack. It is a policy and workflow library that an AI coding agent uses to understand a project, select the controls that actually apply, install project-local instructions, and keep those instructions current as the product evolves.

## AI AGENT ENTRY PROTOCOL

If you are an AI coding agent reading this repository because a user asked you to use it:

**Do not start building immediately.**

Your first responsibility is to understand the user's project.

Before implementing these standards:

1. Determine whether this is a new project or an existing project.
2. Discuss the project with the user before making architectural or product assumptions.
3. Ask only the questions necessary to resolve important unknowns.
4. Do not repeat questions the user has already answered.
5. Ask questions progressively rather than presenting an overwhelming questionnaire.
6. Build a Project Profile and Project Capabilities record.
7. Determine which standards and Skills apply.
8. Apply mandatory security controls without inventing unnecessary infrastructure.
9. Initialize or verify local Git safety before substantial AI-driven changes.
10. Create or update the relevant project documentation.
11. Install only currently relevant Skills into the coding agent's active skill directory.
12. Keep the remaining standards available locally as a dormant library for future features.
13. After bootstrap, use project-local instructions for normal development instead of repeatedly reading this remote repository.

### Important

A project's first set of decisions is not permanent.

Users may change their minds, remove features, change providers, introduce new roles, or add features after the MVP. The project-local instructions must support this. When a decision changes, update the affected canonical documentation, decision history, active Skills, security controls, tests, and implementation together.

## Recommended User Prompt

A user can start with something as simple as:

> I want to build a mobile app. Before writing code, read this standards repository, discuss the project with me, ask the necessary questions based on the repository, and then prepare the project with the relevant documents and AI instructions.

For an existing product:

> I have an existing application. Read this standards repository, inspect only the parts of my project needed to understand its current architecture and risks, ask me any important unanswered questions, and safely install the relevant project-local standards without rewriting unrelated code.

## How It Works

```text
User explains project
        |
        v
AI reads this repository
        |
        v
New or existing project?
        |
        v
Progressive discovery questions
        |
        v
Project Profile + Capabilities
        |
        v
Git safety / recovery baseline
        |
        v
Create or update canonical project docs
        |
        v
Copy full dormant standards library locally
        |
        v
Activate only relevant Skills
        |
        v
Create small project AGENTS.md
        |
        v
Build in small, testable milestones
        |
        v
User changes decision / adds capability
        |
        v
Impact analysis -> docs -> Skills -> tests -> implementation
```

## Local Project Layout After Bootstrap

A compatible coding agent should create an equivalent project-local structure:

```text
project/
├── AGENTS.md
├── docs/
│   ├── DOCUMENTATION_INDEX.md
│   ├── PROJECT_PROFILE.md
│   ├── PROJECT_CAPABILITIES.md
│   ├── PRODUCT_DECISION_LOG.md
│   ├── ARCHITECTURE_DECISIONS.md
│   ├── CHANGE_IMPACT_MAP.md
│   └── other project-specific canonical documents
├── .ai/
│   ├── STANDARDS_MANIFEST.md
│   ├── SKILL_CATALOG.md
│   └── standards-library/
│       └── dormant copies of reusable standards/Skills
└── .agents/
    └── skills/
        └── only Skills that currently apply
```

The `.ai/standards-library/` directory is dormant reference material. It is not intended to be loaded on every coding task.

The `.agents/skills/` directory contains only active project-relevant Skills.

## Design Principles

- Context before code.
- Security is part of design, not a final patch.
- Small changes beat broad speculative refactors.
- Trust boundaries must be explicit.
- Authentication is not authorization.
- Client input never becomes authority.
- Retryable work must be designed for safe repetition.
- Failure paths need tests, not only happy paths.
- Documentation must describe the product that actually exists.
- Product decisions can change; stale instructions cannot remain.
- Git history is the default recovery mechanism.
- Production evidence is stronger than assumptions.
- Use the minimum infrastructure needed to satisfy real requirements.

## Standards Levels

Rules use three levels:

### MUST
Required for correctness, security, privacy, integrity, or recoverability.

### SHOULD
Strong default. Deviate only for a documented project-specific reason.

### CONSIDER
Evaluate when applicable. Do not add infrastructure merely because a control exists in this repository.

See `core/STANDARDS_LEVELS.md`.

## Start Here

AI agents should read:

1. `BOOTSTRAP.md`
2. Either `workflows/NEW_PROJECT.md` or `workflows/EXISTING_PROJECT.md`
3. `SKILL_CATALOG.md`
4. Relevant core policies
5. Only the Skills selected for the project

Humans can start with the same files, but the repository is intentionally written so an AI coding agent can operate it directly.

## Product Evolution

For a new feature added later, the user should normally **not need to paste this repository URL again**.

The project records the source repository and revision in `.ai/STANDARDS_MANIFEST.md` and keeps a dormant local standards library.

When a user later says, for example:

> Add private chat between buyers and sellers.

the AI should:

1. Detect that chat is new or was previously deferred.
2. Ask only chat-specific unanswered questions.
3. Update `PROJECT_CAPABILITIES.md`.
4. Record the changed decision in `PRODUCT_DECISION_LOG.md`.
5. Consult `CHANGE_IMPACT_MAP.md`.
6. Activate the relevant local Skill.
7. Update affected product, architecture, security, API, data, privacy, notification, failure-mode, and test documentation.
8. Create a Git recovery checkpoint where appropriate.
9. Implement the feature.
10. Run relevant positive and negative tests.

See `workflows/ADD_FEATURE.md` and `workflows/DECISION_CHANGE.md`.

## Scope

These standards improve engineering discipline. They do not guarantee that software is secure, bug-free, compliant, or production-ready. High-risk systems still require real testing, environment verification, monitoring, and appropriate human/security/compliance review.

## Bugs Found While Building

The standards do not require an AI to ignore bugs it discovers during implementation or testing.

A small, clearly correct, low-risk bug in the same affected feature may be fixed immediately and retested.

Unrelated or broad issues should be reported rather than silently expanding the task.

A security vulnerability in the code path being created, modified, or validated must not be knowingly shipped simply because it was not in the original request.

See `core/DISCOVERED_BUG_POLICY.md`.

## External Providers, App Stores, Laws, and Standards

V1 includes dormant policy modules for:

- Paystack
- Flutterwave
- Monnify
- Google Play
- Apple App Store
- Nigeria data protection
- Nigeria consumer protection
- Nigeria payments/fintech applicability
- Nigeria digital lending
- OWASP ASVS
- OWASP API Security
- OWASP MASVS
- NIST SSDF
- PCI DSS

These modules are **not all active on every project**.

The AI resolves applicability from the Project Profile, then verifies
time-sensitive rules against the current official authority.

See:

- `core/EXTERNAL_POLICY_VERIFICATION.md`
- `core/COMPLIANCE_APPLICABILITY.md`
- `compliance/POLICY_REGISTRY.md`

Baseline external-source verification date for V1.0.0: 2026-08-12.

## Context Routing After Bootstrap

After bootstrap, the project should contain `.ai/TASK_ROUTER.md`.

The AI should not reread every Markdown file or Skill for each task.

Instead it should:

1. classify the requested change;
2. use the task router, documentation index, and project capabilities as routing aids;
3. read only relevant canonical docs;
4. use only relevant active Skills;
5. expand context only when a direct dependency, discovered risk, or new capability requires it.

This keeps the project self-guiding without turning every task into a full repository scan.
