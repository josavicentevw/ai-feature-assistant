---
description: Generate a task list from a PRD file
agent: task-planner
---

Generate a task list from the PRD at: $ARGUMENTS

Follow this process exactly:

1. Load the `prd-analysis` skill and analyze the PRD file.
2. Load the `codebase-assessment` skill and survey the repository for relevant
   patterns, components, and conventions.
3. Load the `task-planning-phase-1` skill.
4. Generate 4-6 high-level parent tasks (NO sub-tasks yet).
5. Present them to me and say: "Respond with 'Go' to proceed."
6. STOP and WAIT for me to say "Go".
7. After I say "Go", load the `task-planning-phase-2` and `relevant-files` skills.
8. Expand each parent task into detailed sub-tasks.
9. Assemble the final task list with Relevant Files and Notes sections.
10. Save to `/tasks/tasks-[prd-file-name].md`.
