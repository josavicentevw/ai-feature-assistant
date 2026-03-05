---
name: prd-interview
description: >-
  Operational checklist for gathering context before drafting a PRD. Ensures
  mandatory clarifying questions are asked covering problem, users, scope,
  acceptance criteria, data, design, and edge cases. MUST be completed before
  any PRD is written.
---

## Goal

Gather enough context through clarifying questions BEFORE drafting a PRD. This
skill enforces the mandatory interview step that cannot be skipped.

## CRITICAL RULE

The interview MUST happen before any PRD is drafted. If the user has not
answered clarifying questions, the PRD CANNOT be written. There are no
exceptions to this rule.

## Checklist

Ask clarifying questions covering EVERY area below. Use numbered options for
quick user responses. Do not skip any area.

1. **Problem/Goal**
   - "What problem does this feature solve for the user?"
   - "What is the main goal we want to achieve with this feature?"
   - Options: a) Solve [specific problem], b) Improve [metric], c) Enable
     [capability], d) Other (please describe)

2. **Target User**
   - "Who is the primary user of this feature?"
   - Options: a) End users, b) Administrators, c) Developers, d) All users,
     e) Other (please specify)

3. **Core Actions**
   - "What key actions should a user be able to perform with this feature?"
   - List 3-5 potential actions based on the prompt and ask the user to
     confirm, remove, or add.

4. **User Stories**
   - "Can you provide user stories?"
   - Format: "As a [type of user], I want to [perform an action] so that
     [benefit]."
   - Suggest 2-3 stories based on the prompt and ask the user to refine.

5. **Acceptance Criteria**
   - "How will we know when this feature is successfully implemented?"
   - "What are the key success criteria?"

6. **Scope/Non-Goals**
   - "Are there specific things this feature should NOT do?"
   - Suggest likely non-goals based on the prompt and ask the user to confirm.

7. **Data Requirements**
   - "What kind of data does this feature need to display or manipulate?"
   - Options: a) User-generated content, b) System data, c) External API data,
     d) Configuration data, e) Other

8. **Design/UI**
   - "Are there existing design mockups or UI guidelines to follow?"
   - "Can you describe the desired look and feel?"
   - Options: a) Follow existing design system, b) New design needed,
     c) Minimal/functional UI, d) Reference provided

9. **Edge Cases**
   - "What potential edge cases or error conditions should we consider?"
   - Suggest 2-3 likely edge cases and ask the user to confirm or add more.

## Rules

- Ask BEFORE writing. NEVER draft without user answers.
- Focus on WHAT and WHY, not HOW.
- Order questions by scope impact (broadest first).
- Provide lettered or numbered options for every question.
- Wait for the user to answer ALL questions before proceeding.

## Output

A complete list of clarifying questions with enumerated options, ready for the
user to respond. After answers are received, hand off to the `prd-drafting`
skill.
