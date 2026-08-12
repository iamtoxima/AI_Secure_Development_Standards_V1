# Decision Change Workflow

Use whenever the user changes a previous product, architecture, security, provider, data, or scope decision.

## Procedure

1. Identify the old decision.
2. Confirm the new intent.
3. Ask only unanswered questions needed to implement the new direction.
4. Determine whether the change:
   - activates a capability;
   - removes a capability;
   - changes a role;
   - changes data;
   - changes provider/architecture;
   - changes a security boundary;
   - changes a failure/retry path.
5. Read `CHANGE_IMPACT_MAP.md`.
6. Update the current canonical requirements.
7. Append a dated decision entry.
8. Update Project Capabilities.
9. Update Architecture Decisions when relevant.
10. Activate/deactivate local Skills as needed.
11. Update security requirements and tests.
12. Update implementation plan.
13. Create a Git checkpoint before broad/risky changes where appropriate.
14. Implement.
15. Verify the new state.
16. Remove obsolete code when safe; rely on Git history rather than duplicate backup code.

## Never

- silently rewrite old decisions;
- leave stale docs;
- keep a Skill active after the capability is permanently removed unless another active concern still needs it;
- weaken security merely because the new decision is urgent.
