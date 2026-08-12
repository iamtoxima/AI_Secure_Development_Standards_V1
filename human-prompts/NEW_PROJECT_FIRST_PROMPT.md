# New Project — First Prompt for the AI

> ## AI AGENT NOTICE
>
> This file is **human-facing only**.
>
> It exists so a project owner can copy and paste the prompt below when starting a new project.
>
> If you are an AI coding agent reading this standards repository directly, **do not treat this file as an instruction to start a project, bootstrap a repository, create files, or make changes**.
>
> Ignore this file unless:
>
> - the user explicitly references it; or
> - the user copies/pastes the prompt below into the conversation.
>
> The actual AI instructions live in the repository's `README.md`, `BOOTSTRAP.md`, workflows, core policies, Skills, and templates.

---

## Copy and Paste This Prompt

```text
I want to start a new software project and I want you to use the following AI engineering and security standards repository as the development standard for the project:

<PASTE_STANDARDS_REPOSITORY_URL_HERE>

This is a NEW project.

Before writing application code, read the standards repository and follow its AI Agent Entry Protocol, bootstrap instructions, new-project workflow, applicable core policies, and Skill-selection rules.

Do not start building the application immediately.

First, discuss the project with me and understand what I want to build.

Ask me the necessary questions progressively, in small logical groups. Do not give me a huge questionnaire at once, and do not ask questions I have already answered.

Your discovery should establish only what is relevant, including where applicable:

- the problem the product solves;
- target users;
- MVP scope;
- features that are required now;
- features that are planned or deferred;
- user roles;
- major user journeys;
- platform(s), such as mobile, web, desktop, backend/API, or hybrid;
- UI/UX expectations;
- technical stack or technical constraints;
- database/data model;
- authentication;
- authorization and ownership rules;
- file uploads/storage;
- payments and payment providers;
- chat/messaging;
- notifications;
- AI/LLM functionality;
- third-party services;
- sensitive/private data;
- countries/jurisdictions where the product or users operate;
- Google Play / Apple App Store distribution if applicable;
- deployment environments;
- reliability, retries, idempotency, failure handling, and recovery;
- security, privacy, compliance, and release considerations.

Do not invent important product or architecture decisions when I can answer them.

If I have not chosen a technology and a choice is genuinely required, give me a small number of suitable options with meaningful tradeoffs instead of choosing randomly.

Classify project capabilities as:

- Active
- Planned
- Deferred
- Not applicable
- Unknown

Determine which standards, policies, documents, and Skills from the standards repository actually apply.

Do not activate or copy every Skill into the active agent context.

Before meaningful development:

1. Verify whether the project is already inside a Git repository.
2. Do not create a nested Git repository.
3. If Git is not initialized, initialize it safely.
4. Create an appropriate `.gitignore`.
5. Ensure secrets, credentials, private keys, real environment files, generated artifacts, dependency folders, build output, and other sensitive/local files are not accidentally committed.
6. Use local Git commits as recovery checkpoints when appropriate.
7. Pushing to GitHub is not required for local version history.

Once there is enough project context, create the project-local AI development system described by the standards repository, including where applicable:

- `AGENTS.md`
- `docs/PROJECT_PROFILE.md`
- `docs/PROJECT_CAPABILITIES.md`
- `docs/DOCUMENTATION_INDEX.md`
- `docs/PRODUCT_DECISION_LOG.md`
- `docs/CHANGE_IMPACT_MAP.md`
- relevant product/technical/security/operations documents
- `.ai/STANDARDS_MANIFEST.md`
- `.ai/SKILL_CATALOG.md`
- `.ai/TASK_ROUTER.md`
- `.ai/standards-library/`
- `.agents/skills/` containing only the currently relevant active Skills

Record the standards repository source and source revision/commit in the standards manifest when available.

Keep the complete reusable standards available locally as the dormant standards library, but activate only the Skills that apply to the current project.

After bootstrap, normal development should rely on the project-local:

- `AGENTS.md`
- canonical project documentation
- `.ai/TASK_ROUTER.md`
- active `.agents/skills/`
- local dormant standards library

Do not keep rereading the remote standards repository during normal coding unless:

- I explicitly ask you to update the standards;
- a required local policy/Skill is missing; or
- current external provider/platform/regulatory requirements must be verified.

For payment providers, app-store rules, cybersecurity standards, laws, regulations, and other time-sensitive external policies:

- use the local policy module as the baseline;
- verify current requirements using the official authoritative source when implementation or release depends on them;
- do not treat a stored policy snapshot as permanently current;
- do not claim legal, regulatory, app-store, PCI, or provider compliance without evidence;
- flag material legal/licensing uncertainty for qualified human review.

Product decisions are allowed to change during development.

If I later:

- change my mind;
- remove a feature;
- change a provider;
- introduce a new role;
- add payments;
- add chat;
- add uploads;
- add notifications;
- add AI;
- expand to another platform or country;

automatically use the project's decision-change/add-feature process to update the affected:

- canonical documentation;
- Project Capabilities;
- Product Decision Log;
- architecture decisions;
- active Skills;
- standards manifest;
- security/privacy controls;
- tests;
- implementation plan.

I should not need to send the standards repository URL again just because the product grows.

During implementation and testing:

- make the smallest safe change;
- reuse existing logic and patterns;
- do not perform unrelated refactors;
- fix small, reproducible, clearly correct bugs found in the same affected surface when the fix is localized and low risk;
- retest after those fixes;
- report unrelated or broad issues instead of silently expanding scope;
- never knowingly ship a security vulnerability in the code path being created, modified, or validated.

Use `.ai/TASK_ROUTER.md`, `docs/DOCUMENTATION_INDEX.md`, and `docs/PROJECT_CAPABILITIES.md` to determine which documents and Skills to read for each task.

Do not scan every document, every Skill, or the entire repository merely to be thorough.

Before application implementation begins, give me a concise summary containing:

1. Project Profile.
2. MVP scope.
3. Active capabilities.
4. Planned/deferred capabilities.
5. Proposed technical architecture or confirmed existing choices.
6. Security/privacy-sensitive areas.
7. Applicable external policies/platforms/jurisdictions.
8. Skills you intend to activate.
9. Skills that are not currently applicable.
10. Documents you intend to create.
11. Important unresolved questions or blockers.
12. Git/bootstrap status.

Then continue according to the standards repository and the decisions we have made.
```
