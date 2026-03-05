---
name: relevant-files
description: >-
  Identify repository files likely to be created or modified to implement the
  task plan. Includes test file paths with one-line descriptions.
---

## Goal

List files likely to be created or modified to implement the plan.

## Process

1. Review the task plan and PRD requirements.
2. Identify existing files that will need modification.
3. Identify new files that will need to be created.
4. Include corresponding test files for each source file.

## Rules

- Include likely test files alongside source files.
- Use existing repo conventions for file placement and naming.
- Use EXACT paths only -- never invent or guess paths for existing files.
- For new files, follow the project's directory structure conventions.
- Provide a one-line description explaining why each file is relevant.

## Output Format

```markdown
## Relevant Files

- `path/to/existing/file.ts` - Needs modification for [reason].
- `path/to/new/file.ts` - New file for [purpose].
- `path/to/new/file.test.ts` - Unit tests for `file.ts`.
```
