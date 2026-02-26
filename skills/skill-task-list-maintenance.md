# Skill: Task List Maintenance

## Goal
Keep the task list and relevant files accurate throughout execution.

## Inputs
- Current task list.
- Implementation progress.

## Outputs
- Updated task list with completed items marked.
- Updated `Relevant Files` section.

## Mode
- autonomous

## Handoff
- Maintains authoritative task list for the next execution step.

## Rules
- Mark each sub-task `[x]` immediately when finished.
- Mark parent tasks only after all sub-tasks and closeout protocol complete.
- Add new tasks as they emerge.
- Do not invent paths.

## Recommended model
- gpt-5.2-codex

## Suggested prompt
"Update the task list to reflect completed sub-tasks and keep `Relevant Files` accurate. Do not invent paths."
