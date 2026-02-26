# Skill: Task Planning Phase 2 (Sub-Tasks)

## Goal
Expand parent tasks into detailed sub-tasks and assemble the final task list.

## Inputs
- Confirmation "Go".
- Parent tasks list.
- PRD reference.

## Outputs
- Sub-tasks under each parent task.
- Final task list with `Relevant Files` and `Notes` sections.

## Mode
- autonomous

## Handoff
- Writes the final task list to `/tasks/` for execution.

## Rules
- Keep sub-tasks clear and actionable.
- Cover the full PRD scope.
- Follow the required Markdown structure.
- Include test guidance in `Notes`.
- Include a `Relevant Files` list with reasons.

## Required output structure
```
## Relevant Files

- `path/to/file` - Why it is relevant.

### Notes

- Unit tests should live alongside the code they test.
- Use `npx jest [optional/path/to/test]` to run tests.

## Tasks

- [ ] 1.0 Parent Task
  - [ ] 1.1 Sub-task
```

## Recommended model
- gpt-5.2-codex

## Suggested prompt
"With the 'Go' confirmation, expand each parent task into sub-tasks and output the final task list with the required sections and notes."
