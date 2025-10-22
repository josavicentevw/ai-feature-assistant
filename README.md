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

## Recommended Workflow
1. **Capture the feature idea.** Point the AI assistant to `create-prd.md` and provide the initial feature prompt. The assistant must ask clarifying questions before producing the PRD.
2. **Generate the PRD.** After the clarifications are answered, the assistant writes the PRD using the structure in `create-prd.md` and saves it under `/tasks/` with the required naming convention.
3. **Plan implementation tasks.** Reference `generate-tasks.md` with the PRD filename. The assistant reviews the repository, proposes high-level tasks, pauses for confirmation, then expands each task into sub-tasks and enumerates relevant files.
4. **Execute the plan.** During development, follow `process-task-list.md` to work through sub-tasks sequentially, update completion status, and run tests before marking parent tasks complete.

## Usage Tips
- Keep all generated artifacts inside the `/tasks/` directory so history remains ordered and easy to track.
- When collaborating with a human teammate, share the generated PRD and task list early to confirm scope before development begins.
- Feel free to adapt the question prompts in `create-prd.md` to the specific product area, but preserve the requirement to ask clarifying questions before writing the PRD.

## Contributing
Improvements are welcome. When updating any of the rule files, describe the rationale and provide examples so downstream AI agents and developers can adopt the changes confidently.
