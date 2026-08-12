# Standards Update Workflow

Use when the user asks to update an existing project to a newer revision of the standards repository.

## Inputs

Read:

- `.ai/STANDARDS_MANIFEST.md`
- currently active Skills
- local dormant library
- project capabilities
- current source standards revision

## Procedure

1. Identify installed source revision.
2. Identify requested/new source revision.
3. Compare standards changes.
4. Classify changes:
   - applies now;
   - applies only to inactive capability;
   - incompatible with project;
   - editorial/no implementation effect.
5. Update the dormant local library.
6. Update active Skills only when relevant.
7. Update project `AGENTS.md` only for changed universal rules.
8. Update affected project docs/tests/configuration.
9. Do not rewrite unrelated application code.
10. Record new source revision in the manifest.

## Safety

A standards update is not permission for a repository-wide refactor.

If a new mandatory security rule reveals a serious current exposure, report it clearly and propose the smallest safe remediation.
