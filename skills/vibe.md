When the user asks you to rewrite or improve a prompt for a code-generation agent, follow this system precisely.

## When to Activate

Use this skill whenever:

- The user explicitly asks to "rewrite", "improve", "flesh out", or "enhance" a prompt for a code-generation agent
- The user shares a prompt draft that needs refinement for better code generation results
- The user requests help with prompt engineering specifically for code generation tasks
- The user wants to transform a vague coding request into a structured prompt for an AI coding assistant

## Output Rules

1. Output ONLY the rewritten prompt in the specified format
2. Do NOT include any commentary, explanations, or meta-discussion about the rewrite
3. Present the prompt as a user message, not a system prompt
4. Do NOT include role hinting (e.g., "You are a...", "Act as a...")
5. Assume the code agent has full access to the codebase and understands the project's frameworks, libraries, and languages
6. Structure the prompt to elicit the desired behavior from the code agent

## Prompt Structure

Every rewritten prompt MUST follow this structure:

```
[The rewritten prompt as a direct user message]
```

### Required Elements

The rewritten prompt MUST include these elements:

1. **Clear Task Description**: What needs to be built or implemented
2. **Clarification Request**: Explicit instruction to ask for clarification on any unanswered questions
3. **Decision Flagging**: Explicit instruction to flag any questionable decisions or assumptions
4. **Implementation Plan**: Explicit requirement to provide a detailed step-by-step implementation plan before writing code
5. **Context Assumption**: Implicit assumption that the agent has full codebase access (do not state this explicitly)

### Writing Guidelines

1. **User Message Format**: Write as if you (the user) are speaking directly to the code agent
2. **Conciseness**: Be specific and direct, avoiding unnecessary preamble
3. **Action-Oriented**: Use imperative language when appropriate
4. **Clarity**: Ensure the requirements are unambiguous
5. **Completeness**: Include all necessary information from the original query
6. **Professional Tone**: Maintain a professional, collaborative tone

### Agent Behavior Requirements

The rewritten prompt must explicitly instruct the agent to:

1. **Ask for clarification** on any unanswered questions or ambiguities
2. **Flag questionable decisions** including assumptions, trade-offs, or potential issues
3. **Provide detailed implementation plan** with step-by-step approach before writing any code
4. **Consider existing codebase** (implied through context, not stated)

## Examples

### Example 1: Simple Feature Request

**Original Query:**
"Add a search function to the user dashboard"

**Rewritten Prompt:**
```
I need to add a search function to the user dashboard. Before you start coding, please:

1. Ask me any clarifying questions you have about requirements or implementation details
2. Flag any decisions that seem questionable or where you're making assumptions
3. Provide a detailed step-by-step implementation plan

Once we've aligned on the plan, proceed with the implementation.
```

### Example 2: Bug Fix

**Original Query:**
"The login API is returning 500 errors when users have special characters in their passwords"

**Rewritten Prompt:**
```
The login API is returning 500 errors when users have special characters in their passwords. Please:

1. First, ask for any clarification you need about the error patterns or existing code
2. Flag any implementation decisions that might be problematic
3. Provide a step-by-step plan for investigating and fixing this issue

After we review the plan together, implement the fix.
```

### Example 3: Complex Feature

**Original Query:**
"We need to implement user role-based permissions across the application. Admins should see everything, managers see their department, regular users see only their own data."

**Rewritten Prompt:**
```
I need to implement user role-based permissions across the application with three levels: admins (see everything), managers (see their department), and regular users (see only their own data).

Before implementing:

1. Ask me any questions about permission models, data structures, or edge cases
2. Flag any architectural decisions or assumptions you're making
3. Provide a detailed implementation plan covering:
   - Database changes needed
   - API modifications required
   - Frontend updates
   - Testing strategy
   - Migration approach for existing data

Once we've discussed and refined the plan, proceed with the implementation.
```

### Example 4: Refactoring Task

**Original Query:**
"Refactor the payment processing module to use the new Stripe API version"

**Rewritten Prompt:**
```
I need to refactor the payment processing module to use the new Stripe API version. Please:

1. Ask clarifying questions about which parts of the module need updating
2. Flag any compatibility issues or breaking changes you anticipate
3. Provide a step-by-step refactoring plan including:
   - Areas of the codebase affected
   - Testing strategy
   - Rollback plan
   - Timeline estimates

After we agree on the plan, implement the refactoring.
```

## Process

1. **Analyze the original query** to understand the core requirement
2. **Identify missing elements** that need to be added (clarification, flagging, planning)
3. **Rewrite in user message format** using direct, clear language
4. **Incorporate required elements** (clarification request, decision flagging, implementation plan requirement)
5. **Review for completeness** - ensure all original requirements are preserved
6. **Ensure professional tone** - collaborative, not dictatorial

## Quality Checklist

Before finalizing the rewritten prompt, verify:

- [ ] Prompt is written as a user message (not system prompt)
- [ ] No role hinting included
- [ ] Explicit request for clarification questions
- [ ] Explicit request to flag questionable decisions
- [ ] Explicit requirement for implementation plan before coding
- [ ] All original requirements are preserved
- [ ] Language is clear and direct
- [ ] Tone is professional and collaborative
- [ ] Assumes codebase context (but doesn't state it explicitly)
- [ ] Format follows the specified structure

## Common Patterns

### For New Features:
- Emphasize planning and clarification due to undefined requirements
- Include scope definition in the prompt

### For Bug Fixes:
- Focus on investigation and analysis before implementation
- Include error reproduction requirements

### For Refactoring:
- Emphasize impact analysis and testing
- Include rollback considerations

### For Performance Improvements:
- Include measurement and benchmarking requirements
- Emphasize before/after comparison
