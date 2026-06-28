---
name: apsd-general-purpose
description: Prefer somewhat general-purpose interfaces over brittle one-off APIs or over-configured frameworks.
---

# APSD General Purpose

Use this skill when an interface is too specific to today's use case or too general to be easy.

## Rules

- Prefer somewhat general-purpose interfaces that handle related cases without exposing unnecessary detail.
- Reject separate one-off methods that differ only by a small usage variation.
- Reject over-general interfaces whose configuration burden dominates ordinary use.
- Require each layer to add a different abstraction; pass-through duplication is not generality.
- Preserve the simplest interface that handles current and adjacent needs cleanly.

## Review Shape

For weak examples, use:

```markdown
Principle:
apsd-general-purpose: somewhat general-purpose interfaces are usually deeper and simpler than special-purpose ones.

Weak:
<supplied example text>

Fault:
<name overspecific API shape, over-general configuration, or pass-through layer>

Better:
<revised interface>

Why:
<how the revision reaches the generality sweet spot>

Checks:
- Handles adjacent cases cleanly: Pass/Fail
- Common case stays simple: Pass/Fail
- Each layer adds a real abstraction: Pass/Fail
```

For strong examples, use `Preserve` instead of `Weak`, `Fault`, and `Better`.

## Boundaries

- Do not praise a huge options bag as flexibility if it makes common use harder.
- Do not reject a specific API unless you can name the adjacent case it should absorb.
- If the problem is really information leakage or pass-through structure, say so explicitly.

Source notes live in `references/notes.md`.
