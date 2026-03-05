---
name: subtask-execution
description: >-
  Protocol for implementing a single sub-task, updating the task list, and
  pausing for user approval before proceeding to the next sub-task.
---

## Goal

Implement a single sub-task and update the task list.

## Protocol (strict order)

1. Read the task list file and identify the next unchecked sub-task (`[ ]`).
2. Implement ONLY that one sub-task. Make minimal, focused changes.
3. Mark it `[x]` in the task list file immediately.
4. Update the `Relevant Files` section if new files were created or existing
   files were modified.
5. Explain the change briefly -- focus on WHY, not just WHAT.
6. **STOP** and ask: "Sub-task [n.m] complete. Ready for the next one? (yes/y)"
7. Do NOT proceed to the next sub-task until the user responds "yes" or "y".

## Rules

- ONE sub-task at a time. No exceptions.
- Minimal changes -- only what the sub-task requires.
- Update the task list file after every sub-task completion.
- Explain why after each sub-task, not just what changed.
- If you discover something that needs a new task, add it to the task list
  but do not work on it until it is the next unchecked item.
- If you encounter a blocker, stop and report it to the user.

## Output

- Code changes in the repository.
- Updated task list with the sub-task marked `[x]`.
- Brief explanation of the change.
- Pause message waiting for user approval.
