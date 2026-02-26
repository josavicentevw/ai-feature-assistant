# Skill: Parent Task Closeout Protocol

## Goal
Close a parent task following the testing and commit protocol.

## Inputs
- All sub-tasks completed.
- Repo state.

## Outputs
- Full test suite executed.
- Commit created with conventional format.
- Parent task marked completed.

## Mode
- autonomous

## Handoff
- Confirms parent task completion for governance.

## Rules
- Run the full test suite before committing.
- If tests fail, stop and report.
- Stage changes with `git add .` only after tests pass.
- Remove temporary code/files before committing.
- Commit message must use conventional format and multiple `-m` lines, referencing the task and PRD.

## Recommended model
- gpt-5.2-codex

## Suggested prompt
"Once all sub-tasks are complete, run the full test suite, stage changes, remove temp artifacts, commit with conventional format and multiple -m lines, and mark the parent task complete."
