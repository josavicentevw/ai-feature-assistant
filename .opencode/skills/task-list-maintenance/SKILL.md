---
name: task-list-maintenance
description: >-
  Keep the task list and Relevant Files section accurate throughout execution.
  Mark completions, add emergent tasks, and verify all file paths exist.
---

## Goal

Keep the task list and relevant files accurate throughout the execution phase.

## Rules

1. **Sub-task completion** -- Mark each sub-task `[x]` immediately when it is
   finished. Do not batch updates.
2. **Parent task completion** -- Mark parent tasks `[x]` ONLY after:
   - ALL sub-tasks under it are `[x]`, AND
   - The closeout protocol has passed (tests + commit).
3. **Emergent tasks** -- Add new tasks as they are discovered during
   implementation. Place them logically within the existing structure.
4. **Relevant Files** -- Keep the section current:
   - Add every file created or modified during execution.
   - Give each file a one-line description of its purpose.
   - Remove files that are no longer relevant.
   - Use ONLY exact, verified paths. NEVER invent paths.
5. **Frequency** -- Update the task list file after each significant change,
   not just at the end of a session.

## Verification Checks

Periodically verify:
- No parent task is `[x]` while it has unchecked sub-tasks.
- All paths in Relevant Files actually exist in the repository.
- Task numbering is consistent (1.0, 1.1, 1.2, 2.0, 2.1, etc.).
- No duplicate tasks exist.

## Output

Updated task list file with accurate completion status and current Relevant
Files section.
