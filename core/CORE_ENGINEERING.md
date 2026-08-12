# Core Engineering Policy

These rules are intended to apply broadly.

## Scope

- Inspect only task-relevant code, documentation, configuration, schema, and direct dependencies.
- Do not scan the entire repository unless the task genuinely requires it.
- Make the smallest safe change that fully solves the request.
- Do not perform unrelated refactors or speculative improvements.
- Preserve existing architecture and conventions unless the task requires change.

## Reuse

- Search the relevant scope before creating reusable logic.
- Reuse or extend existing functions, services, validators, clients, repositories, loggers, and error handlers when practical.
- Do not create parallel implementations of the same responsibility.
- Prefer one source of truth for business rules.

## Architecture

- Do not introduce a new framework, state system, database client, auth layer, logger, queue, cache, provider abstraction, or major dependency without concrete need.
- When the project already documents an architectural decision, follow it unless the user intentionally changes it.

## Trust

- External data is not authority.
- Client-provided IDs, roles, permissions, state, prices, payment status, ownership, and entitlements must not become trusted merely because they are well-formed.
- Security-sensitive truth should come from trusted server-side state or another explicitly trusted authority.

## Validation

- Validate data at trust boundaries.
- Use context-appropriate protections rather than generic character stripping.
- Prefer project-standard validation libraries and schemas over scattered manual validation.

## Testing

- Run the narrowest relevant checks.
- Test meaningful failure paths for security-sensitive work.
- Do not run the complete test suite merely by habit when a smaller targeted check is sufficient.
- Do not claim verification that did not run or did not complete.

## Documentation

- Behavior-changing work must update affected canonical documentation in the same task.
- Do not create duplicate documents when an existing canonical file covers the topic.
- Keep decision history when product choices change.

## Output

At completion, keep the report concise:

1. What changed.
2. Files affected.
3. Tests/checks performed.
4. Important risks, deferred work, or follow-up.

Do not narrate every internal step.

## Style

- Do not use emoji in code comments.

## Bugs Discovered During Work

- While implementing or testing the requested work, fix small, clearly correct, low-risk bugs found in the same affected surface.
- Do not ignore reproducible regressions merely because they were not named in the original request.
- Rerun the relevant check after the fix.
- Do not silently expand scope into unrelated repairs or broad cleanup.
- Report unrelated, architectural, ambiguous, or high-risk issues for follow-up.
- Never knowingly ship a contained security regression in the code path being created, modified, or validated.
- Follow `core/DISCOVERED_BUG_POLICY.md` for the full decision rule.
