---
description: Begin executing tasks from a task list file
agent: task-executor
---

Begin executing tasks from: $ARGUMENTS

Follow this process exactly:

1. Read the task list file specified above.
2. Find the next unchecked sub-task (`[ ]`).
3. Load the `subtask-execution` skill.
4. Implement ONLY that one sub-task.
5. Mark it `[x]` in the task list file.
6. Update the Relevant Files section if needed.
7. Explain what changed and why.
8. STOP and ask: "Sub-task complete. Ready for the next one? (yes/y)"
9. Wait for my approval before proceeding to the next sub-task.
10. When ALL sub-tasks under a parent task are done, load the
    `parent-task-closeout` skill and follow the closeout protocol
    (test, stage, clean up, commit, mark parent complete).
