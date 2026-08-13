---
name: feature-lifecycle
description: Feature flags, staged rollout, deferred or incomplete capabilities, emergency kill switches, safe activation, and product-feature lifecycle controls.
---


# Feature Lifecycle

- A feature's code existing does not mean the feature is ready for users.
- Keep unfinished/high-risk functionality inaccessible until readiness gates pass.
- Prefer a safe disabled state for risky capabilities when practical.
- Use feature flags for staged rollout or emergency disable when justified.
- Feature flags are not authorization controls.
- Security checks remain mandatory when a flag is enabled.
- Protect feature-flag administration with trusted authorization.
- Audit high-impact flag changes when appropriate.
- Define rollback/disable behavior before launching risky capabilities.
- For small feature deferrals or presentation-only capability changes, follow the narrow synchronization rule in `core/DOCUMENTATION_LIFECYCLE.md`; do not treat hidden presentation as evidence that implementation, architecture, API, data, security, or operations changed.
- When a deferred feature becomes active, run the Add Feature workflow and activate the relevant Skills.
- When a feature is removed, update capabilities, docs, tests, routes, data lifecycle, and active Skills rather than leaving hidden stale functionality.
