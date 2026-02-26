# Skills Overview

This directory contains the operational skills that implement the workflow defined in the root rules (`create-prd.md`, `generate-tasks.md`, `process-task-list.md`). Each skill is a small, focused unit that maps to one workflow stage.

## Workflow Order

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

## Notes

- Skills are written to be used by agents defined in `agents.md`.
- The task planning skills enforce the two-phase "Go" confirmation step.
- The execution and closeout skills enforce the test and commit protocol.
- Hybrid mode keeps the three required pauses: answers, "Go", and per-sub-task approval.
