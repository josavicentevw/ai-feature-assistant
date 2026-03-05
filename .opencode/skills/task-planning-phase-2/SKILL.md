---
name: task-planning-phase-2
description: >-
  Expand approved parent tasks into detailed sub-tasks with Relevant Files and
  Notes sections. Produces the final task list in the required Markdown format.
---

## Goal

Expand parent tasks into detailed sub-tasks and assemble the final task list.
This is Phase 2, executed only after the user confirms with "Go".

## Process

1. Receive the "Go" confirmation from the user.
2. Break each parent task into smaller, actionable sub-tasks.
3. Ensure sub-tasks logically follow from the parent task.
4. Cover the implementation details implied by the PRD.
5. Consider existing codebase patterns without being constrained by them.
6. Assemble with Relevant Files and Notes sections.
7. Save the complete task list to `/tasks/tasks-[prd-file-name].md`.

## Required Output Structure

```markdown
## Relevant Files

- `path/to/file.ts` - Brief description of why this file is relevant.
- `path/to/file.test.ts` - Unit tests for `file.ts`.

### Notes

- Unit tests should typically be placed alongside the code they test.
- Use the project's test runner to execute tests.

## Tasks

- [ ] 1.0 Parent Task Title
  - [ ] 1.1 Sub-task description
  - [ ] 1.2 Sub-task description
- [ ] 2.0 Parent Task Title
  - [ ] 2.1 Sub-task description
  - [ ] 2.2 Sub-task description
- [ ] 3.0 Parent Task Title
```

## Rules

- Keep sub-tasks clear, actionable, and specific.
- Cover the full PRD scope -- no requirements should be left unaddressed.
- Follow the required Markdown structure exactly.
- Include test guidance in the Notes section.
- Include a Relevant Files list with reasons for each file.
- Sub-tasks are numbered as `1.1`, `1.2`, `2.1`, `2.2`, etc.
- Each sub-task should be small enough to implement in one focused session.

## Output

The complete task list file saved to `/tasks/tasks-[prd-file-name].md`.
