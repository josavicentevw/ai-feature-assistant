# AI Feature Assistant

## Overview
This repository packages the prompt engineering playbooks used to run an AI-powered feature planning assistant. The goal is to help product teams go from a raw feature idea to a detailed implementation plan by guiding an AI through three repeatable workflows:

- Asking clarifying questions and drafting a Product Requirements Document (PRD).
- Translating the approved PRD into high-level and detailed engineering tasks.
- Managing progress on those tasks with a clear execution protocol.

These instructions are written for a junior developer or AI agent so that each step is explicit and easy to follow.

## Repository Contents
- `create-prd.md` — Rules for interviewing the requester, collecting missing context, drafting the PRD, and saving it to `/tasks/`.
- `generate-tasks.md` — Guidelines for turning a completed PRD into an actionable task list, including the mandated two-phase (parent tasks → sub-tasks) workflow.
- `process-task-list.md` — Execution rules for keeping task lists up to date while implementation is in progress, including when to run tests and how to commit changes.
- `agents.md` — Agent definitions aligned to the workflow stages.
- `skills/` — Skill definitions that translate the workflow into operational steps.

## Recommended Workflow
1. **Capture the feature idea.** Point the AI assistant to `create-prd.md` and provide the initial feature prompt. The assistant must ask clarifying questions before producing the PRD.
2. **Generate the PRD.** After the clarifications are answered, the assistant writes the PRD using the structure in `create-prd.md` and saves it under `/tasks/` with the required naming convention.
3. **Plan implementation tasks.** Reference `generate-tasks.md` with the PRD filename. The assistant reviews the repository, proposes high-level tasks, pauses for confirmation, then expands each task into sub-tasks and enumerates relevant files.
4. **Execute the plan.** During development, follow `process-task-list.md` to work through sub-tasks sequentially, update completion status, and run tests before marking parent tasks complete.

## Agent and Skill Mapping
- **PRD Interviewer Agent:** `skills/skill-prd-interview.md`
- **PRD Writer Agent:** `skills/skill-prd-drafting.md`
- **Task Planning Agent:** `skills/skill-task-planning-phase-1.md`, `skills/skill-task-planning-phase-2.md`, `skills/skill-relevant-files.md`
- **Task Execution Agent:** `skills/skill-subtask-execution.md`, `skills/skill-parent-task-closeout.md`
- **Task List Governance Agent:** `skills/skill-task-list-maintenance.md`
- **Model routing:** `skills/skill-model-routing.md`

## Skills Overview
This directory contains the operational skills that implement the workflow defined in the root rules (`create-prd.md`, `generate-tasks.md`, `process-task-list.md`). Each skill is a small, focused unit that maps to one workflow stage.

### Workflow Order

| Order | Skill | Mode |
| --- | --- | --- |
| 1 | `skills/skill-model-routing.md` | autonomous |
| 2 | `skills/skill-prd-interview.md` | supervised (waits for answers) |
| 3 | `skills/skill-prd-drafting.md` | autonomous |
| 4 | `skills/skill-prd-analysis.md` | autonomous |
| 5 | `skills/skill-codebase-assessment.md` | autonomous |
| 6 | `skills/skill-task-planning-phase-1.md` | supervised (waits for "Go") |
| 7 | `skills/skill-task-planning-phase-2.md` | autonomous |
| 8 | `skills/skill-subtask-execution.md` | supervised (waits for "yes"/"y") |
| 9 | `skills/skill-parent-task-closeout.md` | autonomous |
| 10 | `skills/skill-task-list-maintenance.md` | autonomous |

### Notes
- Skills are written to be used by agents defined in `agents.md`.
- The task planning skills enforce the two-phase "Go" confirmation step.
- The execution and closeout skills enforce the test and commit protocol.
- Hybrid mode keeps the three required pauses: answers, "Go", and per-sub-task approval.

## How to Use Agents and Skills
1. Start with the agent that matches your current stage (see mapping above).
2. Use the corresponding skill document as the operational checklist and prompt template.
3. Follow the rules in the skill file exactly, especially the "Go" confirmation step and closeout protocol.
4. Keep artifacts in `/tasks/` and update task lists after each sub-task.
5. If unsure which model to use, apply `skills/skill-model-routing.md`.

## Hybrid Mode (Autonomy)
Hybrid mode is the default. It runs autonomously except for three required human checkpoints:

- After PRD interview questions (waits for answers).
- After task planning phase 1 (waits for "Go").
- After each sub-task execution (waits for "yes"/"y").

All other stages run without pauses using the rules in each skill file.

## Tooling Notes
- Use the skill files as operational checklists and prompt templates.
- Use `/tasks/` for all generated artifacts (PRDs, task lists, interview notes).
- The task planning workflow enforces the two-phase parent tasks → sub-tasks flow.
- The execution workflow enforces test and commit rules before closing parent tasks.

## Examples

### Example: From Feature Idea to PRD
1. Start the **PRD Interviewer Agent** with `skills/skill-prd-interview.md`.
2. Ask clarifying questions and wait for answers.
3. Run the **PRD Writer Agent** with `skills/skill-prd-drafting.md` to produce `/tasks/0001-prd-<feature>.md`.

### Example: Generate Tasks from a PRD
1. Run **Task Planning Phase 1** with `skills/skill-task-planning-phase-1.md`.
2. Wait for user "Go".
3. Run **Task Planning Phase 2** with `skills/skill-task-planning-phase-2.md` and include `skills/skill-relevant-files.md`.
4. Save the final task list as `/tasks/tasks-0001-prd-<feature>.md`.
5. Always reference the relevant PRD when writing or updating tasks.

### Example: Execute a Sub-Task
1. Run **Sub-Task Execution** with `skills/skill-subtask-execution.md` for the next unchecked sub-task.
2. Update the task list and wait for "yes"/"y".
3. When all sub-tasks under a parent task are done, run **Parent Task Closeout** with `skills/skill-parent-task-closeout.md`.

## Usage Tips
- Keep all generated artifacts inside the `/tasks/` directory so history remains ordered and easy to track.
- When collaborating with a human teammate, share the generated PRD and task list early to confirm scope before development begins.
- Feel free to adapt the question prompts in `create-prd.md` to the specific product area, but preserve the requirement to ask clarifying questions before writing the PRD.

## Contributing
Improvements are welcome. When updating any of the rule files, describe the rationale and provide examples so downstream AI agents and developers can adopt the changes confidently.
