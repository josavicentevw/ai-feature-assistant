---
name: codebase-assessment
description: >-
  Survey the repository for files, patterns, and conventions relevant to a PRD.
  Returns exact paths with short notes. Does not propose changes.
---

## Goal

Identify existing components, patterns, and files in the repository that are
relevant to the PRD being planned.

## Process

1. Review the repository structure (directories, key files, configs).
2. Identify files and components related to the PRD's requirements.
3. Note architectural patterns, naming conventions, and dependencies.
4. Look for existing utilities, helpers, or shared modules that could be
   leveraged.

## Rules

- Do NOT propose changes or implementations yet.
- Use EXACT existing paths only.
- Include notes on patterns and conventions that new code should follow.
- Note the test framework and test file conventions in use.

## Output

A list of relevant files/components with:
- Exact file paths.
- Short description of what each file does.
- Notes on patterns and conventions observed.
