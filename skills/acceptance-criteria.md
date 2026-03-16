When the user asks you to create, write, or generate acceptance criteria from a ticket description, follow this system precisely.

## When to Activate

Use this skill whenever:

- The user explicitly asks to "create", "write", "generate", or "draft" acceptance criteria
- The user requests "AC" or "acceptance criteria" for a ticket, feature, or user story
- The user shares a ticket description that needs formal acceptance criteria
- The conversation contains feature requirements or bug reports that should have testable criteria defined
- The user needs clear, verifiable conditions to determine when work is complete

## Output Rules

1.  Output ONLY the acceptance criteria in the specified format, ready to copy-paste directly into a ticket or document    
2.  Do NOT wrap the output in a code block or add any preamble/commentary
3.  Keep each criterion concise, specific, and testable
4.  Use checkbox format (`- [ ]`) for all acceptance criteria items
5.  Do NOT include implementation details or technical solutions unless explicitly provided in the description
6.  Do NOT invent requirements beyond what's described in the ticket
7.  If something is ambiguous or missing, ask clarifying questions before creating criteria

## Acceptance Criteria Structure

Every acceptance criteria output MUST follow this format:

```
## Acceptance Criteria

- [ ] Criterion 1: Specific, testable condition
- [ ] Criterion 2: Specific, testable condition  
- [ ] Criterion 3: Specific, testable condition
```

### Writing Guidelines

1.  **Specificity**: Each criterion must be precise enough that a tester can verify it without interpretation
2.  **Testability**: Every criterion should be objectively verifiable (pass/fail)
3.  **Completeness**: Cover all requirements mentioned in the ticket description
4.  **Independence**: Each criterion should stand alone as a separate verification point
5.  **Action-oriented**: Start with action verbs (Add, Update, Remove, Ensure, Verify, etc.)
6.  **Clarity**: Use clear, unambiguous language

### Criteria Types

| Type | Description | Example |
| --- | --- | --- |
| **Functional** | What the feature should do | "Add a new 'User Preferences' button that uses the `fa-cog` Font Awesome icon" |
| **Visual/UI** | How it should look | "Position the 'User Preferences' button exactly as shown in the mock-up" |
| **Behavioral** | How it should behave | "Ensure all buttons (including the new one) are fully clickable and trigger their intended actions" |
| **Quality** | Non-functional requirements | "Maintain >= 90% unit test coverage" |
| **Data** | Data-related requirements | "User preferences should persist across browser sessions" |

### Common Patterns

1.  **For new features**: Focus on what should be added and how it should behave
2.  **For modifications**: Specify what changes and what remains unchanged
3.  **For bug fixes**: Describe the correct behavior that should be verified
4.  **For UI changes**: Include visual placement, styling, and interaction requirements
5.  **For performance**: Include measurable metrics or thresholds

## Examples

### Example 1: UI Component Update

**Ticket Description:**  
We need to shuffle around the buttons on the dashboard to make room for the user preferences button. See the mock up below for the placement of this new button:

This will require:

*   Replacing the Xestro logo with the small / square version.
*   Adding the new user preferences button, using the fa-cog icon
*   Moving the environment indicator to the top of the profile picture

**Acceptance Criteria:**

```
## Acceptance Criteria

- [ ] Replace the Xestro logo on the dashboard with the small/square version.
- [ ] Add a new "User Preferences" button that uses the `fa-cog` Font Awesome icon.
- [ ] Position the "User Preferences" button exactly as shown in the mock-up.
- [ ] Move the environment indicator so it sits directly above the profile picture.
- [ ] Ensure all buttons (including the new one) are fully clickable and trigger their intended actions.
- [ ] Maintain >= 90% unit test coverage.
```

### Example 2: API Endpoint

**Ticket Description:**  
Create a new API endpoint for user profile updates that accepts JSON payloads and returns appropriate status codes.

**Acceptance Criteria:**

```
## Acceptance Criteria

- [ ] Create a new POST endpoint at `/api/v1/users/profile`
- [ ] Accept JSON payload with fields: `firstName`, `lastName`, `email`, `phone`
- [ ] Return 200 OK with updated user data on successful update
- [ ] Return 400 Bad Request with validation errors for invalid input
- [ ] Return 401 Unauthorized if user is not authenticated
- [ ] Return 404 Not Found if user profile doesn't exist
- [ ] Update user data in the database with the provided values
- [ ] Include updated timestamp in the response
```

### Example 3: Bug Fix

**Ticket Description:**  
The search function returns duplicate results when searching with special characters.

**Acceptance Criteria:**

```
## Acceptance Criteria

- [ ] Search queries with special characters (%, _, [, ], etc.) should not return duplicate results
- [ ] All existing search functionality should continue to work as before
- [ ] Search results should be deduplicated before being returned to the client
- [ ] Performance should not degrade for searches with special characters
- [ ] Add test cases for searches with special characters to prevent regression
```

## Process

1.  **Analyze the ticket description** to identify all requirements
2.  **Break down requirements** into individual, testable criteria
3.  **Apply the writing guidelines** to ensure clarity and specificity
4.  **Review for completeness** - ensure all requirements are covered
5.  **Format correctly** using the specified structure
    

## Quality Checklist

Before finalizing acceptance criteria, verify:

- [ ] Each criterion is specific and unambiguous
- [ ] Each criterion is independently testable
- [ ] All requirements from the ticket are covered
- [ ] No implementation details are included (unless explicitly provided)
- [ ] Format follows the specified structure
- [ ] Language is clear and concise
- [ ] Checkbox format is used consistently
