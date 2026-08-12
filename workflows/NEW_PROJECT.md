# New Project Workflow

Use when meaningful application code does not yet exist.

## 1. Discovery Before Code

Do not scaffold the app immediately.

Progressively establish:

- product/problem
- users and roles
- MVP scope
- out-of-scope/deferred features
- core journeys
- platform(s)
- technical preferences or constraints
- sensitive data
- auth/permissions
- integrations
- payments/uploads/chat/notifications/AI if applicable
- deployment expectations
- reliability expectations

## 2. Create Context

At minimum create:

- PROJECT_PROFILE
- PROJECT_CAPABILITIES
- PRODUCT_DECISION_LOG
- DOCUMENTATION_INDEX
- CHANGE_IMPACT_MAP
- PRD
- implementation plan

Create technical/data/UI/security/operations docs as applicable.

## 3. Establish Architecture

Do not choose technologies randomly.

When the user has not selected a technology and a choice is required:

- present a small set of suitable options;
- explain meaningful tradeoffs;
- account for team skill, budget, security, hosting, scale, and maintainability;
- record the selected decision.

## 4. Git

Initialize local Git before meaningful implementation.

Create a safe `.gitignore`.

Create a baseline commit after initial project context/configuration is ready.

## 5. Install Standards

Copy the dormant standards library locally.

Activate only relevant Skills.

Create small project `AGENTS.md`.

## 6. Plan the Build

Break work into testable milestones.

Typical categories may include:

- project scaffold
- auth
- data model
- core backend/API
- core UI
- integrations
- security hardening
- testing
- deployment
- launch verification

The actual order depends on the project.

## 7. Build

For each milestone:

1. read only relevant context;
2. implement small scope;
3. update docs;
4. run targeted tests;
5. review security implications;
6. create a stable local Git checkpoint when appropriate.
