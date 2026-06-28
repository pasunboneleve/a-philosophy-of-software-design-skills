# AGENTS.md

Use repository-local instructions first when present. Use the Codex skills below as the standing workflow rules.

## Global invariants

- Never push unless the user explicitly asks.
- Do not bypass validation, task hygiene, or review loops.

## Code and version control

When working on code, architecture, tests, commits, branches, Kata, Roborev, PRs, or version control:

Prefer and apply:
- $roborev-kata-workflow
- $commit-discipline
- $change-friendly-architecture

Before running `git commit`:

- Announce the applicable skills for the commit phase.
- Re-read `$commit-discipline`.
- Classify the commit as simple or non-trivial.
- For non-trivial commits, use the structured commit message sections from `$commit-discipline`.
- Confirm validation status and Kata status.

## Text and documentation

When writing, editing, or reviewing prose, prompts, code, APIs, tests, architecture notes, or other text-bearing work:

Load and apply:
- $oiticica-style

When changing or reviewing README files, docs, help text, man pages, info pages, changelog prose, or other project documentation:

Load and apply:
- $documentation-boundary
- $docs-structure
- $oiticica-style

## Skill index

- Every skill in this repository lives under `src/apsd-*/SKILL.md`.
- Every skill must have `agents/openai.yaml`, `evals/evals.yaml`, and `references/notes.md`.
- Every skill must be listed in the root `README.md` with a `src/<skill-name>/SKILL.md` link.
- Eval prompts must prove skill lift: with-skill runs should pass near 100%, and without-skill runs should fail near 0%.
- Do not make eval prompts self-contained by teaching the review shape, rubric, concept definition, expected fault, or expected answer. That behavior belongs in `SKILL.md`.

Use the `testing` skill to choose validation scope. For skill package changes, the blast radius is each changed skill, so run focused validation:

```bash
direnv exec . bash scripts/validate_skills.sh <skill-name>
```

## Fallback

If the task is ambiguous, prefer:
- deterministic validation over reasoning
- small, reversible changes
- feature branches
