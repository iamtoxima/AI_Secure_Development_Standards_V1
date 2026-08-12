# Existing Project Workflow

Use when meaningful code, schema, infrastructure, or deployed behavior already exists.

## Goal

Install standards without pretending the project is new and without broad rewrites.

## 1. Preserve User Work

Before modification:

- detect the Git root;
- inspect working-tree state;
- do not reset/discard uncommitted work;
- do not create nested Git;
- do not commit unknown secrets/generated artifacts.

If the project has no Git repository, follow `core/VERSION_CONTROL.md`.

## 2. Targeted Reconnaissance

Inspect only enough to identify:

- platforms/frameworks
- architecture boundaries
- database/data layer
- auth/authorization approach
- storage
- APIs
- logging/error handling
- tests
- deployment
- existing documentation
- sensitive capabilities

Do not perform an exhaustive repository audit unless the user asks for one.

## 3. Ask the User What Code Cannot Answer

Examples:

- intended product scope
- future/deferred features
- business rules
- roles and permissions
- compliance/legal requirements
- why an unusual architecture decision exists
- accepted risk
- planned migration

## 4. Build Current-State Project Context

Create or update:

- PROJECT_PROFILE
- PROJECT_CAPABILITIES
- DOCUMENTATION_INDEX
- PRODUCT_DECISION_LOG
- CHANGE_IMPACT_MAP

Do not invent historical decisions that are not supported by evidence.

Label unknowns clearly.

## 5. Select Skills

Activate Skills based on actual project capabilities.

Do not install a Skill simply because a package exists but the feature is unused.

## 6. Remediation Strategy

Do not combine standards installation with a massive refactor.

Classify discovered gaps:

- critical immediate blocker
- high priority
- normal backlog
- future hardening
- accepted/not applicable

Fix only what the user requested or what is necessary to avoid an unsafe standards installation, unless the user asks for a broader remediation effort.

## 7. Baseline

Where safe:

- create a local baseline commit before substantial AI-generated remediation;
- preserve current behavior unless intentionally changed;
- add regression tests around critical behavior before risky refactors.
