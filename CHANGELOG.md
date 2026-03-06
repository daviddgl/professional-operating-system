# Changelog — Professional Operating System Framework

All notable changes to the **framework specification** and **root-level files** are documented here. Changes to individual reference implementations are documented in their own `CHANGELOG.md` files.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

---

## [Unreleased]

> Changes documented here will be included in the next version.

### Added
- **§12 Extension System: Skills** — New spec section defining the skills plugin model: `skills/` sidecar directory, skill file format, skill types (Universal / Profession / Custom), the skills library structure, and bundle behaviour (`skills_compiled.md`)
- **`/skills-library/`** — Framework-root shared library with universal skill templates; first skill: Writing Voice (includes `README.md` and `generation_prompt.md`)
- **`scripts/bundle.sh`** — Skills compilation pass: produces `bundle/skills_compiled.md` when `skills/` directory contains files; updated deployment instructions, summary, and next steps output

### Changed
- **PROFESSION_SPEC.md §13** (was §12) — Professions That Fit: renumbered due to insertion of §12 Extension System
- **PROFESSION_SPEC.md §14** (was §13) — Reference Implementations: renumbered; added optional compliance check for `skills/` format

### Migration Steps

---

## [1.0] — 2026-03-04

**Initial release** — First version of the Professional Operating System framework.

### Framework Rules Established

- **MUST rules:** 7-layer model, portability contract, Rule Zero, file header standard, command format (all fields required), 5 command categories minimum, file freshness system
- **SHOULD rules (defaults):** 3 decision gates, 6 boardroom personas (range 4–8 acceptable)
- **Three-tier content model:** Tier 1 Structure (framework), Tier 2 Profession (generator), Tier 3 Personal (setup wizard)
