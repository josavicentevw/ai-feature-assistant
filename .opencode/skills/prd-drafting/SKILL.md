---
name: prd-drafting
description: >-
  Write a complete PRD from the feature prompt and user answers using the
  required section structure and naming convention. Must only be used AFTER the
  prd-interview skill has been completed.
---

## Goal

Write a complete PRD from the initial prompt and the user's interview answers.

## Pre-condition

This skill MUST only be used after the user has answered clarifying questions
from the `prd-interview` skill. If interview answers are not available, refuse
to draft and instruct the caller to complete the interview first.

## Required Sections

The PRD must include all of these sections:

1. **Introduction/Overview** -- Briefly describe the feature and the problem it
   solves. State the goal.
2. **Goals** -- List specific, measurable objectives for this feature.
3. **User Stories** -- Detail user narratives describing feature usage and
   benefits.
4. **Functional Requirements** -- List specific functionalities the feature
   must have. Use clear, concise language. NUMBER these requirements.
5. **Non-Goals (Out of Scope)** -- Clearly state what this feature will NOT
   include to manage scope.
6. **Design Considerations** (optional) -- Link to mockups, describe UI/UX
   requirements, or mention relevant components/styles.
7. **Technical Considerations** (optional) -- Mention known technical
   constraints, dependencies, or suggestions.
8. **Success Metrics** -- How will success be measured?
9. **Open Questions** -- List remaining questions or areas needing
   clarification.

## Rules

- Number ALL functional requirements.
- Write for a junior developer: explicit, unambiguous, no jargon.
- Short sentences. No ambiguity.
- Do NOT implement the PRD.
- Save as `/tasks/[n]-prd-[feature-name].md` where `[n]` is a 4-digit
  zero-padded sequence starting from 0001.

## Naming Convention

- Check `/tasks/` for existing PRD files to determine the next sequence number.
- Format: `0001-prd-user-authentication.md`, `0002-prd-dashboard.md`, etc.
- The `[feature-name]` should be a short, hyphenated slug.

## Output

A Markdown PRD file saved to `/tasks/` following the naming convention.
