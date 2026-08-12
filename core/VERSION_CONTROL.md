# Version Control Safety

Git is the default recovery mechanism for AI-driven development.

## Repository Detection

Before substantial modification:

1. Determine whether the working directory is already inside a Git repository.
2. Never create a nested Git repository inside an existing repository.
3. Inspect the working tree state before destructive or broad operations.

## New Projects

If no repository exists:

1. initialize Git;
2. create an appropriate `.gitignore`;
3. exclude secrets, credentials, private keys, environment files with real values, dependency/build artifacts, generated output, and sensitive local data;
4. create an initial local commit after the safe scaffold/context is ready.

Pushing to GitHub or another remote is not required for local Git history.

## Existing Projects

If the repository has uncommitted user changes:

- do not discard them;
- do not reset them;
- do not overwrite them;
- do not clean untracked files blindly;
- do not create a convenience commit containing unknown secrets or generated files.

Understand the state before proceeding.

## Recovery Checkpoints

Create meaningful local commits at stable milestones when appropriate, for example:

- initial scaffold
- authentication complete
- data model/migrations complete
- payment workflow complete
- major feature complete
- release candidate

Do not create noisy commits after every trivial edit unless the project workflow requires it.

## Destructive Git Operations

Do not use destructive operations such as hard reset, forced clean, history rewrite, or force push against user work unless:

- the user explicitly requests it;
- the consequences are understood;
- recoverability has been considered.

## Deprecated Code

Do not create `/garbage`, `.old`, `.bak`, or duplicate implementations merely to preserve history.

Git history is the default recovery method.

An archive/garbage directory may be used only for non-code historical artifacts when a project explicitly requires it and the canonical documentation has already absorbed the useful information.

Never preserve secrets in archives.
