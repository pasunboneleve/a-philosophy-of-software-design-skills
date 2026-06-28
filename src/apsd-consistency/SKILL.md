---
name: apsd-consistency
description: Use conventions, invariants, and pattern reuse to reduce surprise and cognitive load.
---

# APSD Consistency

Use this skill when similar things are not done similarly, or different things are not distinguished clearly enough.

## Rules

- Use the same name, pattern, and error convention for the same concept everywhere.
- Do not use the same label for different concepts.
- Follow existing project conventions unless there is a strong reason to change all related code.
- Preserve invariants that remove special cases and simplify reasoning.
- Treat one-off style innovation in an established codebase as a cost, not as automatic improvement.

## Review Shape

For weak examples, use:

```markdown
Principle:
apsd-consistency: consistency lets readers reuse knowledge safely across the codebase.

Weak:
<supplied example text>

Fault:
<name inconsistent naming, style, error handling, or invariant drift>

Better:
<specific convention-aligned revision>

Why:
<how the change reduces surprise or duplicate decisions>

Checks:
- Same concept, same pattern: Pass/Fail
- Different concepts distinguished: Pass/Fail
- Existing convention preserved or deliberately replaced: Pass/Fail
```

For strong examples, use `Preserve` instead of `Weak`, `Fault`, and `Better`.

## Boundaries

- Do not force uniformity across truly different abstractions.
- Do not argue for a new convention unless it is strong enough to justify changing all related code.
- If the example's real problem is naming precision rather than convention drift, say so.
- When the fault is mixed error handling or mixed return conventions within one operation family, `Better` must pick one rule for the whole family. Do not leave one sibling returning `null`, another throwing, and another returning booleans.
- If the example already says which spelling is primary and which names survive only as deprecated compatibility aliases, treat it as strong. Use `Preserve`, not `Weak`, `Fault`, or `Better`.
- Do not rewrite a strong convention statement merely to restate the same primary-versus-compatibility rule in different words.

Source notes live in `references/notes.md`.
