# Project AI Engineering Rules

These rules apply to AI coding work in this repository.

## Scope

- Inspect only task-relevant code, docs, configuration, schema, and direct dependencies.
- Do not scan the entire repository unless necessary.
- Make the smallest safe change that fully solves the request.
- Avoid unrelated refactors and speculative infrastructure.
- Reuse existing functions, utilities, clients, services, validators, loggers, and patterns when practical.
- Search the relevant scope before creating duplicate reusable logic.

## Architecture and Security

- Preserve documented architecture unless the task intentionally changes it.
- Do not introduce a new framework, provider, auth layer, database client, logger, queue, cache, or major dependency without concrete need.
- Security boundaries are mandatory.
- Treat external/client data as untrusted.
- Do not trust client-supplied roles, ownership, permission, price, payment status, entitlement, or privileged state.
- Enforce protected authorization in trusted server/policy logic.

## Git Safety

- Respect the existing Git root.
- Do not create nested Git repositories.
- Do not discard or overwrite uncommitted user work.
- Do not use destructive Git operations without explicit approval.
- Use Git history rather than duplicate backup/garbage code.
- Create a recovery checkpoint before substantial risky changes when appropriate.

## Product Decisions and Documentation

Product decisions may change.

When the user changes a material decision or adds/removes a capability:

1. update `docs/PROJECT_CAPABILITIES.md`;
2. append the decision to `docs/PRODUCT_DECISION_LOG.md`;
3. consult `docs/CHANGE_IMPACT_MAP.md`;
4. update affected canonical docs in the same task;
5. activate/deactivate relevant local Skills;
6. update `.ai/STANDARDS_MANIFEST.md`;
7. update relevant tests/security controls.

Do not leave stale documentation behind.

Before creating a new documentation file, check `docs/DOCUMENTATION_INDEX.md`.

## Skills

Use active Skills under `.agents/skills/`.

If a newly requested capability requires an inactive Skill, use the dormant local copy in `.ai/standards-library/`, activate it, and update the manifest.

Do not fetch the remote standards repository during ordinary development unless the required local standard is missing or the user requests a standards update.

## Verification

- Run the narrowest relevant tests, lint, type checks, or security checks.
- For security-sensitive changes, test important unauthorized/failure paths.
- Do not claim a check passed if it was not run or did not complete.
- Do not mark a release/security gate complete without evidence.

## Style

- Do not use emoji in code comments.

## Completion Report

Keep the final report concise:

1. What changed.
2. Files affected.
3. Tests/checks performed.
4. Important risk, blocker, or follow-up.

## Bugs Discovered During Implementation or Testing

- Fix small, reproducible, clearly correct bugs found in the same affected surface when the fix is localized and low risk.
- Rerun the relevant test/check after the fix.
- Mention the additional fix in the completion summary.
- Do not silently expand into unrelated cleanup, architecture changes, or ambiguous product decisions.
- Report unrelated or broad issues for follow-up.
- If a security vulnerability is discovered in the code path being created, modified, or validated, fix it when contained or block unsafe shipment and surface the risk when broader.

## External Policies and Current Requirements

When implementation/release depends on payment-provider rules, app-store policy,
law/regulation, or another external security standard:

- use the local policy module to determine the baseline;
- verify time-sensitive requirements against the current official source;
- prefer provider/platform/regulator/standards-organization sources;
- do not mark compliance Verified from a stored snapshot alone;
- do not invent legal/licensing conclusions when qualified review is required.

## Context Routing

Do not read every project document or Skill for every task.

Before implementation:

1. Classify the requested change by affected capability/surface.
2. Read `docs/DOCUMENTATION_INDEX.md` when document routing is needed.
3. Read `docs/PROJECT_CAPABILITIES.md` when capability applicability matters.
4. Read `.ai/TASK_ROUTER.md` when the task spans multiple concerns or the correct context is not obvious.
5. Read only the canonical documents relevant to the requested change.
6. Use only Skills relevant to the affected capability/surface.
7. Expand context only when blocked, when a direct dependency requires it, or when a discovered risk changes scope.

Examples:

- Database query/schema change:
  - read the data model/database docs;
  - use the database Skill;
  - add security/resilience only if the change crosses those boundaries.
- API behavior change:
  - read the API contract;
  - use API/security Skills as relevant.
- UI-only visual change:
  - read relevant design/product context;
  - do not load payment/database/compliance policies unless behavior actually touches them.
- Payment change:
  - read payment/API/security/resilience guidance;
  - read the applicable provider policy;
  - verify time-sensitive provider rules when needed.
- New capability:
  - run the Add Feature workflow before implementation.
- Changed product decision:
  - run the Decision Change workflow before implementation.

Do not scan all docs, all Skills, or the full repository merely to be thorough.
