# Skill: PRD Analysis

## Goal
Extract requirements, stories, criteria, and risks from an existing PRD.

## Inputs
- PRD file path in `/tasks/`.

## Outputs
- Summary of functional requirements.
- Summary of user stories.
- Success metrics and open questions.
- List of ambiguities or risks.

## Rules
- Do not propose implementations.
- Preserve the PRD's language and intent.
- Call out missing sections if any.

## Recommended model
- gpt-5.2-codex

## Suggested prompt
"Analyze the PRD at the given path. Return: (1) numbered functional requirements, (2) user stories summary, (3) success metrics and open questions, (4) ambiguities or risks. Do not propose technical solutions."
