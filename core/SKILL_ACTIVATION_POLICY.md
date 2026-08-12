# Skill Activation Policy

The standards repository may contain many Skills. A project should not actively load all of them.

## Dormant Library

After bootstrap, maintain a local copy of the reusable Skill library under:

`.ai/standards-library/`

This directory is not intended as an auto-loaded agent instruction location.

## Active Skills

Install currently applicable Skills under the coding agent's supported local Skill directory.

For Codex:

`.agents/skills/<skill-name>/SKILL.md`

## Activate a Skill When

- the capability is active;
- the task is implementing that capability now;
- the project contains a persistent architectural concern covered by the Skill.

## Do Not Activate a Skill Merely Because

- the capability might exist someday;
- an example in this repository mentions it;
- the technology theoretically supports it.

## Feature Added Later

When a newly requested capability maps to an inactive local Skill:

1. activate the local dormant copy;
2. record it in the manifest;
3. update project capabilities;
4. perform change-impact analysis;
5. ask capability-specific questions;
6. update docs/tests;
7. implement.

The remote standards repository should not be required for ordinary capability activation.
