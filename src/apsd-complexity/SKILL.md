---
name: apsd-complexity
description: Treat change amplification, cognitive load, and obscurity as first-order design failures.
---

# APSD Complexity

Use this skill when the controlling problem is complexity itself: too many places to change, too much context to hold, or too much hidden knowledge.

## Rules

- Judge complexity by three tests: change amplification, cognitive load, and unknown unknowns.
- Name dependencies and obscurity as the two common root causes.
- Prefer strategic improvements over tactical patches.
- Reject small local fixes that multiply future exceptions, flags, or call-site knowledge.
- When a design is already simple and local, preserve it.
- When the example is literal hand-rolled prefix stripping and the language has a standard-library primitive for it, prefer that primitive over fresh slicing logic.
- If a short example already uses that standard primitive inline, do not downgrade it just because the literal prefix string appears twice.

## Review Shape

Use this shape for a weak example:

```markdown
Principle:
apsd-complexity: complexity is anything that makes the system harder to understand or modify.

Weak:
<supplied example text>

Fault:
<name the exact change amplification, cognitive load, or obscurity problem>

Better:
<specific redesign or rewrite>

Why:
<how the revision reduces future complexity>

Checks:
- Change amplification: Pass/Fail
- Cognitive load: Pass/Fail
- Obscurity: Pass/Fail
```

Use this shape for a strong example:

```markdown
Principle:
apsd-complexity: complexity is anything that makes the system harder to understand or modify.

Preserve:
<supplied example text>

Why:
<why the design is already local and obvious>

Checks:
- Change amplification: Pass/Fail
- Cognitive load: Pass/Fail
- Obscurity: Pass/Fail
```

## Boundaries

- Do not say only `this is complex`; name the mechanism.
- Do not turn a local design problem into a broad architecture rewrite unless the example forces it.
- Prefer one concrete simplification over a large checklist.
- For literal manual prefix-removal examples, prefer the standard primitive to helper extraction, compatibility wrappers, or fresh index arithmetic.
- If an example already replaces hand-rolled branching or slicing with one standard-library primitive and keeps the change local, treat it as strong. Use `Preserve`, not `Weak`.
- Do not invent a named constant or extra binding for a two-line `startswith` plus `removeprefix` example unless the surrounding example already establishes reuse.
- Do not invent helper methods, compatibility wrappers, or extra abstraction layers for a two-line example that is already local and obvious.

Source notes live in `references/notes.md`.
