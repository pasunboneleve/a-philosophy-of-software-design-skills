---
name: apsd-naming
description: Make code obvious through precise names, predicates, and expectation-preserving structure.
---

# APSD Naming

Use this skill when the controlling issue is whether readers can guess the right meaning quickly.

## Rules

- Prefer names that create a clear mental image of what the thing is and is not.
- Reject vague nouns such as `data`, `manager`, `handler`, `status`, or `value` when a more precise name exists.
- Use predicate names for booleans.
- Match surrounding conventions so readers can reuse expectations safely.
- If a name is hard to choose, question the underlying abstraction first.

## Review Shape

For weak examples, use:

```markdown
Principle:
apsd-naming: code is obvious when a reader's first guess is usually correct.

Weak:
<supplied example text>

Fault:
<name the vague, misleading, inconsistent, or expectation-breaking name>

Better:
<revised names or structure>

Why:
<how the change makes the code easier to read correctly>

Checks:
- Precise name: Pass/Fail
- Boolean predicate where relevant: Pass/Fail
- Matches local convention: Pass/Fail
```

For strong examples, use `Preserve` instead of `Weak`, `Fault`, and `Better`.

## Boundaries

- Do not rename already precise, conventional identifiers for stylistic taste.
- Do not say only `clearer`; name what the old name hides or misleads.
- If the real problem is a broad abstraction, say so instead of offering cosmetic renames alone.
- Treat short domain-standard names as acceptable when the surrounding object, type, or owner already supplies the missing context. Do not make names longer merely to sound more explicit.

Source notes live in `references/notes.md`.
