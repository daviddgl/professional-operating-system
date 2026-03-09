# Compliance Checklist

Validate the generated profession variant against this checklist before calling it complete.

## Structure

- `references/<profession>-os/` exists
- All 7 required layers exist: `00_BOOT/` through `06_BOARDROOM/`
- `skills/` is present if the variant includes profession skills
- `scripts/` exists and includes `bundle.sh`

## Required Files

- `bundle.conf`
- `README.md`
- `CHANGELOG.md`
- `ARCHITECTURE.md`
- `SETUP_WIZARD.md`
- `00_BOOT/README.md`
- `00_BOOT/bootstrap_prompt.md`
- `01_KERNEL/{profession}_operating_system.md`
- `01_KERNEL/{profession}_decision_protocol.md`
- `01_KERNEL/personal_dna.md`
- `02_CONFIG/{context}_operating_system.md`
- `02_CONFIG/{context}_strategy.md`
- `03_DRIVERS/{roster}_operating_system.md` or `{roster}_portfolio.md`
- `03_DRIVERS/{entity}_card - [Name].md`
- `04_PROCESSES/{plan_type}_plan.md`
- `05_COMMANDS/command_reference.md`
- `05_COMMANDS/system_prompt.md`
- `06_BOARDROOM/boardroom.md`

## Header Compliance

Every generated markdown file starts with the required header structure:

```markdown
# [File Title]

> **Layer:** [LAYER_NAME]
> **Owner:** [Owner Name]
> **Version:** [YYYY.MM]
> **Last Updated:** [YYYY-MM-DD]
> **Portable:** [Yes — reason] / [No — reason]
```

## Kernel and Decision Protocol

- Rule Zero is copied verbatim
- Decision protocol contains §0 through §4
- Gate order is clear and defensible
- Override, conflict, and exception rules are defined
- Fast vs slow decisions include profession-specific examples

## Command System

- All five command categories from the spec are present
- Every command uses the exact required field structure
- Every command declares OS Files to Read
- Every command declares Ask User For inputs without inventing live data
- Freshness uses 🔴, 🟡, and 🟢 correctly
- Output Format is explicit and structured

## Boardroom

- Persona roster includes 4 to 8 personas, with 6 recommended
- Each persona includes worldview, focus areas, and two probing questions
- Working principles exist
- Activation logic exists
- Session format exists
- The profession chair block exists

## Tier Separation

- Tier 1 structure is preserved
- Tier 2 profession content is fully defined
- Tier 3 scaffolding is present but marked as example content where appropriate

## Bundling and Usability

- `bundle.conf` values match the profession naming
- `scripts/bundle.sh` is present and compatible with the reference structure
- `SETUP_WIZARD.md` can populate the user-specific files
- The variant is ready to bundle without additional structural edits

## Final Review Questions

1. Does this feel like a native system for the target profession rather than a renamed coach or manager variant?
2. Would a real professional in that role understand the command names immediately?
3. Are the pressure signals, gates, and personas specific enough to be useful?
4. Can the user personalize the variant cleanly using only the Setup Wizard?
5. Is anything still generic where the profession clearly needs sharper domain language?