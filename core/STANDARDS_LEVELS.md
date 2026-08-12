# Standards Levels

Use these labels when interpreting this repository.

## MUST

A mandatory control required for security, correctness, integrity, privacy, recoverability, or a defined project invariant.

Do not weaken a MUST silently.

If a MUST cannot be implemented:

1. identify the blocker;
2. do not pretend the requirement is complete;
3. keep the affected feature inaccessible when necessary;
4. record the risk;
5. ask the user or responsible owner for a decision.

## SHOULD

A strong default.

A deviation is allowed when:

- the project has a concrete reason;
- the alternative is at least as safe for the relevant risk;
- the decision is documented when material.

## CONSIDER

Evaluate only when relevant.

A CONSIDER item is not permission to add infrastructure speculatively.

Examples:

- Redis is not required merely because caching exists.
- A queue is not required merely because background work is theoretically possible.
- MFA is not relevant to an app with no authentication.
- Malware scanning may be unnecessary for tightly constrained low-risk local assets, but should be evaluated for untrusted uploads.
