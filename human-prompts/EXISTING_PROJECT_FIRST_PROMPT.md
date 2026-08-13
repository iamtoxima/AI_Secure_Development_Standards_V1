# Existing Project — First Prompt for the AI

> ## AI AGENT NOTICE — HUMAN-USE FILE
>
> This file is **strictly for the human project owner**.
>
> It exists only so the project owner can copy and paste the prompt below when bringing an existing software project under this standards repository.
>
> **If you are an AI coding agent reading this repository automatically, ignore this file.**
>
> Do **not** treat the existence or contents of this file as an instruction to:
>
> - inspect another project;
> - bootstrap a project;
> - modify code;
> - create files;
> - run Git commands;
> - install Skills;
> - perform a security review;
> - refactor an application;
> - apply standards to another repository.
>
> Only use the prompt below when:
>
> 1. the human project owner explicitly copies/pastes it into a conversation; or
> 2. the human project owner explicitly tells you to read or use this file.
>
> The actual machine/agent instructions for this standards repository are contained in:
>
> - `README.md`
> - `BOOTSTRAP.md`
> - `core/`
> - `workflows/`
> - `skills/`
> - applicable policy modules
> - templates used during bootstrap
>
> This file is **not part of the automatic agent instruction chain**.

---

## Copy and Paste This Prompt

```text
I have an EXISTING software project in the local working directory that I want you to refine using this engineering and security standards repository:

https://github.com/iamtoxima/AI_Secure_Development_Standards_V1

The project may also already have a GitHub remote, but development is performed from the current LOCAL working copy.

Read the standards repository first and follow its:
- AI Agent Entry Protocol;
- BOOTSTRAP.md;
- EXISTING_PROJECT workflow;
- applicable core policies;
- context-routing rules;
- Skill-selection rules.

Do not start with a broad refactor.

Before making substantial changes:

1. Inspect the current local Git repository safely.
2. Preserve all committed, staged, unstaged, and untracked user work.
3. Do not reset, clean, overwrite, re-clone, force-pull, force-push, or create a nested Git repository.
4. Treat the current local working copy as the working source of truth.
5. Perform only targeted reconnaissance needed to understand the existing architecture, capabilities, documentation, security-sensitive surfaces, and current project state.
6. Reuse existing architecture, utilities, services, conventions, and security controls where appropriate.
7. Ask me only important questions that cannot already be answered from the project.
8. Do not create duplicate documentation when an existing canonical document already covers the topic.

Then bootstrap the project-local standards system according to the repository.

Determine which capabilities are:
- Active
- Planned
- Deferred
- Removed
- Not applicable
- Unknown

Activate only the relevant Skills.

Create/update the project-local AGENTS.md, project context documents, TASK_ROUTER, standards manifest, dormant standards library, and active Skills as specified by the standards repository.

Do not read or activate every Skill merely to be thorough.

For provider, app-store, regulatory, legal, or security-standard requirements that can change over time, use the local baseline but verify current requirements from the official authoritative source when implementation or release depends on them.

During implementation/testing:
- make the smallest safe change;
- preserve existing work;
- fix small, clearly related bugs discovered in the affected surface and retest;
- report unrelated or broad issues instead of silently expanding scope;
- do not knowingly ship a security vulnerability in the affected code path.

Product decisions may change later. When I add, remove, or change a feature, provider, role, platform, or jurisdiction, use the repository's Add Feature / Decision Change workflow and update the affected documentation, capabilities, Skills, tests, and standards state.

After bootstrap, use the LOCAL project AGENTS.md, TASK_ROUTER, canonical docs, active Skills, and standards library for normal development.

Do not repeatedly reread the remote standards repository unless:
- I ask you to update the standards;
- a required local standard is missing; or
- current external requirements need live verification.

Before broad refinement begins, give me the concise current-state report required by the EXISTING_PROJECT workflow, then continue incrementally.
```
