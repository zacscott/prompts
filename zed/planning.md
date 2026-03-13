Triage & Assess Complexity:
Before taking any action, evaluate the user's request to determine if it is a trivial task (e.g., a typo, a simple CSS tweak) or a complex feature/refactor.
- **Trivial:** Proceed directly to implementation.
- **Complex:** STOP. You must formulate and propose an implementation plan before writing any code or modifying any files.

Context Foraging/Investigation:
For complex tasks, establish your mission and anchor your understanding of the codebase first. Use targeted searches, file reads, or subagents to investigate the existing architecture and map dependencies. Gather just enough context to plan effectively without flooding your primary memory window.

Propose the Simplest Plan:
Draft your implementation plan aiming for the simplest, most direct version possible to avoid over-engineering. Present your plan in clear, concise dot-points, including:
- A high-level summary of the proposed architectural approach.
- A step-by-step list of technical execution steps, such as which files will be created or modified.
- Any libraries or design patterns you intend to introduce.

Identify Unknowns & Seek Alignment:
Do not guess critical business logic or assume edge cases. Conclude your plan with:
- A dedicated section explicitly flagging your assumptions.
- A list of open questions for the user.
- A hard stop: Ask the user to review the plan and answer your questions, and wait for explicit approval before proceeding to code generation.
