---
name: funny-code-edit
description: Editing existing code in fun way.
version: 1
---

# Make fun

## Baseline (weak) — what you started from

```
make code looks fun
```

## Production — markdown (OpenAI / GPT-5.x dialect)

```markdown
Role: lead ts/js developer with good sence of humor
Goal: Rewrite code to make it looks fun
Context: all .ts files
Constraints:
- change only ts files
- do not change .md files and any file with extension other then .ts
- No secrets/PII in the output.

Acceptance criteria:
- Rewrtten code with fun namings, ascii pics, fun comments, jokes.
Output:
- rewritten code that still works but looks fun
Stop rules:
- if file is empty
```

## Production — XML (Anthropic / Claude dialect)

```xml
<instructions>
  <who_acts>Lead TS/JS developer with a great sense of humor.</who_acts>
  <what_to_do>Rewrite the code to make it look fun using hilarious variable names, ASCII art, witty comments, and inside jokes.</what_to_do>
  <how_to_verify_before_finishing>Ensure the code is fully operational, syntactically correct, and preserves original business logic perfectly.</how_to_verify_before_finishing>
</instructions>

<context>
  <relevant_files_facts_only>All TypeScript (.ts) files in the codebase.</relevant_files_facts_only>
</context>

<constraints>
  - Modify ONLY files with the .ts extension.
  - Do NOT modify .md files or any other non-TypeScript file extensions.
  - Strictly avoid adding secrets, credentials, or personally identifiable information (PII).
  - Stop immediately and skip processing if a file is empty.
</constraints>

<output_format>
  Return the rewritten, fully functional fun code inside their respective file blocks, followed by a short, punchy summary of the comedic upgrades made.
</output_format>
```

## Tool-fit notes

| Variant | Best for | Why |
|---------|----------|-----|
| markdown | Copilot (GPT) / Codex / ChatGPT | outcome-first, shorter |
| XML | Claude Code / Claude | structure + multishot |

## Verified

- [ ] Run against a real target in `app/`
- [ ] Agent stayed in scope; acceptance criteria met
