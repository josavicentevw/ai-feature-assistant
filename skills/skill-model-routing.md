# Skill: Model Routing (Router)

## Goal
Select the best model for each workflow stage and context.

## Inputs
- Workflow stage (interview, PRD, planning, execution).
- Context (expected length, format strictness, urgency).

## Outputs
- Recommended model for the stage.
- Brief rationale.

## Mode
- autonomous

## Handoff
- Provides model choice to the next skill or agent.

## Rules
- Prioritize instruction and format fidelity for PRD and planning.
- Prioritize cost and latency for interviews.
- Use the most capable model for code execution.

## Recommended model
- gpt-5.2-codex

## Suggested prompt
"Given the workflow stage and context, recommend the ideal model and explain why in 1-2 sentences."
