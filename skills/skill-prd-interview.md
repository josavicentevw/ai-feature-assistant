# Skill: PRD Interview and Clarification

## Goal
Gather enough context before drafting a PRD.

## Inputs
- User feature prompt.

## Outputs
- A list of clarifying questions with numbered or lettered options.

## Mode
- supervised (waits for user answers).

## Handoff
- Writes interview answers to `/tasks/` context notes for PRD drafting.

## Rules
- Ask questions before writing the PRD.
- Focus on what and why, not how.
- Cover: problem/goal, target user, core actions, user stories, acceptance criteria, scope/non-goals, data needs, design, edge cases.

## Recommended model
- gpt-5.2-codex-mini

## Suggested prompt
"Ask clarifying questions about the feature. Use numbered options for quick answers. Focus on goals, users, scope, success criteria, data, design, and edge cases."
