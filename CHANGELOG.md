# Changelog

All notable changes to this repository are documented in this file.

This project uses SemVer. Version tags use the `vMAJOR.MINOR.PATCH` format.

## [Unreleased]

### Changed

- Restructured the repository into a standalone skill project with `src/` skills, OpenAI metadata, evals, references, shared validation scripts, install linking, CI, and repository-local agent instructions.
- Rewrote the APSD material into focused operational skills and added `apsd-software-design` as an orchestrator for general design review and refactoring requests.
- Aligned installation with the `oiticica-style` model so this repository links skill directories only and does not host shared `home/AGENTS.md` instructions.
