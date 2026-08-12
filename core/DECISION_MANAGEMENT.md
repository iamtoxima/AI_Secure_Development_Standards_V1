# Decision Management

Product development is expected to change.

The AI must support changing decisions without allowing specifications, security controls, tests, and implementation to drift apart.

## Material Decision

A decision is material when it changes one or more of:

- product scope
- supported platform
- user role
- access/permission
- data collected or retained
- provider/integration
- architecture
- database schema
- external API
- payment behavior
- file/storage behavior
- messaging/notification behavior
- AI capability
- security boundary
- failure/retry behavior
- deployment/release behavior

## On a Material Change

1. Clarify the new intent if needed.
2. Read the current relevant canonical docs only.
3. Read the previous decision entry.
4. Use `CHANGE_IMPACT_MAP.md`.
5. Update current canonical requirements.
6. Append the decision to `PRODUCT_DECISION_LOG.md`.
7. Update `PROJECT_CAPABILITIES.md`.
8. Update architecture decision records when applicable.
9. Activate/deactivate Skills when capability scope changed.
10. Update security controls and tests.
11. Create a Git checkpoint before substantial implementation when appropriate.
12. Implement the change.
13. Verify the new behavior and important failure paths.

## Reversibility

Prefer reversible implementation strategies for uncertain or high-risk product decisions.

Consider:

- feature flags;
- safe disabled states;
- additive migrations followed by cleanup;
- staged rollouts;
- compatibility periods.

Do not keep permanently duplicated code just to preserve reversibility.
