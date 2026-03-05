---
name: prd-analysis
description: >-
  Extract functional requirements, user stories, success criteria, and risks
  from an existing PRD. Does not propose implementations.
---

## Goal

Extract requirements, stories, criteria, and risks from an existing PRD to
inform task planning.

## Process

1. Read the PRD at the specified path in `/tasks/`.
2. Extract and return:
   - **Numbered functional requirements** -- preserve the PRD's numbering.
   - **User stories summary** -- condensed list of all user stories.
   - **Success metrics and open questions** -- as stated in the PRD.
   - **Ambiguities or risks** -- anything unclear, contradictory, or missing.

## Rules

- Do NOT propose implementations or technical solutions.
- Preserve the PRD's language and intent.
- Call out missing sections explicitly if any required section is absent.
- Flag any functional requirements that are vague or testable only subjectively.

## Output

A structured analysis of the PRD with four clearly labeled sections, ready
for consumption by the task planning skills.
