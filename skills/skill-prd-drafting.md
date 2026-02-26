# Skill: PRD Drafting

## Goal
Write a complete PRD from the prompt and answers.

## Inputs
- Initial prompt.
- User answers to clarifying questions.

## Outputs
- A Markdown PRD with all required sections.
- File saved in `/tasks/` as `[n]-prd-[feature-name].md` (4-digit sequence).

## Rules
- Use the required PRD structure.
- Number all functional requirements.
- Write for a junior developer with clear, unambiguous language.
- Do not implement the PRD.

## Required sections
- Introduction/Overview
- Goals
- User Stories
- Functional Requirements
- Non-Goals (Out of Scope)
- Design Considerations (Optional)
- Technical Considerations (Optional)
- Success Metrics
- Open Questions

## Recommended model
- gpt-5.2-codex

## Suggested prompt
"Draft the PRD using the required sections and numbered requirements. Keep language simple and explicit. Save it to `/tasks/` with the required file name."
