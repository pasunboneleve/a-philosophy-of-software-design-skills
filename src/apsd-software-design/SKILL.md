---
name: apsd-software-design
description: Route general design, refactoring, and review work through the relevant APSD skills.
---

# APSD Software Design

Use this skill when the user asks for a general software-design review, refactoring assessment, API critique, or architecture check and has not named a narrower APSD skill.

This skill is a router. It selects only the APSD skills that match the real fault.

## Pipeline

1. Check complexity first.
2. Check boundaries and abstraction shape.
3. Check failure and special-case design.
4. Check names, comments, and conventions.
5. Check whether the process or plan itself is weak.

Stop when one or two skills explain the real problem. Do not force every APSD category into the answer.

## Routing rules

- Use `apsd-complexity` when the issue is scattered change, hidden knowledge, or rising cognitive load.
- Use `apsd-deep-modules` when the issue is interface depth, information leakage, or pass-through layering.
- Use `apsd-errors` when exceptions or special cases dominate the design.
- Use `apsd-naming` when the main reading failure is vague, misleading, or inconsistent identifiers.
- Use `apsd-comments` when missing or low-value comments block understanding, especially at interfaces.
- Use `apsd-general-purpose` when the interface is too specific or too configurable.
- Use `apsd-design-process` only when the example is a plan, implementation approach, or refactoring process and it shows tactical patching, first-idea lock-in, or no interface thinking.
- Use `apsd-consistency` when the fault is convention drift, mixed patterns, or weakened invariants.

## Selection rules

- Select one to three skills unless the user asks for a full audit.
- If the user names a specific APSD skill, use that skill and add another only when it is necessary to explain the real fault.
- Preserve already strong designs instead of inventing change.
- If the prompt says `revise only if needed`, revise only for a concrete APSD fault. Do not rewrite for flow, extra explicitness, or longer names alone.
- Do not label a design complex if the real problem is only naming, comments, or one missing invariant.
- Do not route to `apsd-comments` when better naming or a better boundary would remove the need for extra prose.
- Treat a design as already strong when it already hides implementation detail behind a clear owner, returns explicit field names, and shows no concrete change-amplifying fault.
- Do not select `apsd-design-process` to praise a finished design artifact when `apsd-deep-modules`, `apsd-naming`, or another concrete design skill already explains the passing relation.

## Output shape

```markdown
Selected skills:
- <skill>: <why it applies>

Diagnosis:
- <skill>: <specific fault or passing relation>

Revision:
<revised design advice, code sketch, or "No revision needed.">

Checks:
- <skill check>: Pass/Fail
```

## Evidence rules

- In `Selected skills`, cite the exact evidence from the example, such as the generic field names, the pass-through layers, or the catch-and-ignore exception pattern.
- In `Diagnosis`, name the APSD fault directly: `shallow pass-through layer`, `avoidable exception`, `generic field names`, `information leakage`, or another concrete fault.
- When routing to `apsd-errors`, say whether callers are forced to catch and ignore an avoidable exception or another special case.
- When routing to `apsd-errors`, make the `Revision` change the contract directly: return a status/result, make the operation idempotent, or otherwise remove the expected catch-and-ignore path.
- When routing to `apsd-naming`, mention the actual vague identifiers by name.
- When the design already passes the selected checks, write `Revision: No revision needed.`

## Finish

Before answering, verify that:

- every selected skill is named exactly;
- every selected skill has concrete evidence in the example;
- the revision reduces future complexity rather than only rephrasing the problem.

Source notes live in `references/notes.md`.
