# Documentation Lifecycle

Documentation is part of the product state.

## Canonical Source of Truth

Maintain `docs/DOCUMENTATION_INDEX.md`.

Every important topic should have one canonical active document where practical.

Before creating a new root-level or `docs/` document:

1. check the documentation index;
2. search for an existing canonical document;
3. update the existing document instead of creating a duplicate.

## Same-Task Synchronization

When implementation or product decisions affect any of the following, update the relevant documentation in the same task:

- product behavior
- supported roles
- user flow
- API contracts
- database/data model
- storage/file paths
- permissions/authorization
- security posture
- environment variables/secrets
- external providers
- payments
- webhooks
- notifications
- background jobs
- retry/idempotency behavior
- logging/audit events
- deployment/release behavior
- failure modes
- testing requirements

Do not knowingly leave documentation describing behavior that no longer exists.

## Small Deferrals and Presentation-Only Changes

When a small feature is deferred or only its presentation, visibility, or availability changes:

- update only documentation whose canonical truth actually changed;
- usually update `PROJECT_CAPABILITIES.md` and `PRODUCT_DECISION_LOG.md`;
- update the PRD or other product specification only when user-visible product requirements changed materially;
- do not update implementation or function registries when the underlying logic remains unchanged;
- do not update architecture, API, data-model, security, or operational documentation merely because a feature is hidden or deferred, unless those systems also changed.

Do not infer an implementation or system-contract change from a presentation-only capability change. This narrow synchronization rule keeps canonical documentation accurate without loading or rewriting unaffected context.

## Decision Changes

Do not rewrite history as if the old decision never existed.

When the user changes a material decision:

- update the current canonical specification;
- append the new decision to `PRODUCT_DECISION_LOG.md`;
- preserve the prior decision and its reason when useful;
- update `PROJECT_CAPABILITIES.md`;
- update architecture decisions when relevant;
- update affected Skills and tests.

## Evidence Status

A document may describe a control as:

- Planned
- Implemented
- Verified
- Deferred
- Blocked
- Not applicable

Do not mark a control Verified merely because code exists.

## Archival

Historical documents may be archived when:

- their useful current content has been folded into canonical docs;
- they are clearly marked historical;
- they do not contain secrets.

Do not keep stale active documents alongside current documents without clear status.
