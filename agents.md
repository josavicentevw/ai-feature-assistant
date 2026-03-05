# AI Feature Assistant

## Overview
This project uses a structured workflow to go from feature ideas to implemented
code. The workflow has three stages with three mandatory human checkpoints.

## Workflow Stages
1. **PRD Creation** -- Interview the user (ALWAYS ask clarifying questions
   first), then draft a Product Requirements Document.
2. **Task Planning** -- Analyze PRD, generate parent tasks (pause for "Go"),
   then expand into sub-tasks.
3. **Task Execution** -- Implement one sub-task at a time (pause per sub-task
   for user approval).

## Mandatory Human Checkpoints
These checkpoints are non-negotiable. The agent MUST stop and wait.

1. **After PRD interview questions** -- Wait for the user to answer every
   clarifying question before drafting the PRD. NEVER skip this step.
2. **After task planning phase 1** -- Present parent tasks and wait for the
   user to say "Go" before generating sub-tasks.
3. **After each sub-task execution** -- Wait for the user to say "yes" or "y"
   before proceeding to the next sub-task.

## Artifact Conventions
- PRD files: `/tasks/[n]-prd-[feature-name].md` (n = 4-digit zero-padded
  sequence starting from 0001)
- Task lists: `/tasks/tasks-[prd-file-name].md`
- All generated artifacts go in `/tasks/`

## Agent-Skill Mapping

| Agent | Skills Used |
|-------|-------------|
| prd-interviewer | `prd-interview`, `prd-drafting` |
| prd-writer | `prd-drafting` |
| task-planner | `prd-analysis`, `codebase-assessment`, `task-planning-phase-1`, `task-planning-phase-2`, `relevant-files` |
| task-executor | `subtask-execution`, `parent-task-closeout` |
| task-governance | `task-list-maintenance` |

## Commit Protocol
When all sub-tasks under a parent task are complete:
1. Run full test suite.
2. Only if tests pass: stage changes (`git add .`).
3. Remove temporary files and temporary code.
4. Commit with conventional format using multiple `-m` flags.
5. Reference the task number and PRD context in the commit message.

## Critical Rule: PRD Interview
The PRD Interviewer agent MUST ALWAYS ask clarifying questions before drafting
a PRD. This rule cannot be bypassed. The agent must cover:
- Problem/Goal
- Target User
- Core Actions
- User Stories
- Acceptance Criteria
- Scope/Non-Goals
- Data Requirements
- Design/UI
- Edge Cases

Questions must use numbered or lettered options for quick user responses.

## Quick Start Commands
- `/create-prd <feature idea>` -- Start the PRD workflow
- `/generate-tasks <prd-file>` -- Generate tasks from a PRD
- `/process-tasks <task-list-file>` -- Begin executing tasks

## External File Loading
When working on PRD creation or task planning, load the relevant skill using
the `skill` tool. Skills contain the operational checklists for each stage.
