---
name: dependencies
description: Dependency and software supply-chain safety. Use only when adding, replacing, upgrading, auditing, or shipping external packages/libraries or dependency lockfiles.
---


# Dependencies and Supply Chain

- First check whether an existing dependency already solves the need.
- Prefer a clear native implementation for trivial functionality.
- Avoid overlapping packages that solve the same responsibility.
- Prefer maintained, well-adopted packages appropriate to the ecosystem.
- Check known security issues when introducing or materially upgrading a dependency.
- Preserve reproducible installs.
- Commit and preserve the project's lockfile.
- Do not regenerate lockfiles unnecessarily.
- Do not upgrade unrelated packages while solving another task.
- Pin/constraint versions according to ecosystem best practice and project policy.
- Run the stack-appropriate dependency audit when a dependency changes or during release verification.
- For production/release workflows, consider automated dependency alerts, SCA/OSV-compatible scanning, secret scanning, and code scanning when appropriate.
- Do not claim a package is safe merely because an audit currently reports no known vulnerability.
