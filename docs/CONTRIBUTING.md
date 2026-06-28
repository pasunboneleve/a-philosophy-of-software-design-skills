# Contributing

This repository packages focused Codex skills derived from John Ousterhout's *A Philosophy of Software Design*.

## Repository shape

Each skill must include:

- `src/<skill-name>/SKILL.md`
- `src/<skill-name>/agents/openai.yaml`
- `src/<skill-name>/evals/evals.yaml`
- `src/<skill-name>/references/notes.md`

Every skill must be linked from the root `README.md`.

## Skill rules

- Keep `SKILL.md` concise and operational.
- Put behavior in `SKILL.md`, not in the eval prompt.
- Include positive and negative eval cases for behavior-changing skills.
- Design evals as skill-ablation tests: with-skill runs should pass near 100%, and without-skill runs should fail near 0%.
- Use assertions that test behavior rather than exact wording unless wording is the behavior under test.

## Validation

Use focused validation for changed skills:

```bash
direnv exec . bash scripts/validate_skills.sh apsd-complexity
```

Run full validation only when shared scripts, CI, or cross-cutting skill infrastructure changes.

For script changes, also run:

```bash
bash -n scripts/*.sh
```

For local model-backed evals, put `OPENAI_API_KEY` in `.env`. The committed `.envrc` loads `.env` into the shell with direnv; `.env` is ignored by Git.
