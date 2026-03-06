# Changelog

All notable changes to the Coach Operating System (COS) framework will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), adapted for AI-executable version upgrades.

## How to Upgrade

When a new version is released:

1. Download the new COS template files
2. Run the `version_upgrade` command in your AI copilot
3. The AI will read your current version, compare to the CHANGELOG, and walk you through the changes

The upgrade preserves all your existing data and only asks about new/changed sections.

---

## [Unreleased]

### Removed

### Added
- **`skills/writing_voice.md`** — Writing Voice skill template (blank, ready for generation via `skills-library/writing-voice/generation_prompt.md`)

### Changed
- **`05_COMMANDS/system_prompt.md`** — Added `skills/` extension sidecar to architecture map; updated Portability Rules to include Skills; added Skills Activation rule for content generation tasks
- **`scripts/bundle.sh`** — Produces `bundle/skills_compiled.md` alongside main bundle when `skills/` contains files

---

## [2026.02] - 2026-02-26

**Initial Release** — First versioned release of the Coach Operating System framework.
