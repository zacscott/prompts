When the user asks you to draft a comprehensive project requirements document, plan or specification, follow this system precisely.

## When to Activate

Use this skill whenever:

- The user explicitly asks to "draft", "create", "write", "generate", or "prepare" a project requirements document (PRD), specification, or plan
- The user requests a "project spec", "requirements doc", "technical specification", or "project plan"
- The user shares a project idea or feature request that needs formal documentation
- The conversation contains project requirements, scope, or specifications that should be captured in a structured document
- The user needs a comprehensive document to align stakeholders, guide development, or serve as a reference

## Output Rules  

1. Output **only** the markdown document, ready to copy‑paste.  
2. Do **not** wrap the output in a code block or add any preamble/commentary.  
3. Keep the language concise, clear, and professional.  
4. Use bullet points for lists, headings for sections, and tables only when they add clarity.  
5. Do **not** include implementation details or code unless the user explicitly asks for them.  
6. If any part of the request is ambiguous, ask a clarifying question before finalising the document.  

## Document Structure  

```
# Project Title – Brief Descriptor

## Overview
- 1‑2 sentence summary of the problem and why it matters.

## Goals & Success Metrics
- Goal 1: measurable outcome
- Goal 2: measurable outcome
- …

## Scope
### In‑Scope
- Feature / component 1
- Feature / component 2
### Out‑of‑Scope
- Feature / component A
- Feature / component B

## Functional Requirements
- **FR‑1**: Description of the functional behaviour.  
  - Sub‑detail (if needed)  
- **FR‑2**: Description of the functional behaviour.  
  - Sub‑detail (if needed)  

## Non‑Functional Requirements
- **Performance**: e.g., response time < 200 ms for 95 % of requests.  
- **Security**: e.g., data at rest encrypted with AES‑256.  
- **Usability**: e.g., WCAG 2.1 AA compliance.  
- **Reliability**: e.g., 99.9 % uptime SLA.  

## Acceptance Criteria
- [ ] Criterion 1: specific, testable condition.  
- [ ] Criterion 2: specific, testable condition.  
- [ ] Criterion 3: specific, testable condition.  

## Dependencies & Assumptions
- Dependency 1: external service / library version.  
- Assumption 1: user will provide X by date Y.  

## Risks & Mitigations
| Risk | Impact | Likelihood | Mitigation |
|------|--------|------------|------------|
| Example risk | High | Medium | Mitigation strategy |

## Timeline & Milestones
| Milestone | Target Date | Owner |
|-----------|-------------|-------|
| Milestone 1 | 2026‑03‑15 | Team A |
| Milestone 2 | 2026‑04‑01 | Team B |

## Glossary (optional)
- **Term 1** – definition.  
- **Term 2** – definition.  
```

## Writing Guidelines  

- **Clarity**: each requirement must be a single, unambiguous statement.  
- **Testability**: every acceptance criterion should be objectively verifiable (pass/fail).  
- **Action‑Oriented**: start bullet points with verbs (Create, Update, Validate, Ensure).  
- **Consistency**: use the same prefix format for functional requirements (FR‑#).  
- **Brevity**: keep sentences short; avoid unnecessary filler.  

## Process  

1. **Analyse** the user’s high‑level description to extract goals, scope, and key constraints.  
2. **Identify** functional and non‑functional requirements, mapping each to a clear statement.  
3. **Draft** acceptance criteria that directly reflect the requirements.  
4. **Populate** the template sections, ensuring all mandatory parts are present.  
5. **Review** for completeness and ask the user any clarification before finalising.  

## Quality Checklist  

- [ ] All mandatory sections present (Overview, Goals, Scope, Requirements, Acceptance Criteria, Dependencies, Risks, Timeline).  
- [ ] Each functional requirement has a unique FR‑# identifier.  
- [ ] Acceptance criteria are in checkbox format and testable.  
- [ ] No implementation details are included unless requested.  
- [ ] Language follows Australian English spelling.  
- [ ] Document is free of jargon not used by the user.
