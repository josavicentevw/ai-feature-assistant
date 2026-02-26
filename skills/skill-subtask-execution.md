# Skill: Sub-Task Execution

## Goal
Implement a single sub-task and update the task list.

## Inputs
- Task list and current sub-task.

## Outputs
- Code changes in the repo.
- Task list updated with the sub-task marked `[x]`.

## Mode
- supervised (waits for "yes"/"y" per sub-task).

## Handoff
- Updates repo state and task list for governance.

## Rules
- One sub-task at a time.
- Ask for user permission before starting the next sub-task ("yes" or "y").
- Stop after each sub-task and wait for approval.
- Update the task list immediately after the sub-task.
- Explain the change briefly.

## Recommended model
- gpt-5.2-codex

## Suggested prompt
"Implement only the current sub-task. Update the task list and stop to ask for permission before the next sub-task."
