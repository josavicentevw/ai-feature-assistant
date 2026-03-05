---
name: parent-task-closeout
description: >-
  Closeout protocol for a parent task. Run full test suite, stage changes only
  if tests pass, clean up temp artifacts, commit with conventional format, and
  mark the parent task complete.
---

## Goal

Close a parent task following the mandatory testing and commit protocol.

## Pre-condition

ALL sub-tasks under the parent task must be marked `[x]` before this protocol
can begin. If any sub-task is still `[ ]`, refuse to proceed.

## Protocol (strict order -- no steps may be skipped)

1. **Verify** -- Confirm all sub-tasks under the parent are `[x]`.
2. **Test** -- Run the full test suite (`pytest`, `npm test`, `bin/rails test`,
   or whatever the project uses).
3. **If tests FAIL** -- STOP immediately. Report the failures. Do NOT stage,
   commit, or mark the parent complete. The failures must be fixed first.
4. **If tests PASS** -- Stage all changes with `git add .`.
5. **Clean up** -- Remove any temporary files, debug code, or scaffolding
   that should not be committed.
6. **Commit** -- Use conventional commit format with multiple `-m` flags:
   ```
   git commit -m "feat: summary of parent task" \
     -m "- Key change 1" \
     -m "- Key change 2" \
     -m "Related to T[n] in [prd-file]"
   ```
   Use the appropriate prefix: `feat:`, `fix:`, `refactor:`, `test:`,
   `docs:`, `chore:`, etc.
7. **Mark complete** -- Mark the parent task `[x]` in the task list file.

## Rules

- NEVER commit if tests fail.
- NEVER skip the test step.
- NEVER mark the parent complete without a successful commit.
- Use conventional commit format.
- Reference the task number and PRD context in the commit message.
- Remove ALL temporary artifacts before committing.

## Output

- Test suite results.
- Git commit with conventional message.
- Parent task marked `[x]` in the task list.
