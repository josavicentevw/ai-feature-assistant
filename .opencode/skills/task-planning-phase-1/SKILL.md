---
name: task-planning-phase-1
description: >-
  Generate 4-6 high-level parent tasks from a PRD and codebase assessment. No
  sub-tasks. Pauses for user confirmation before proceeding to Phase 2.
---

## Goal

Create high-level parent tasks from the PRD and repo assessment. This is
Phase 1 of the two-phase task planning process.

## Process

1. Synthesize the PRD analysis and codebase assessment.
2. Generate 4-6 parent tasks that cover the full PRD scope.
3. Order tasks by dependency (foundational tasks first).
4. Present in the task list format (NO sub-tasks).
5. End with the mandatory pause message.

## Rules

- Do NOT include sub-tasks in this phase.
- Keep scope aligned with the PRD -- no gold-plating.
- Create the task file as `tasks-[prd-file-name].md` in `/tasks/`.
- Use `- [ ] 1.0 Parent Task Title` format.
- Number parent tasks as `1.0`, `2.0`, `3.0`, etc.
- Typically 4-6 parent tasks, but use judgment.

## Mandatory Pause

After presenting parent tasks, you MUST say:

> "I have generated the high-level tasks based on the PRD. Ready to generate
> the sub-tasks? Respond with **'Go'** to proceed."

Then STOP and WAIT for the user's "Go" response. Do NOT generate sub-tasks
until confirmed.

## Output

4-6 parent tasks saved to `/tasks/tasks-[prd-file-name].md`, followed by a
pause waiting for the user to say "Go".
