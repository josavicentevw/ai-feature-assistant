# Skills Overview

This directory contains the operational skills that implement the workflow defined in the root rules (`create-prd.md`, `generate-tasks.md`, `process-task-list.md`). Each skill is a small, focused unit that maps to one workflow stage.

## Workflow Order

1. **Model routing**
   - `skills/skill-model-routing.md`
2. **PRD interview**
   - `skills/skill-prd-interview.md`
3. **PRD drafting**
   - `skills/skill-prd-drafting.md`
4. **PRD analysis**
   - `skills/skill-prd-analysis.md`
5. **Codebase assessment**
   - `skills/skill-codebase-assessment.md`
6. **Task planning phase 1 (parent tasks)**
   - `skills/skill-task-planning-phase-1.md`
7. **Task planning phase 2 (sub-tasks + relevant files)**
   - `skills/skill-task-planning-phase-2.md`
8. **Sub-task execution**
   - `skills/skill-subtask-execution.md`
9. **Parent task closeout**
   - `skills/skill-parent-task-closeout.md`
10. **Task list maintenance**
   - `skills/skill-task-list-maintenance.md`

## Notes

- Skills are written to be used by agents defined in `agents.md`.
- The task planning skills enforce the two-phase "Go" confirmation step.
- The execution and closeout skills enforce the test and commit protocol.
