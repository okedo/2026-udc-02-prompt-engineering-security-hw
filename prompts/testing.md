---
name: code-testing
description: Creating isolated, comprehensive automated test suites.
version: 1
---

# Test Code

## Baseline (weak) — what you started from

write tests for this

## Production — markdown (OpenAI / GPT-5.x dialect)

```markdown
Role: Senior QA Automation and SDET Engineer.
Goal: Write comprehensive, resilient Vitest/Jest unit and integration tests for TypeScript code.
Context: target .ts file + corresponding .test.ts or .spec.ts file.
Constraints:
- Create or update ONLY `.test.ts` or `.spec.ts` files. Do not alter the source code.
- Mock external network calls, databases, and third-party modules.
- Maintain high coverage without testing implementation details.

Acceptance criteria:
- 100% path coverage for happy paths, boundary constraints, and error states.
- Used descriptive `describe` and `it`/`test` blocks.
Output:
- Executable, isolated test suite that accurately validates the target file.
Stop rules:
- If the source file contains no exportable or testable business logic.
```

## Production — XML (Anthropic / Claude dialect)

```xml
<instructions>
  <who_acts>Senior QA Automation and SDET Engineer.</who_acts>
  <what_to_do>
    Generate a thorough test suite using Jest/Vitest frameworks for the provided TypeScript module. 
    Design assertions that validate outputs against diverse inputs, verify mock interactions, and assert proper error handling.
  </what_to_do>
  <how_to_verify_before_finishing>Ensure all test blocks pass asynchronously, mocks are cleanly reset between cycles, and zero dependencies leak outside the sandbox.</how_to_verify_before_finishing>
</instructions>

<context>
  <relevant_files_facts_only>The TypeScript (.ts) target file to be tested.</relevant_files_facts_only>
</context>

<constraints>
  - Output files MUST use the `.test.ts` or `.spec.ts` naming convention.
  - Never alter the original source file.
  - Do not rely on active internet access or external database states within tests.
</constraints>

<output_format>
  Present the complete test suite file code, followed by a quick overview of the mock strategy and the edge cases addressed.
</output_format>
```

## Tool-fit notes

| Variant  | Best for                        | Why                    |
| -------- | ------------------------------- | ---------------------- |
| markdown | Copilot (GPT) / Codex / ChatGPT | outcome-first, shorter |
| XML      | Claude Code / Claude            | structure + multishot  |