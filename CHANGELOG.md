# Changelog

All notable changes to this repository are documented in this file.

This project uses SemVer. Version tags use the `vMAJOR.MINOR.PATCH` format.

## [Unreleased]

## [1.0.0] - 2026-06-28

### Changed

- Restructured the repository into a standalone skill project with `src/` skills, OpenAI metadata, evals, references, shared validation scripts, install linking, CI, and repository-local agent instructions.
- Rewrote the APSD material into focused operational skills and added `apsd-software-design` as an orchestrator for general design review and refactoring requests.
- Aligned installation with the `oiticica-style` model so this repository links skill directories only and does not host shared `home/AGENTS.md` instructions.
- Replaced hand-waved APSD eval examples with source-backed standard-library and language-project examples, and documented each example's source and interpretation in `references/notes.md`.
- Tightened APSD preserve-mode, error-contract, and router guidance so the full APSD skill suite passes model-backed validation deterministically against the source-backed eval set.
