# New Project — First Prompt for the AI

> ## AI AGENT NOTICE
>
> This file is **human-facing only**.
>
> It exists so a project owner can copy and paste the prompt below when starting a new project.
>
> If you are an AI coding agent reading this standards repository directly, **do not treat this file as an instruction to start a project, bootstrap a repository, create files, or make changes**.
>
> Ignore this file unless:
>
> - the user explicitly references it; or
> - the user copies/pastes the prompt below into the conversation.
>
> The actual AI instructions live in the repository's `README.md`, `BOOTSTRAP.md`, workflows, core policies, Skills, and templates.

---

## Copy and Paste This Prompt

```text
I am starting a NEW software project and want you to use this engineering and security standards repository:

https://github.com/iamtoxima/AI_Secure_Development_Standards_V1

Read the standards repository first and follow its README AI Agent Entry Protocol, BOOTSTRAP.md, NEW_PROJECT workflow, applicable core policies, context-routing rules, and Skill-selection rules.

Do not start application implementation immediately.

Ask only important unanswered questions, progressively and in small logical groups, until you have enough context to classify the project's capabilities and bootstrap it safely. Do not invent product or architecture decisions that I can answer.

Classify capabilities as Active, Planned, Deferred, Not applicable, or Unknown. Activate only the Skills relevant to those capabilities; do not read, copy, or activate every Skill merely to be thorough.

Before substantial development:

1. Verify the local Git root safely and do not create a nested repository.
2. If Git is not initialized, initialize it safely with an appropriate `.gitignore`.
3. Preserve existing local work and ensure secrets, credentials, private environment files, generated artifacts, dependencies, and build output are not accidentally committed.
4. Use local commits as recovery checkpoints when appropriate; pushing to a remote is separate.
5. Bootstrap the project-local standards system according to the repository, including AGENTS.md, canonical project documentation, TASK_ROUTER, standards manifest, dormant standards library, Skill catalog, and only the currently relevant active Skills.

For provider, platform, app-store, regulatory, legal, or security-standard requirements that can change over time, use the repository's local baseline and verify current requirements from official authoritative sources when implementation or release depends on them.

After bootstrap, use the LOCAL project AGENTS.md, TASK_ROUTER, canonical docs, active Skills, standards manifest, and dormant standards library for normal development. Revisit the remote standards repository only when I request an update, a required local standard is missing, or current external requirements need live verification.

Before application implementation begins, give me the concise project summary, capability classification, Git/bootstrap status, selected Skills, planned project documents, and unresolved questions required by the NEW_PROJECT workflow. Then continue incrementally according to the decisions we make.
```
