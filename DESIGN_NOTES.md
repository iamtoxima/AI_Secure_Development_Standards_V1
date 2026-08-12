# V1 Design Notes

This repository intentionally incorporates several recurring principles from practical AI-assisted software-development/security checklists and project runbooks:

- context before code;
- product/technical/app-flow/data-model/implementation planning;
- explicit documentation sources of truth;
- same-task documentation updates;
- dated product decision logs;
- secure local Git checkpoints instead of duplicate backup code;
- explicit authorization and negative tests;
- idempotency beyond payments;
- environment separation;
- bounded request and upstream response handling;
- private-by-default sensitive storage;
- secure upload lifecycle including content validation/quarantine/scanning where risk warrants it;
- structured logging with recursive redaction and request IDs;
- evidence-based launch gates that reopen after related changes;
- feature flags/kill switches for risky deferred functionality;
- supply-chain and secret scanning during release verification;
- failure-mode/runbook thinking for external dependencies.

The V1 design deliberately separates:

1. universal project instructions;
2. dormant reusable standards;
3. active task/project Skills;
4. project-specific canonical documentation.

This is intended to reduce unnecessary context loading while keeping future standards available locally.

## Proactive Bug-Fix Boundary

V1 explicitly preserves useful AI behavior discovered during real testing:

- small related regressions can be corrected immediately;
- validation must be rerun;
- unrelated defects do not become silent scope expansion;
- security issues in the affected surface cannot be knowingly ignored.

This prevents "smallest safe change" from being misread as "never fix anything the user did not type explicitly."

## External Policy Architecture

V1 uses three layers for external requirements:

1. permanent universal security invariants in Skills;
2. provider/platform/jurisdiction snapshots in dormant policy modules;
3. live verification of time-sensitive requirements against official sources.

This prevents two opposite failures:

- a project having only vague "follow provider docs" instructions with no
  permanent security floor;
- a project hardcoding provider/app-store/legal details that silently become
  stale.

## Context Routing Layer

V1 includes a dedicated task router so project-local context selection is explicit.

The intended routing chain is:

```text
Task
  -> AGENTS.md
  -> TASK_ROUTER.md when needed
  -> DOCUMENTATION_INDEX.md
  -> PROJECT_CAPABILITIES.md
  -> only relevant canonical docs
  -> only relevant active Skills
```

This reduces both missed controls and unnecessary token/context use.
