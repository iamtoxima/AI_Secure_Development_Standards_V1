# Codex Adapter

Codex supports repository instructions through `AGENTS.md` and repo-scoped Skills under `.agents/skills/`.

Bootstrap should:

1. create a small repository-level `AGENTS.md`;
2. copy only currently applicable Skills to `.agents/skills/<name>/SKILL.md`;
3. keep the full reusable library outside `.agents/skills`, such as `.ai/standards-library/`;
4. keep Skill `description` concise and trigger-specific;
5. use only `name` and `description` in required Skill frontmatter unless additional metadata is intentionally supported.

The standards repository itself is agent-neutral in principle; this folder describes the Codex mapping.
