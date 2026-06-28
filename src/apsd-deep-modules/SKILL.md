---
name: apsd-deep-modules
description: Prefer simple interfaces with powerful hidden implementations and reject shallow pass-through layers.
---

# APSD Deep Modules

Use this skill when the main question is interface depth, information hiding, or pass-through structure.

## Rules

- Prefer modules whose interface is much simpler than their implementation.
- Keep implementation details out of the interface comment and parameter list.
- Reject pass-through layers that add no new abstraction.
- Treat leaked design decisions across modules as information leakage.
- Make common cases simple; keep rare cases possible without burdening every caller.

## Review Shape

For weak examples, use:

```markdown
Principle:
apsd-deep-modules: a good module hides complexity behind a simple interface.

Weak:
<supplied example text>

Fault:
<name shallow interface, information leakage, or pass-through structure>

Better:
<specific interface or boundary revision>

Why:
<how the change makes the module deeper>

Checks:
- Interface simplicity: Pass/Fail
- Hidden implementation detail: Pass/Fail
- Value beyond pass-through: Pass/Fail
```

For strong examples, use `Preserve` instead of `Weak`, `Fault`, and `Better`.

## Boundaries

- Do not praise a wrapper merely because it creates another layer.
- Do not call a module deep if callers still need to know its internal format or policy.
- If the current interface is already small and powerful, preserve it.
- In `Better`, do not offer a menu of optional tweaks. Either remove the redundant layer or assign each retained layer one narrow responsibility that adds a real abstraction.
- In `Better`, state the final boundary directly instead of saying `consider` or listing options. Name which layer disappears, or name the single responsibility each retained layer keeps.
- In `Better`, do not join incompatible revisions with `or`. Pick one final boundary shape and write it as the recommendation.

Source notes live in `references/notes.md`.
