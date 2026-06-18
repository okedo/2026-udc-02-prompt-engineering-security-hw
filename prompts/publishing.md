---
name: code-publishing
description: Auditing and configuring manifests for deployment and package registry releases.
version: 1
---

# Publish Code

## Baseline (weak) — what you started from

get this package ready to release

## Production — markdown (OpenAI / GPT-5.x dialect)

```markdown
Role: DevSecOps and Release Delivery Specialist.
Goal: Audit, prepare, and configure a project package for safe, seamless distribution to npm, GitHub releases, or registries.
Context: `package.json`, `tsconfig.json`, lockfiles, and build artifacts.
Constraints:
- Modify only configuration, distribution setup, or release pipeline files.
- Strictly adhere to Semantic Versioning (SemVer) rules.
- Ensure build outputs (.d.ts files, minified bundles) are perfectly routed.

Acceptance criteria:
- Validated that `files` array inclusions in `package.json` prevent bloat (no tests or source maps leaked unless required).
- Dependency vs PeerDependency boundaries are accurately defined.
- Created an automated, structured CHANGELOG entry for the deployment.
Output:
- Optimally configured deployment files and a clear distribution checklist.
Stop rules:
- If missing essential baseline metadata like licenses or author fields.
```

## Production — XML (Anthropic / Claude dialect)

```xml
<instructions>
  <who_acts>DevSecOps and Release Delivery Specialist.</who_acts>
  <what_to_do>
    Review package descriptors and bundling definitions to ready the project for public distribution. 
    Audit build target exports, clean up outdated or insecure dependencies, and structure clear package entry points (CommonJS/ESM exports).
  </what_to_do>
  <how_to_verify_before_finishing>Confirm all required files exist in the distribution payload, types are packaged properly, and the lockfile matches package definitions.</how_to_verify_before_finishing>
</instructions>

<context>
  <relevant_files_facts_only>`package.json`, asset pipelines, and package configurations.</relevant_files_facts_only>
</context>

<constraints>
  - Never expose private developer environment paths, access keys, or internal registry links.
  - Do not increment versions arbitrarily without analyzing release change impacts.
</constraints>

<output_format>
  Output the updated `package.json` or pipeline configuration file, followed by a step-by-step pre-flight checklist for the terminal.
</output_format>
```

## Tool-fit notes

| Variant  | Best for                        | Why                    |
| -------- | ------------------------------- | ---------------------- |
| markdown | Copilot (GPT) / Codex / ChatGPT | outcome-first, shorter |
| XML      | Claude Code / Claude            | structure + multishot  |