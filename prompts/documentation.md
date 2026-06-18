---
name: code-documentation
description: Generating project README structures and rich codebase docstrings.
version: 1
---

# Write Documentation

## Baseline (weak) — what you started from

write a readme for this code

## Production — markdown (OpenAI / GPT-5.x dialect)

```markdown
Role: Technical Writer and Developer Relations Engineer.
Goal: Generate clean, professional Markdown documentation and TSDoc/JSDoc block comments.
Context: target .ts source files or an existing `README.md`.
Constraints:
- Modify or create only `.md` files or code docstrings. Do not alter executable logic.
- Use explicit, jargon-free terminology accessible to non-native speakers.
- Keep examples highly realistic and syntax-error-free.

Acceptance criteria:
- Codebase includes fully detailed TSDoc headers for all exported methods, params, and return shapes.
- The `README.md` provides clear setup rules, architectural overviews, and functional usage code snippets.
Output:
- Updated Markdown documentation file or inline-documented codebase.
Stop rules:
- If no documentable surface functions or public APIs exist.
```

## Production — XML (Anthropic / Claude dialect)

```xml
<instructions>
  <who_acts>Technical Writer and Developer Relations Engineer.</who_acts>
  <what_to_do>
    Draft clean, comprehensive markdown documentation or generate exhaustive inline JSDoc/TSDoc blocks for the source code.
    Document the 'Why' behind architectural choices, spell out input/output interfaces, and outline setup prerequisites clearly.
  </what_to_do>
  <how_to_verify_before_finishing>Verify markdown syntax rendering, ensure code block blocks mention the correct language tags, and confirm API contracts match the code perfectly.</how_to_verify_before_finishing>
</instructions>

<context>
  <relevant_files_facts_only>Source files requiring documentation and project markdown files (`README.md`, `API.md`).</relevant_files_facts_only>
</context>

<constraints>
  - Do not make any functional edits to executable code strings.
  - Keep sentences concise, clear, and scannable.
  - Do not leak proprietary system mechanics or credentials in examples.
</constraints>

<output_format>
  Provide the resulting Markdown document or the code decorated with rich inline comments inside standard code fences.
</output_format>
```

## Tool-fit notes

| Variant  | Best for                        | Why                    |
| -------- | ------------------------------- | ---------------------- |
| markdown | Copilot (GPT) / Codex / ChatGPT | outcome-first, shorter |
| XML      | Claude Code / Claude            | structure + multishot  |