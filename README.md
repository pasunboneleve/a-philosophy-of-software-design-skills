# APSD skills for [Codex](https://developers.openai.com/codex/cli), [Claude Code](https://claude.com/product/claude-code), and [Pi](https://pi.dev/)

[![Skill CI](https://github.com/pasunboneleve/a-philosophy-of-software-design-skills/actions/workflows/skill-ci.yml/badge.svg)](https://github.com/pasunboneleve/a-philosophy-of-software-design-skills/actions/workflows/skill-ci.yml?query=event%3Apull_request)

Focused software-design skills derived from John Ousterhout's *A Philosophy of Software Design*. Skill sources live under `src/`.

## Why this exists

The book is useful because it names recurring design failures precisely: change amplification, shallow modules, information leakage, pass-through layers, vague names, comment debt, special-case drift, and convention drift.

This repository turns those ideas into operational skills for coding agents. Instead of one long summary, it provides small skills that can be invoked directly or routed through one orchestrator.

## Skills

- [`apsd-software-design`](src/apsd-software-design/SKILL.md): routes general design, refactoring, and review work through the relevant APSD skills.
- [`apsd-complexity`](src/apsd-complexity/SKILL.md): treats change amplification, cognitive load, and obscurity as first-order design failures.
- [`apsd-deep-modules`](src/apsd-deep-modules/SKILL.md): prefers simple interfaces with hidden implementation power and rejects shallow pass-through layers.
- [`apsd-errors`](src/apsd-errors/SKILL.md): defines errors and special cases out of existence when possible, masks them low, and crashes only when recovery is dishonest.
- [`apsd-naming`](src/apsd-naming/SKILL.md): makes code obvious through precise names, predicates, and expectation-preserving structure.
- [`apsd-comments`](src/apsd-comments/SKILL.md): requires comments to explain abstractions, invariants, and non-obvious design intent instead of repeating code.
- [`apsd-general-purpose`](src/apsd-general-purpose/SKILL.md): prefers somewhat general-purpose interfaces over brittle one-off APIs or over-configured frameworks.
- [`apsd-design-process`](src/apsd-design-process/SKILL.md): enforces design-it-twice, interface comments first, and strategic improvement while changing code.
- [`apsd-consistency`](src/apsd-consistency/SKILL.md): uses conventions, invariants, and pattern reuse to reduce surprise and cognitive load.

## Use

Run `bash scripts/link_skills.sh` to symlink the skills into `~/.codex/skills`, `~/.claude/skills`, and `~/.agents/skills`.

This repository installs skill directories only. Shared global agent instructions belong in the sibling `../skills` repository, which can reference this skill set separately.

After linking, invoke a skill directly:

```text
Use apsd-deep-modules to review this API design.
```

or use the orchestrator:

```text
Use apsd-software-design to review this change for complexity and design quality.
```

## Validation

Run focused validation for changed skills:

```bash
direnv exec . bash scripts/validate_skills.sh apsd-deep-modules
```

Model-backed evals use [`scripts/skilpel.yaml`](scripts/skilpel.yaml), which sets target and judge temperature to `0`.

For local model-backed evals, put `OPENAI_API_KEY` in `.env`. The committed `.envrc` loads `.env` into the shell with direnv; `.env` is ignored by Git.

## Contributing

See [`docs/CONTRIBUTING.md`](docs/CONTRIBUTING.md) for the repository shape, required skill artifacts, and validation workflow.

## Versioning

The current version is recorded in `VERSION`.

See `CHANGELOG.md` for release history. Version tags use `vMAJOR.MINOR.PATCH`.

## License

MIT. See [`LICENSE`](LICENSE).

## Attribution

These skills are based on ideas from John Ousterhout's *A Philosophy of Software Design*. Eval passages are invented unless a skill's `references/notes.md` says otherwise.
