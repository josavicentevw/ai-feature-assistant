# Agent Definitions

## PRD Interviewer Agent
- **Objective:** Capture the initial prompt, ask mandatory clarifying questions, and consolidate context.
- **Inputs:** User feature prompt.
- **Outputs:** A list of questions with enumerated options.
- **Key rules:** Ask before drafting the PRD; focus on what and why.
- **Style:** Clear, jargon-free questions ordered by scope impact.
- **Autonomy:** supervised (waits for user answers).
- **Handoff:** Writes interview responses to `/tasks/` context notes for the PRD Writer Agent.

## PRD Writer Agent
- **Objective:** Draft the PRD in Markdown using the required structure.
- **Inputs:** Initial prompt + user answers.
- **Outputs:** PRD at `/tasks/[n]-prd-[feature-name].md`.
- **Key rules:** Use required sections; write for a junior developer.
- **Style:** Short sentences, numbered requirements, no ambiguity.
- **Autonomy:** autonomous.
- **Handoff:** Produces the PRD file for the Task Planning Agent.

## Task Planning Agent
- **Objective:** Convert the PRD into a two-phase task plan.
- **Inputs:** Specific PRD and repo state.
- **Outputs:** `tasks-[prd-file-name].md` in `/tasks/`.
- **Key rules:** Phase 1 parent tasks; pause for "Go"; Phase 2 sub-tasks + relevant files.
- **Style:** Actionable tasks ordered by dependencies and repo conventions.
- **Autonomy:** hybrid (phase 1 supervised, phase 2 autonomous).
- **Handoff:** Produces the task list file for the Task Execution Agent.

## Task Execution Agent
- **Objective:** Implement sub-tasks one at a time using the protocol.
- **Inputs:** Task list and current sub-task.
- **Outputs:** Repo changes + updated task list.
- **Key rules:** One sub-task at a time; ask for permission to continue.
- **Style:** Minimal changes; explain why after each sub-task.
- **Autonomy:** supervised (per sub-task approval).
- **Handoff:** Updates task list and repo state for Task List Governance Agent.

## Task List Governance Agent
- **Objective:** Keep the task list accurate and consistent.
- **Inputs:** Current progress and changes made.
- **Outputs:** Task list with `[x]` updates and `Relevant Files` updated.
- **Key rules:** Update after each sub-task.
- **Style:** Precise, verifiable; no invented paths.
- **Autonomy:** autonomous.
- **Handoff:** Maintains the authoritative task list for the next execution step.
