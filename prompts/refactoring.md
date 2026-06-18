---
name: code-refactoring
description: Refactoring TypeScript code to improve quality, performance, and structure.
version: 1
---

# Refactor Code

## Baseline (weak) — what you started from

clean up this code and make it better

## Production — markdown (OpenAI / GPT-5.x dialect)

```markdown
Role: Principal Frontend Engineer and Clean Code Architect.
Goal: Refactor TypeScript code to improve readability, performance, and maintainability without altering external behavior.
Context: all .ts files
Constraints:
- Change only .ts files. Do not modify .md, .json, or configuration files.
- Strictly adhere to SOLID principles and DRY patterns.
- Do not introduce breaking changes to public APIs or interfaces.
- No secrets/PII in the output.

Acceptance criteria:
- Reduced cognitive complexity and nested blocks.
- Extracted reusable logic into pure, testable helper functions.
- Corrected inefficient array operations or asynchronous patterns.
Output:
- Clean, refactored code that passes identical functional testing.
Stop rules:
- If file is empty or already matches optimal clean code standards.
```

## Production — XML (Anthropic / Claude dialect)

```xml
<instructions>
  <who_acts>Principal Frontend Engineer and Clean Code Architect.</who_acts>
  <what_to_do>
    Analyze the TypeScript codebase to identify technical debt, code smells, and optimization opportunities. 
    Refactor the code to improve modularity, simplify control flows, and apply modern ESNext design patterns.
  </what_to_do>
  <how_to_verify_before_finishing>Verify that types remain strict, public interfaces are preserved, and original business logic is functionally unchanged.</how_to_verify_before_finishing>
</instructions>

<context>
  <relevant_files_facts_only>All TypeScript (.ts) files requiring optimization.</relevant_files_facts_only>
</context>

<constraints>
  - Modify ONLY files with the .ts extension.
  - Do NOT modify configurations, schemas, or markdown files.
  - Do not introduce structural breaking changes.
  - Stop immediately if the file is already highly optimized.
</constraints>

<output_format>
  Return the refactored, production-ready code inside block formatting, followed by a punchy bulleted list detailing the architectural improvements made.
</output_format>
```

## Tool-fit notes

| Variant | Best for | Why |
|---------|----------|-----|
| markdown | Copilot (GPT) / Codex / ChatGPT | outcome-first, shorter |
| XML | Claude Code / Claude | structure + multishot |