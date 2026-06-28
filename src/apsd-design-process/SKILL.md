---
name: apsd-design-process
description: Enforce design-it-twice, interface comments first, and strategic improvement while changing code.
---

# APSD Design Process

Use this skill when the issue is how to approach design work, not just which local rule to apply.

## Rules

- Design it twice: consider at least one materially different alternative before settling.
- Write interface comments before implementation for new modules and major new methods.
- Improve design while touching code; do not hide behind minimal-diff tactics.
- Prefer incremental design of abstractions over either big upfront planning or feature-only churn.
- When judging a plan, ask whether it leaves the system easier to change than before.

## Review Shape

For weak examples, use:

```markdown
Principle:
apsd-design-process: design quality improves when alternatives are considered explicitly and abstractions are clarified before code hardens.

Weak:
<supplied example text>

Fault:
<name first-idea lock-in, tactical patching, missing interface thought, or no improvement while touching code>

Better:
<revised process or plan>

Why:
<how the better process improves design quality>

Checks:
- Alternative considered: Pass/Fail
- Interface clarified early: Pass/Fail
- Leaves code easier to change: Pass/Fail
```

For strong examples, use `Preserve` instead of `Weak`, `Fault`, and `Better`.

## Boundaries

- Do not demand exhaustive design exploration; one real alternative is enough.
- Do not treat process ceremony as design quality.
- If the example is already strategically improving code, preserve it.

Source notes live in `references/notes.md`.
