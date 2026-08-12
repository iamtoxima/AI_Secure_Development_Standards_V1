# Discovered Bug Policy

AI-assisted development should remain proactive during implementation and testing without turning every task into a repository-wide cleanup.

## Related Low-Risk Bugs

While implementing, testing, smoke-checking, or validating requested work, the AI MAY fix an additional bug without asking first when all of the following are true:

- the bug is reproducible or clearly demonstrated by the current check;
- it is directly related to the feature, component, workflow, files, or behavior currently being changed or tested;
- the intended correct behavior is clear from the user's request, existing code, tests, or canonical documentation;
- the fix is small, localized, and low risk;
- the fix does not introduce a new product decision, architecture, dependency, provider, or unrelated behavior;
- relevant validation can be rerun after the fix.

Examples include:

- responsive overflow on the screen currently being changed;
- duplicate loading/status text in the handler currently being edited;
- an incorrect loading, empty, retry, or error state found during the current smoke test;
- a small validation or authorization omission in the endpoint currently being modified;
- a broken edge case exposed by a newly added test;
- a clearly duplicated assignment or stale branch inside the exact feature being validated.

When fixing such an issue:

1. make the smallest safe correction;
2. update related tests when practical;
3. rerun the relevant check;
4. mention the additional fix in the final summary.

## Unrelated or Broad Issues

Do not silently expand the task to repair unrelated defects elsewhere in the repository.

If a discovered issue is:

- unrelated to the current surface;
- architectural;
- ambiguous;
- high risk;
- dependent on a new product decision;
- likely to substantially expand the task;

then:

- do not ignore it;
- report it clearly;
- recommend a follow-up;
- ask before implementing it when necessary.

## Security Issues

Never knowingly leave a security vulnerability in the code path being created, modified, or validated merely because the user did not explicitly mention it.

If a discovered security issue is within the affected surface and has a clear, contained fix:

- fix it;
- add or update a regression/negative test when practical;
- rerun the relevant checks;
- report it in the final summary.

If the security issue is broader, architectural, or could materially change product behavior:

- do not knowingly ship an unsafe implementation;
- surface the risk immediately;
- explain what must change;
- keep the affected feature inaccessible or incomplete when necessary until the risk is addressed.

## Scope Principle

Use this rule:

```text
Same affected surface + small + clearly correct
    -> fix automatically and retest

Unrelated / broad / ambiguous
    -> report, do not silently expand scope

Security vulnerability in affected surface
    -> fix if contained, otherwise block unsafe shipment and escalate
```

## Version Control

Do not preserve superseded code by creating duplicate `/garbage`, `.old`, `.bak`, or backup implementations.

When obsolete code is safely replaced:

- remove the obsolete implementation;
- rely on Git history for recovery;
- preserve non-code historical artifacts only when the project explicitly requires archival.
