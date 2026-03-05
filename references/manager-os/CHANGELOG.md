# Changelog

All notable changes to the Manager Operating System (MOS) framework will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), adapted for AI-executable version upgrades.

## How to Upgrade

When a new version is released:

1. Download the new MOS template files
2. Run the `version_upgrade` command in your AI copilot
3. The AI will read your current version, compare to the CHANGELOG, and walk you through the changes

The upgrade preserves all your existing data and only asks about new/changed sections.

---

## [Unreleased]

### Removed
- `LICENSE`, `AUTHORS.md`, `CONTACT.md`, `NOTICE`, `CONTRIBUTING.md`, `.gitignore` — consolidated to monorepo root. These files live at the root of `daviddgl/professional-operating-system` and apply to all references. Standalone repo retains its own copies.
- `01_KERNEL/manager_decision_protocol.md` §3 and §4 — expanded from stub to full spec-compliant content (re-entry rules, max iteration limit, Rule Zero override trigger, reversibility table with 7 examples, Pressure Mode interaction)

> Changes documented here will be included in the next version.

### Added

### Changed

### Removed

### Migration Steps

**For existing users upgrading to this version:**

---

## [2026.02] - 2026-02-14

**Initial Release** — First versioned release of the Manager Operating System framework.
