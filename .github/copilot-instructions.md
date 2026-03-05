# Copilot Instructions — Professional Operating System Framework

> **Audience:** Framework contributors and variant creators.
> If you are an end user of a specific profession variant, open that
> reference folder directly — its own `.github/copilot-instructions.md`
> will load instead.

## What This Repository Is

This repository is the **Professional Operating System (POS) Framework** — a meta-framework that defines the structural rules for building portable, markdown-based decision-support systems for any profession.

It contains:
- **`PROFESSION_SPEC.md`** — The formal specification all profession variants must follow
- **`scripts/bundle.sh`** — Parameterized bundle generator for any profession variant
- **`references/coach-os/`** — Career Coach OS reference implementation
- **`references/manager-os/`** — Engineering Manager OS reference implementation
- **`GENERATOR_PROMPT.md`** — (Planned) Meta-wizard for generating new profession variants

## Repository Structure

```
/
├── PROFESSION_SPEC.md        # The spec — read this first
├── GENERATOR_PROMPT.md       # AI meta-wizard for new variants (stub)
├── scripts/
│   └── bundle.sh             # Parameterized bundle generator
└── references/
    ├── coach-os/             # Career Coach OS (7-layer structure)
    └── manager-os/           # Engineering Manager OS (7-layer structure)
```

## Working with Reference Implementations

Each reference follows the 7-layer model defined in `PROFESSION_SPEC.md §3`:

| Folder | Layer | Purpose |
|--------|-------|---------|
| `00_BOOT/` | System manual | Onboarding, portability contract |
| `01_KERNEL/` | Portable core | Philosophy, decision protocol, personal DNA |
| `02_CONFIG/` | Environment | Practice/company-level context |
| `03_DRIVERS/` | Swappable | Client/team portfolio + entity cards |
| `04_PROCESSES/` | Ephemeral | Quarterly/tactical plan |
| `05_COMMANDS/` | Interface | Named AI commands + system prompt |
| `06_BOARDROOM/` | Advisory council | Virtual advisor persona definitions |

## Key Conventions

### Naming
- Framework: "Professional Operating System Framework" (abbreviated "POS Framework")
- Variants use ALLCAPS abbreviations: COS (Coach), MOS (Manager)
- File names: lowercase with underscores (`coach_operating_system.md`)

### bundle.conf Format
Each reference must have a `bundle.conf` at its root:
```
PROFESSION=coach
ABBREVIATION=COS
DISPLAY_NAME=Coach
```

### Running the Bundle Script
```bash
cd references/coach-os
bash scripts/bundle.sh
# Output: bundle/cos_compiled.md
```

## PROFESSION_SPEC.md Compliance

All reference implementations MUST satisfy `PROFESSION_SPEC.md §13` (Reference Implementation Checklist). When editing any reference:

1. Preserve the 7-layer folder structure
2. Keep `bundle.conf` in sync with `01_KERNEL/*_operating_system.md` filename
3. Maintain `Rule Zero` verbatim in the decision protocol (§6 of spec)
4. Ensure all commands include the required fields: `Trigger`, `Purpose`, `OS Files to Read`, `Ask User For`, `Critical Files for Freshness`, `Output Format`, `Chains With`
5. Keep `CHANGELOG.md` updated for any structural changes

## When Editing

- `PROFESSION_SPEC.md` — The rulebook. Changes here affect compliance requirements for all variants.
- `scripts/bundle.sh` — Must remain backward-compatible with both references.
- `references/*/` — Edit as independent repos; keep cross-references consistent within each.
- Never embed live client/team data in reference files — templates only.

## Adding a New Profession Variant

1. Copy an existing reference (e.g., `references/coach-os/`) to `references/<profession>-os/`
2. Update `bundle.conf` with new `PROFESSION`, `ABBREVIATION`, `DISPLAY_NAME`
3. Rename layer files to profession vocabulary (see `PROFESSION_SPEC.md §11`)
4. Run `bash scripts/bundle.sh` to verify
5. Validate against `PROFESSION_SPEC.md §13` checklist
6. Submit PR with updated root `CHANGELOG.md`
