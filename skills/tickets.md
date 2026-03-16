When the user asks you to draft, write, or create a GitLab issue or ticket, follow this system precisely.

## When to Activate

Use this skill whenever:
- The user asks to "draft", "write", "create", or "generate" a GitLab issue or ticket
- The user describes work that needs to be done and wants it formatted as an issue
- The user provides requirements, tasks, or feature descriptions intended for their team's backlog

## Output Rules

1. Output ONLY the Markdown issue content, ready to copy-paste directly into GitLab.
2. Do NOT wrap the output in a code block or add any preamble/commentary.
3. Keep the language concise and direct. No filler, no fluff.
4. Use dot points as the primary structure. Full sentences only where necessary for context.
5. Do NOT include sections like Acceptance Criteria, Definition of Done, Story Points, or Priority unless the user explicitly asks for them.
6. Do NOT invent requirements. If something is ambiguous, ask the user before including it.
7. Do NOT include implementation details, technical suggestions, or architectural guidance. The purpose of the ticket is to capture what needs to be done, not how. An engineer will determine the implementation. Only include technical detail if the user explicitly provides it or asks for it.

## Issue Structure

Every issue MUST follow this format:

```
# <Title>

<1-2 sentence description of what this ticket is about and why it matters. Keep it brief.>

## Requirements

- Requirement 1
- Requirement 2
  - Sub-detail if needed
  - Sub-detail if needed
- Requirement 3

## References

- Links to related issues, docs, designs, or discussions
```

### Section Rules

| Section      | Required | Notes                                                                 |
|--------------|----------|-----------------------------------------------------------------------|
| Title        | Yes      | Clear, action-oriented. Prefix with area if useful (e.g., `[Auth]`). |
| Description  | Yes      | 1-2 sentences max. The "what" and "why".                              |
| Requirements | Yes      | Core of the ticket. Dot points only.                                  |
| References   | No       | Include only if the user provides links or references.                |

### Writing Style

- Start dot points with a verb where possible (e.g., "Add", "Update", "Remove", "Ensure")
- Keep each dot point to a single concern
- Use sub-points for detail, not for separate requirements
- Avoid jargon unless it is specific to the user's project and they have used it themselves
- Do not repeat information across sections
- If the user provides vague requirements, ask clarifying questions rather than guessing

## Examples

### Simple Feature

# Add date range filter to reports

Allow users to filter report data by a custom date range rather than being limited to preset options.

## Requirements

- Add a date range picker to the reports toolbar
- Support custom start and end date selection
- Default range: last 30 days
- Update all report queries to respect the selected range
- Persist the selected range across page navigation within the reports section

### Bug Fix

# Fix timeout on large dataset exports

Export endpoint times out when the dataset exceeds ~50k rows, returning a 504 to the client.

## Requirements

- Investigate and resolve the timeout on `/api/v1/exports` for large datasets
- Ensure exports of up to 200k rows complete successfully
- Add progress feedback if the export is long-running
