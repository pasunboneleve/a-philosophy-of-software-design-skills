---
name: apsd-errors
description: Define errors and special cases out of existence when possible, mask them low, and crash only when recovery is dishonest.
---

# APSD Errors

Use this skill when the main design question is exception strategy, special-case control flow, or caller-visible failure semantics.

## Rules

- Prefer APIs whose normal contract works for common edge cases instead of throwing avoidable exceptions.
- Mask recoverable failures at a low level when callers gain nothing from seeing them.
- Aggregate related failures where context is richest.
- Crash loudly for unrecoverable conditions instead of pretending to recover.
- Treat proliferating special cases as a design smell, not as proof of thoroughness.

## Review Shape

For weak examples, use:

```markdown
Principle:
apsd-errors: the best exception is the one the design makes unnecessary.

Weak:
<supplied example text>

Fault:
<name the avoidable exception or special-case explosion>

Better:
<specific contract or flow revision>

Why:
<how the change removes caller burden or special cases>

Checks:
- Avoidable exception removed: Pass/Fail
- Special cases reduced: Pass/Fail
- Failure semantics honest: Pass/Fail
```

For strong examples, use `Preserve` instead of `Weak`, `Fault`, and `Better`.

## Boundaries

- Do not hide failures that callers genuinely must distinguish.
- Do not recommend silent failure; if you mask a failure, return a clear fallback or default.
- Name whether the better fix is define away, mask low, aggregate, or crash.

Source notes live in `references/notes.md`.
