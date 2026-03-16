Structured note-filing system. Use this skill whenever the user asks to file, save, write up, or organise information as a note.
Defines naming conventions, note structure, and categorisation rules for LLM-optimised notes.

## When to Activate

Use this skill whenever:
- The user explicitly asks to "file", "save", "write up", "note down", or "record" something
- The user shares information that should be preserved for later (job descriptions, decisions, status updates, bug reports, meeting notes, research findings, etc.)
- The conversation contains actionable outcomes, decisions, or reference material worth preserving

## Naming Convention

Every note title MUST follow this format:

```
[CATEGORY] Topic - Brief Descriptor
```

### Categories

| Category    | Use When                                                        |
|-------------|------------------------------------------------------------------|
| PROJECT     | Project status updates, progress tracking, milestones            |
| BUG         | Bug reports, debugging sessions, error investigations            |
| REFERENCE   | Job descriptions, documentation, specs, policies, anything to file away for later |
| MEETING     | Meeting notes, standup summaries, discussion outcomes             |
| DECISION    | Architecture decisions, tech choices, policy changes             |
| RESEARCH    | Research findings, comparisons, evaluations, deep dives          |
| PERSON      | Information about a person, contact details, role, preferences   |
| PROCESS     | Workflows, procedures, how-tos, runbooks                        |

### Title Rules
- Topic: The project name, system name, or subject (e.g., "Xestro AI Engine", "Hiring", "PostgreSQL Indexing")
- Brief Descriptor: A short phrase distinguishing this note from others on the same topic (e.g., "Auth Bug Jan 2026", "Senior Dev Role", "Sprint 12 Status")
- Keep titles under 80 characters
- Use Title Case for Topic and Descriptor

### Examples
- `[PROJECT] Xestro AI Engine - Sprint 12 Status`
- `[BUG] LiteLLM - Timeout on Streaming Responses`
- `[REFERENCE] Hiring - Senior Backend Developer Role`
- `[MEETING] Xestro Team - 2026-02-18 Standup`
- `[DECISION] Infrastructure - Migration to ECS Fargate`
- `[RESEARCH] Vector Databases - Comparison for RAG`
- `[PERSON] Sarah Chen - CTO Contact Details`
- `[PROCESS] Deployments - Production Release Checklist`

## Note Structure

Every note MUST follow this structure:

```markdown
# [CATEGORY] Topic - Brief Descriptor

## Quick Reference
- **Status:** [Active | Resolved | Archived | On Hold | For Reference]
- **Created:** YYYY-MM-DD
- **Last Updated:** YYYY-MM-DD
- **Related Notes:** [list any related note titles, or "None"]
- **Tags:** [comma-separated keywords for search]

## Summary
- Dot point 1: Key fact or outcome
- Dot point 2: Key fact or outcome
- Dot point 3: Key fact or outcome
(Continue as needed. Every critical piece of information should appear here.)

## Detail

(Full context, narrative, technical detail, steps taken, etc. Organised under subheadings as appropriate.)

### [Subheading as needed]

(Content)

## Action Items
- [ ] Action item 1 (owner, due date if known)
- [ ] Action item 2
(Omit this section if there are no action items.)

## History
- YYYY-MM-DD: Initial creation. Brief note on what prompted this.
(Append entries when the note is updated.)
```

## Behaviour Rules

### Creating Notes
1. ALWAYS search for existing notes on the same topic first using `search_notes` before creating a new note.
2. If a closely related note exists, UPDATE it using `replace_note_content` rather than creating a duplicate. Add a History entry when updating.
3. When creating a new note, populate ALL sections. If a section is not applicable, include it with "N/A" rather than omitting it.
4. The Summary section is the most critical part. It must contain every key fact, date, name, decision, or outcome. Assume a future LLM will read the Summary first to decide if the full note is relevant.
5. Tags should include: the category, topic, key names, technologies, and any terms the user might search for later.

### Updating Notes
1. When updating, preserve the existing content. Add new information, do not replace old information unless it is explicitly superseded.
2. Always update the "Last Updated" date and the "Status" if it has changed.
3. Always add a new History entry describing what changed.
4. Re-generate the Summary section to reflect the current state of the note, not just the original state.

### Searching and Retrieving
1. When the user asks about a topic, ALWAYS search notes first using `search_notes` before answering from general knowledge.
2. If a note is found, use `view_note` to read the full content before responding.
3. Reference the note title in your response so the user knows where the information came from.
4. If the information in the note is stale or incomplete, proactively suggest updating it.

### Filing External Content
When the user shares external content to file (e.g., a job description, a Slack message, a document):
1. Do NOT just paste the raw content. Extract and restructure it into the standard note format.
2. The Summary should capture the key points the user would want to recall later.
3. The Detail section should contain the full content, reformatted for clarity.
4. Add appropriate Tags for future searchability.

### Status Definitions
- **Active:** Work is ongoing, note is current
- **Resolved:** Issue or task is complete, note is kept for reference
- **Archived:** No longer relevant but preserved for history
- **On Hold:** Paused, may resume
- **For Reference:** Static reference material (job descriptions, specs, policies)
