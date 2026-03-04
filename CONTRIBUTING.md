# Contributing to Professional Operating System

Thanks for your interest in improving the Professional Operating System framework.

## Contribution Types

### 1. Improve the Framework Specification
Improvements to `PROFESSION_SPEC.md` or `GENERATOR_PROMPT.md` — structural rules, vocabulary clarifications, missing edge cases.

### 2. Improve a Reference Implementation
Bug fixes, clarity improvements, or new commands for `references/manager-os/` or `references/coach-os/`. Both must stay compliant with `PROFESSION_SPEC.md`.

### 3. Submit a New Profession Variant
Add a new fully-spec-compliant profession to `references/`. Requirements:
- Built using `GENERATOR_PROMPT.md` (preferred) or hand-crafted
- Passes all checks in the `PROFESSION_SPEC.md §13` compliance checklist
- Tested by at least one person who actually works in that profession
- Includes a `SETUP_WIZARD.md`, `CHANGELOG.md`, and `bundle.conf`

## How to Contribute

1. Fork the repository
2. Create a branch for your change (`feat/improve-spec`, `feat/add-pm-os`, etc.)
3. Make focused, incremental changes
4. Update `CHANGELOG.md` in the affected repo (see CHANGELOG requirements below)
5. Open a pull request with:
   - What problem you are solving
   - What changed
   - Which spec compliance checks you verified
   - Any trade-offs or alternatives considered

## CHANGELOG Requirements

**Every framework or reference implementation change must be documented in the appropriate `CHANGELOG.md` before committing.**

- Changes to `PROFESSION_SPEC.md` or root files → document in root `CHANGELOG.md` (create if absent)
- Changes to a reference implementation → document in that reference's `CHANGELOG.md`

Use these categories:
- `### Added` — New files, commands, sections, features
- `### Changed` — Renamed sections, modified structure, updated commands
- `### Removed` — Deprecated features, deleted content
- `### Migration Steps` — Instructions for existing users upgrading (if breaking change)

**Why this matters:** Profession OS users upgrade via the `version_upgrade` command, which reads `CHANGELOG.md` to apply updates while preserving their personal data. Missing entries = broken upgrades for real users.

## Style Guidelines

- Plain markdown only — no external dependencies, no tooling beyond bash scripts
- Preserve the `{placeholder}` convention for user-specific content
- Use `<!-- HTML comments -->` for inline guidance to users filling templates
- Mark example/template content clearly with: `<!-- EXAMPLE CONTENT: Replace via Setup Wizard -->`
- Keep language practical and concise
- Preserve section numbering in KERNEL files (§1–§N) — they are cross-referenced across many files

## What We Don't Accept

- CLI frameworks, template engines, or tooling beyond bash scripts
- Tool integrations (MCP, API connections to Slack/Jira/etc.) — this is a separate effort
- New structural layers beyond the 7-layer model
- Command formats that deviate from the `PROFESSION_SPEC.md §8.1` template
- Private or company-specific data in any committed file

## Questions

- Email: daviddgl@gmail.com
- GitHub: https://github.com/daviddgl
