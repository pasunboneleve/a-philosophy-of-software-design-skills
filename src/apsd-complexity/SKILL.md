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

Source notes live in `references/notes.md`.
