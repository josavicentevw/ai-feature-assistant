# Skill: Task Planning Phase 1 (Parent Tasks)

## Goal
Create high-level parent tasks from the PRD and repo assessment.

## Inputs
- PRD.
- Codebase assessment.

## Outputs
- 4-6 parent tasks in the task list format (no sub-tasks yet).
- A pause message: "I have generated the high-level tasks... Respond with 'Go' to proceed."

## Mode
- supervised (waits for "Go").

## Handoff
- Captures approved parent tasks for phase 2.

## Rules
- Do not include sub-tasks in this phase.
- Keep scope aligned with the PRD.
- Name the task file `tasks-[prd-file-name].md` in `/tasks/`.

## Recommended model
- gpt-5.2-codex

## Suggested prompt
"Generate parent tasks only. No sub-tasks. End with a pause asking the user to respond with 'Go' to proceed."
