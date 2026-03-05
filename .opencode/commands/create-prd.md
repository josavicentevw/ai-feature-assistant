---
description: Start the PRD creation workflow -- interview then draft
agent: prd-interviewer
---

Start the PRD creation workflow for the following feature:

$ARGUMENTS

Follow this process exactly:

1. Load the `prd-interview` skill.
2. Ask clarifying questions covering ALL nine required topics (problem/goal,
   target user, core actions, user stories, acceptance criteria, scope/non-goals,
   data requirements, design/UI, edge cases). Use numbered options for each.
3. STOP and WAIT for my answers. Do NOT draft anything yet.
4. Once I have answered all questions, load the `prd-drafting` skill.
5. Draft the PRD incorporating my answers into all required sections.
6. Save it to `/tasks/` with the naming convention `[n]-prd-[feature-name].md`.
7. Do NOT implement the PRD.

CRITICAL: You MUST ask clarifying questions BEFORE writing the PRD. This step
is mandatory and cannot be skipped.
