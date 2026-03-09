# Generation Sequence

Use this sequence to generate a new profession variant cleanly and with minimal backtracking.

## 1. Establish Naming First

Create and confirm:
- profession slug used in `references/<profession>-os/`
- display name
- abbreviation
- vocabulary map

Do not generate files before these are stable.

## 2. Separate Invariant Files From Variable Files

### Mostly Invariant Structure

These files preserve the same structural role across professions and should be adapted lightly, not reinvented:
- `00_BOOT/bootstrap_prompt.md`
- `05_COMMANDS/system_prompt.md`
- `ARCHITECTURE.md`
- `scripts/bundle.sh`

For these files:
- keep the role and workflow intact
- update file paths, profession names, and examples
- preserve the underlying framework logic

### Strongly Profession-Specific Files

These files require careful domain rewriting:
- `01_KERNEL/{profession}_operating_system.md`
- `01_KERNEL/{profession}_decision_protocol.md`
- `02_CONFIG/{context}_operating_system.md`
- `02_CONFIG/{context}_strategy.md`
- `03_DRIVERS/*`
- `04_PROCESSES/{plan_type}_plan.md`
- `05_COMMANDS/command_reference.md`
- `06_BOARDROOM/boardroom.md`
- `SETUP_WIZARD.md`

For these files:
- use reference structure
- replace vocabulary and examples fully
- redesign the logic where the profession differs materially

## 3. Generate in This Order

1. `bundle.conf`
2. `README.md`
3. `CHANGELOG.md`
4. `ARCHITECTURE.md`
5. `SETUP_WIZARD.md`
6. `00_BOOT/README.md`
7. `00_BOOT/bootstrap_prompt.md`
8. `01_KERNEL/{profession}_operating_system.md`
9. `01_KERNEL/{profession}_decision_protocol.md`
10. `01_KERNEL/personal_dna.md`
11. `02_CONFIG/{context}_operating_system.md`
12. `02_CONFIG/{context}_strategy.md`
13. `03_DRIVERS/{roster}_operating_system.md` or `{roster}_portfolio.md`
14. `03_DRIVERS/{entity}_card - [Name].md`
15. `04_PROCESSES/{plan_type}_plan.md`
16. `05_COMMANDS/command_reference.md`
17. `05_COMMANDS/system_prompt.md`
18. `06_BOARDROOM/boardroom.md`
19. `skills/` content if included
20. `scripts/bundle.sh`

## 4. File-Specific Guidance

### `bundle.conf`

Must define:
- `PROFESSION=`
- `ABBREVIATION=`
- `DISPLAY_NAME=`

### `SETUP_WIZARD.md`

Should be generated after vocabulary and major design choices are stable.

It should:
- follow the same interview rules as the references
- ask 3 to 5 questions per round
- move in phases
- output complete files
- avoid inventing missing data

### `01_KERNEL/{profession}_operating_system.md`

Use the shared section pattern from the references.

Redesign at minimum:
- values
- expectations
- capacity categories
- mode selector
- standards section
- pressure triggers
- external tools and memory notes

### `01_KERNEL/{profession}_decision_protocol.md`

Preserve the section skeleton:
- §0 Rule Zero
- §1 Hierarchy of Precedence
- §2 Interaction Rules
- §3 New Request Loop
- §4 Decision Speed

Only Rule Zero is verbatim. Everything else must be profession-specific and defensible.

### `05_COMMANDS/command_reference.md`

This is where shallow variants fail.

Ensure:
- command names sound native to the profession
- the files-to-read are specific
- output templates are useful in real work
- freshness requirements are not decorative

### `06_BOARDROOM/boardroom.md`

Map the six archetypes to figures who make sense for the profession.

Avoid generic celebrity substitutions unless they genuinely fit the operating logic.

## 5. Use Example Content Deliberately

The generated variant should be ready to personalize, not ready to use.

Where the file contains Tier 3 content, include:

`<!-- EXAMPLE CONTENT: Replace with your actual data using the Setup Wizard -->`

Use realistic placeholders that teach the user what good input looks like.

## 6. Final Validation Pass

Before stopping:
- compare the generated structure against both references
- run the compliance checklist
- verify naming consistency across file names, command names, and bundle values
- confirm the local `scripts/bundle.sh` path and output expectations still make sense