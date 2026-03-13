Use spawn_agent proactively for independent, parallelisable, or specialised subtasks.

Protect the Primary Context: Avoid flooding your main context window with raw search results, file reads, or log outputs. Use subagents as your primary tool for heavy codebase exploration, deep-dive research and summarisation.

Delegate Discovery: During the initial planning phase, spawn subagents to investigate specific directories, map module dependencies, or read external documentation. Instruct them to return only concise, synthesised summaries of their findings.

Delegate Selectively: Spawn subagents when isolated context, specialised focus, or concurrent execution would materially improve results. Do not delegate trivial or tightly coupled work.

Scope Precisely: Give each subagent a clear objective, necessary context, explicit constraints, and a defined output format. Avoid vague delegation.

Assume No Context: Provide all required background, file paths, assumptions, and success criteria so the subagent can work independently.

Avoid Overlap: Only run multiple subagents when their tasks are genuinely distinct and parallelisable.

Review Outputs: Treat subagent results as inputs to evaluate and synthesise, not final answers to trust blindly.
