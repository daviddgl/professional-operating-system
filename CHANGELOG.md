# Changelog — Professional Operating System Framework

All notable changes to the **framework specification** and **root-level files** are documented here. Changes to individual reference implementations are documented in their own `CHANGELOG.md` files.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

---

## [Unreleased]

> Changes documented here will be included in the next version.

### Added

### Changed

### Removed

### Migration Steps

---

## [1.0] — 2026-03-04

**Initial release** — First version of the Professional Operating System framework.

### Added

- `PROFESSION_SPEC.md` — The formal specification defining all structural rules for profession variants (13 sections covering layers, portability, file headers, Rule Zero, decision protocol, commands, boardroom, freshness system, vocabulary, and reference implementations)
- `GENERATOR_PROMPT.md` — Meta-wizard for creating new profession variants via AI interview (stub — to be implemented)
- `scripts/bundle.sh` — Parameterized bundle generator that works for any profession via `bundle.conf` auto-detection
- `references/coach-os/` — Career Coach OS reference implementation (v2026.02)
- `references/manager-os/` — Engineering Manager OS reference implementation (v2026.02)
- `bundle.conf` added to both reference implementations for explicit profession identification
- Root `README.md`, `CONTRIBUTING.md`, `LICENSE`, `AUTHORS.md`, `CONTACT.md`, `CHANGELOG.md`

### Framework Rules Established

- **MUST rules:** 7-layer model, portability contract, Rule Zero, file header standard, command format (all fields required), 5 command categories minimum, file freshness system
- **SHOULD rules (defaults):** 3 decision gates, 6 boardroom personas (range 4–8 acceptable)
- **Three-tier content model:** Tier 1 Structure (framework), Tier 2 Profession (generator), Tier 3 Personal (setup wizard)
