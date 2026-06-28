---
name: apsd-comments
description: Require comments to explain abstractions, invariants, and non-obvious design intent instead of repeating code.
---

# APSD Comments

Use this skill when the question is what should be documented, where, and at what level.

## Rules

- Interface comments describe what a module does, not how it does it.
- Implementation comments explain strategy, invariants, or non-obvious intent.
- Reject comments that merely restate the code.
- Prefer comments that add precision: units, boundaries, null semantics, ownership, or invariants.
- If code needs a long interface comment to explain a messy abstraction, question the abstraction.

## Review Shape

For weak examples, use:

```markdown
Principle:
apsd-comments: comments should add information the code cannot express by itself.

Weak:
<supplied example text>

Fault:
<name repeated code, missing invariant, wrong abstraction level, or missing precision>

Better:
<revised comment or documentation shape>

Why:
<what information the revision adds>

Checks:
- Adds new information: Pass/Fail
- Right abstraction level: Pass/Fail
- Precision present where needed: Pass/Fail
```

For strong examples, use `Preserve` instead of `Weak`, `Fault`, and `Better`.

## Boundaries

- Do not add comments when better naming or simpler structure would remove the need.
- Do not place implementation detail in an interface comment.
- If the right fix is to simplify the code first, say so.
- If a comment already adds a useful invariant, boundary, null rule, ownership rule, or unit that the identifier alone cannot express, treat it as strong. Do not downgrade it merely because an example or expansion could be added.
- Do not ask for examples, use cases, or surrounding context in a focused comment review when the supplied note already states the needed invariant or unit precisely enough.

Source notes live in `references/notes.md`.
