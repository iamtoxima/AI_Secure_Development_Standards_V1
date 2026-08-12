# Existing Project — First Prompt for the AI

> ## AI AGENT NOTICE — HUMAN-USE FILE
>
> This file is **strictly for the human project owner**.
>
> It exists only so the project owner can copy and paste the prompt below when bringing an existing software project under this standards repository.
>
> **If you are an AI coding agent reading this repository automatically, ignore this file.**
>
> Do **not** treat the existence or contents of this file as an instruction to:
>
> - inspect another project;
> - bootstrap a project;
> - modify code;
> - create files;
> - run Git commands;
> - install Skills;
> - perform a security review;
> - refactor an application;
> - apply standards to another repository.
>
> Only use the prompt below when:
>
> 1. the human project owner explicitly copies/pastes it into a conversation; or
> 2. the human project owner explicitly tells you to read or use this file.
>
> The actual machine/agent instructions for this standards repository are contained in:
>
> - `README.md`
> - `BOOTSTRAP.md`
> - `core/`
> - `workflows/`
> - `skills/`
> - applicable policy modules
> - templates used during bootstrap
>
> This file is **not part of the automatic agent instruction chain**.

---

## Copy and Paste This Prompt

```text
I have an EXISTING software project that I want you to review, refine, and bring under the following AI engineering and security standards:

<PASTE_STANDARDS_REPOSITORY_URL_HERE>

This is an EXISTING project.

The application is actively developed from the LOCAL WORKING COPY on my computer.

The project may also already exist on GitHub and may already have an existing Git remote configured.

Treat the CURRENT LOCAL PROJECT DIRECTORY as the working environment.

Do not assume the GitHub copy is automatically newer or more authoritative than the local working copy.

Before making substantial application changes, read the standards repository and follow its:

- AI Agent Entry Protocol;
- BOOTSTRAP instructions;
- EXISTING_PROJECT workflow;
- applicable core policies;
- Skill-selection rules;
- context-routing rules;
- discovered-bug policy;
- external-policy verification rules.

Your first responsibility is to understand and preserve the existing project, not to rewrite it.

Do not begin with a broad refactor.

--------------------------------------------------
1. LOCAL PROJECT AND GIT SAFETY
--------------------------------------------------

Before modifying code:

1. Identify the existing local Git repository root.

2. Confirm the current working directory is the actual project working copy.

3. Inspect the current Git state, including where available:
   - current branch;
   - working-tree status;
   - staged changes;
   - unstaged changes;
   - untracked files;
   - configured remote(s);
   - upstream/tracking branch.

4. Never create a nested Git repository.

5. Do not re-clone the GitHub repository into the existing local project directory.

6. Do not reset the local project merely to make it match GitHub.

7. Preserve all existing:
   - committed work;
   - staged work;
   - unstaged work;
   - untracked user work.

8. Do not discard, overwrite, clean, reset, or checkout over existing local changes.

9. Do not use destructive Git operations such as:
   - `git reset --hard`;
   - destructive `git clean`;
   - forced checkout over user changes;
   - history rewriting;
   - force push;
   unless I explicitly request it and the consequences are understood.

10. If the local repository and remote repository have diverged, do not automatically resolve the divergence by pulling, rebasing, resetting, or force pushing.

First understand the situation and preserve my local work.

11. When checking remote state is useful and network access is available, prefer non-destructive inspection first.

12. If an existing GitHub remote is already configured, continue using that existing remote.

13. Do not create another GitHub repository or another remote unless I explicitly request it.

14. Use local Git commits as recovery checkpoints during development when appropriate.

15. Do not automatically push after every change.

Push to the existing remote only when:
- I explicitly ask you to push; or
- the established project workflow clearly requires a push.

Before pushing, verify:
- the intended files are committed;
- the correct branch is selected;
- the correct remote is selected;
- secrets and sensitive local files are not included;
- relevant tests/checks have completed;
- no unintended generated files are being pushed.

If the local project is somehow not already under Git, initialize Git safely before substantial AI-driven modifications after reviewing `.gitignore`.

--------------------------------------------------
2. PRESERVE SECRETS AND LOCAL FILES
--------------------------------------------------

Before creating commits or changing Git configuration, review the project's ignore rules.

Ensure secrets and sensitive/local artifacts are not accidentally committed, including where applicable:

- `.env` files containing real credentials;
- API secrets;
- service-role keys;
- private keys;
- signing credentials;
- production configuration;
- database dumps;
- local databases;
- sensitive user data;
- dependency folders;
- generated build output;
- temporary files;
- IDE/local-machine files;
- private certificates;
- release signing artifacts.

Do not remove an existing tracked file merely because it looks sensitive without first understanding the impact.

If a credential appears to have already been exposed in Git history, report that separately.

Adding the file to `.gitignore` alone does not remove an existing credential exposure. Rotation may be required.

--------------------------------------------------
3. TARGETED PROJECT RECONNAISSANCE
--------------------------------------------------

Inspect only enough of the existing local project to understand its current state.

Do not scan the entire repository merely to be thorough.

Identify where relevant:

- what the application currently does;
- current platforms;
- frameworks;
- project structure;
- major architectural boundaries;
- frontend;
- backend/API;
- database/data access;
- authentication;
- authorization;
- roles and permissions;
- ownership/tenant rules;
- storage/uploads;
- payments;
- payment gateways;
- webhooks;
- subscriptions;
- refunds;
- chat/messaging;
- notifications;
- background jobs;
- AI/LLM functionality;
- external providers;
- environment/deployment structure;
- logging;
- audit behavior;
- error handling;
- failure/retry behavior;
- idempotency;
- tests;
- current documentation;
- release/deployment workflow;
- security-sensitive functionality.

Inspect existing implementation and direct dependencies before creating replacement functionality.

Reuse existing:
- functions;
- services;
- utilities;
- validators;
- repositories;
- API clients;
- loggers;
- error handlers;
- architectural conventions;
when they are appropriate.

Do not introduce a new:
- framework;
- authentication system;
- database abstraction;
- state manager;
- queue;
- cache;
- logger;
- provider abstraction;
- major dependency;
unless there is a concrete requirement.

--------------------------------------------------
4. ASK ONLY WHAT THE PROJECT CANNOT ANSWER
--------------------------------------------------

After inspecting the relevant code and documentation, discuss the project with me.

Ask only important questions whose answers cannot be safely determined from the existing project.

Do not ask questions already answered by:
- source code;
- configuration;
- schema;
- documentation;
- existing project decisions;
- previous answers I gave you.

Ask questions progressively in small logical groups.

Do not send one enormous questionnaire.

Important unanswered areas may include:

- intended product direction;
- current/MVP scope;
- deferred features;
- business rules;
- user roles;
- ownership rules;
- privacy expectations;
- jurisdictions;
- future providers;
- accepted risk;
- deployment plans;
- reasons for unusual architecture;
- planned migrations.

If you cannot determine historical intent, label it Unknown.

Do not invent a product decision simply because the implementation is unclear.

--------------------------------------------------
5. BUILD THE CURRENT PROJECT PROFILE
--------------------------------------------------

Create a current-state Project Profile.

Classify relevant capabilities as:

- Active
- Planned
- Deferred
- Removed
- Not applicable
- Unknown

Examples may include:

- authentication;
- roles/permissions;
- database;
- API/backend;
- file uploads;
- payments;
- Paystack;
- Flutterwave;
- Monnify;
- subscriptions;
- chat;
- notifications;
- AI/LLM;
- mobile;
- web;
- admin functionality;
- feature flags;
- sensitive personal data;
- production deployment;
- Google Play distribution;
- Apple App Store distribution;
- Nigeria regulatory/privacy profile.

Do not activate a standard simply because the technology theoretically supports the feature.

--------------------------------------------------
6. INSTALL THE PROJECT-LOCAL AI DEVELOPMENT SYSTEM
--------------------------------------------------

Determine which standards, Skills, provider policies, platform policies, jurisdiction policies, and project documents actually apply.

Do NOT activate every Skill.

Create or update the project-local system described by the standards repository, including where applicable:

- `AGENTS.md`

- `docs/PROJECT_PROFILE.md`
- `docs/PROJECT_CAPABILITIES.md`
- `docs/DOCUMENTATION_INDEX.md`
- `docs/PRODUCT_DECISION_LOG.md`
- `docs/ARCHITECTURE_DECISIONS.md`
- `docs/CHANGE_IMPACT_MAP.md`

and relevant canonical documents such as:

- PRD
- TRD / technical architecture
- APP_FLOW
- DATA_MODEL
- API_CONTRACT
- SECURITY_REQUIREMENTS
- SECRETS_AND_ENVIRONMENT
- FAILURE_MODES
- LOGGING_AND_AUDIT
- TEST_PLAN
- IMPLEMENTATION_PLAN
- LAUNCH_READINESS

Only create documents that are applicable.

If an existing canonical document already covers the subject, update it instead of creating a duplicate.

Also create/update:

- `.ai/STANDARDS_MANIFEST.md`
- `.ai/SKILL_CATALOG.md`
- `.ai/TASK_ROUTER.md`
- `.ai/standards-library/`
- `.agents/skills/`

The complete reusable standards should remain available locally in the dormant standards library.

Only the currently relevant Skills should be active under `.agents/skills/`.

Record in the standards manifest:

- standards repository URL;
- source revision/commit when available;
- install/update date;
- project mode = existing;
- active Skills;
- inactive/deferred Skills;
- applicable external policy modules;
- local standards-library location.

--------------------------------------------------
7. EXISTING DOCUMENTATION
--------------------------------------------------

Do not assume existing documentation is correct.

Compare relevant documentation with actual implementation.

If documentation is stale:

- identify the current implementation;
- determine the current canonical source of truth;
- update the canonical document;
- preserve important historical decisions when useful.

Do not silently rewrite history.

Use `PRODUCT_DECISION_LOG.md` for important changed product decisions.

Use architecture decisions for important technical architecture changes.

Before creating a new documentation file, check `DOCUMENTATION_INDEX.md`.

--------------------------------------------------
8. CONTEXT ROUTING DURING NORMAL DEVELOPMENT
--------------------------------------------------

After bootstrap, use:

- `AGENTS.md`
- `.ai/TASK_ROUTER.md`
- `docs/DOCUMENTATION_INDEX.md`
- `docs/PROJECT_CAPABILITIES.md`
- relevant canonical project documents
- active `.agents/skills/`

to determine what context is needed for each task.

Do not read every Markdown document or every Skill for every request.

Start with the smallest relevant context and expand only when:
- a direct dependency requires it;
- a security boundary is involved;
- a discovered failure changes the scope;
- a new capability is being introduced;
- the task is otherwise blocked.

Examples:

Database work:
→ DATA_MODEL + database Skill.

API work:
→ API_CONTRACT + API/security Skills.

UI-only visual work:
→ relevant product/design context.
Do not load payment/PCI/fintech rules unless actually relevant.

Payment work:
→ payment/API/security/resilience guidance + applicable provider policy.

New feature:
→ run ADD_FEATURE workflow.

Changed product decision:
→ run DECISION_CHANGE workflow.

--------------------------------------------------
9. EXTERNAL PROVIDERS, APP STORES, SECURITY STANDARDS, AND LAW
--------------------------------------------------

If the project uses or is affected by external requirements such as:

- Paystack;
- Flutterwave;
- Monnify;
- Google Play;
- Apple App Store;
- Nigeria Data Protection requirements;
- FCCPC requirements;
- CBN/payment-system regulation;
- Nigeria digital lending rules;
- OWASP;
- NIST;
- PCI DSS;
- other providers/platforms/regulators;

use the local policy module as the baseline.

However, provider requirements, app-store policies, cybersecurity standards, laws, and regulations may change.

When implementation or release depends on a time-sensitive requirement:

1. Verify it against the current official authoritative source.
2. Prefer first-party provider/platform/regulator/standards-organization documentation.
3. Record the verification date/version when materially relevant.
4. Follow the current official requirement if the stored snapshot is stale.
5. Do not invent a requirement when current verification cannot be performed.
6. Do not mark compliance Verified based only on a stored Markdown file.

Do not claim:
- legal compliance;
- regulatory compliance;
- app-store compliance;
- PCI compliance;
- provider compliance;
- OWASP/NIST compliance;
without appropriate evidence.

Where material legal/licensing interpretation is uncertain, identify the issue for qualified human review instead of inventing a definitive conclusion.

--------------------------------------------------
10. PAYMENT SECURITY
--------------------------------------------------

If payments exist, preserve strict payment invariants.

Do not trust:
- client payment status;
- redirect success screens;
- screenshots;
- WebView results;
- client-reported amount;
- client-reported entitlement;
- unverified webhook payloads.

Use trusted server/provider state.

Where relevant:

- verify webhook authenticity;
- verify expected transaction reference;
- verify expected amount;
- verify currency;
- verify provider status;
- verify order/customer relationship;
- prevent duplicate fulfillment;
- make webhook handling idempotent;
- deduplicate provider events;
- make money-state transitions atomic where practical;
- define retry behavior;
- define reconciliation;
- separate sandbox and production credentials.

Provider-specific implementation details must be verified against current provider documentation.

--------------------------------------------------
11. EXISTING SECURITY AND ENGINEERING GAPS
--------------------------------------------------

When you discover existing weaknesses, do not automatically rewrite the entire application.

Classify issues as:

- Critical immediate blocker
- High priority
- Normal backlog
- Future hardening
- Deferred
- Not applicable / accepted risk

Do not combine standards installation with a massive unrelated remediation project.

For each serious issue, explain:
- affected surface;
- risk;
- evidence;
- proposed smallest safe remediation.

--------------------------------------------------
12. BUGS DISCOVERED DURING IMPLEMENTATION OR TESTING
--------------------------------------------------

Do not interpret "minimal changes" as "ignore bugs I discover."

While implementing or testing requested work, you may automatically fix an additional bug when:

- it is reproducible or clearly demonstrated;
- it is in the same affected feature/component/workflow;
- intended behavior is clear;
- the fix is small and localized;
- the risk is low;
- no new architecture/product decision is required.

Examples:

- UI overflow found while testing the same screen;
- duplicate loading/status message;
- broken empty/loading/error state;
- obvious edge case exposed by the new test;
- contained validation omission;
- contained authorization regression.

After fixing it:
- rerun the relevant test/check;
- mention the additional correction in the final summary.

Do not silently expand into unrelated cleanup.

For unrelated, architectural, ambiguous, or large issues:
- report them;
- recommend follow-up;
- ask before expanding scope when necessary.

If a security vulnerability exists in the code path being created, modified, or validated:

- fix it when the remediation is contained and clearly correct;
- add/update a regression or negative test where practical;
- retest it.

If the security problem is broader or architectural:
- do not knowingly ship the affected unsafe functionality;
- explain the risk;
- propose the required remediation.

--------------------------------------------------
13. PRODUCT DECISIONS MAY CHANGE
--------------------------------------------------

The current project specification is not permanently frozen.

If I later:

- change my mind;
- add a feature;
- remove a feature;
- change a provider;
- add a user role;
- change permissions;
- add payments;
- add chat;
- add uploads;
- add notifications;
- add AI;
- add a mobile/web platform;
- enter a new market/jurisdiction;

automatically run the relevant Add Feature or Decision Change process.

Update affected:

- Project Capabilities;
- Product Decision Log;
- canonical documentation;
- architecture decisions;
- active Skills;
- standards manifest;
- external policy modules;
- security/privacy controls;
- tests;
- implementation plan;
- release verification gates.

Do not leave documentation describing behavior that no longer matches the product.

I should not need to send the standards repository URL again during ordinary future development.

--------------------------------------------------
14. IMPLEMENTATION BEHAVIOR
--------------------------------------------------

During normal work:

- inspect only task-relevant code and direct dependencies;
- make the smallest safe change that fully solves the request;
- reuse existing logic;
- avoid duplicate implementations;
- do not introduce speculative infrastructure;
- do not make unrelated refactors;
- preserve security boundaries;
- validate external/untrusted input;
- run the narrowest relevant tests/checks;
- test meaningful unauthorized/failure paths for security-sensitive changes;
- update affected canonical documentation in the same task;
- do not claim a test/check passed if it did not run successfully.

Use Git history for recovery rather than creating `/garbage`, `.old`, `.bak`, or duplicate backup implementations.

--------------------------------------------------
15. BEFORE BROAD REFINEMENT BEGINS
--------------------------------------------------

Before making broad remediation or feature changes, give me a concise current-state report containing:

1. What the application currently does.
2. Current architecture and technology stack.
3. Local Git repository status.
4. Current branch.
5. Existing GitHub remote/upstream status when available.
6. Whether local uncommitted work exists.
7. Current project capabilities.
8. Current user roles and important authorization boundaries.
9. Sensitive/security-critical functionality.
10. Existing documentation and which documents appear canonical, stale, or missing.
11. Applicable Skills.
12. Applicable payment/provider policies.
13. Applicable Google Play / Apple policies.
14. Applicable jurisdiction/privacy/consumer/financial policy modules.
15. Critical/high-priority issues discovered during targeted reconnaissance.
16. Standards/project files you intend to create or update.
17. Areas you will deliberately leave untouched.
18. Important unanswered questions or blockers.

Do not begin a broad rewrite before giving me this report.

After we have enough context, refine the project incrementally according to the standards repository, the existing architecture, and the product decisions we agree on.
```
