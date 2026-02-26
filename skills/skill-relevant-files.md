# Skill: Relevant Files Identification

## Goal
List files likely to be created or modified to implement the plan.

## Inputs
- PRD.
- Task plan.

## Outputs
- `Relevant Files` section with exact paths and reasons.

## Mode
- autonomous

## Handoff
- Supplies the `Relevant Files` section to task planning.

## Rules
- Include likely test files.
- Use existing repo conventions.

## Recommended model
- gpt-5.2-codex

## Suggested prompt
"Identify repo files likely to be created or modified to implement the plan. Return a `Relevant Files` list with path and reason."
