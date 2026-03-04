# Manager Operating System

A portable decision-support system for engineering managers.

Created by **David Garcia Lopez**.

> **Root folder purpose:** repository metadata + onboarding entry docs. The operating system content lives in `00_BOOT` to `06_BOARDROOM`.

- Contact: [CONTACT.md](CONTACT.md)
- Author details: [AUTHORS.md](AUTHORS.md)
- Contributing: [CONTRIBUTING.md](CONTRIBUTING.md)

> **Better decisions come from better preparation, not better intuition under pressure.**

---

## Start Here

1. Read [00_BOOT/README.md](00_BOOT/README.md) for architecture and portability rules
2. **(Optional — Visual learner?)** See [ARCHITECTURE.md](ARCHITECTURE.md) for diagrams of how the OS layers connect, when each layer is consulted, and how data flows
3. Run guided setup with [SETUP_WIZARD.md](SETUP_WIZARD.md)
4. Load [00_BOOT/bootstrap_prompt.md](00_BOOT/bootstrap_prompt.md) into your AI custom instructions

---

## The Problem

Engineering managers make high-stakes decisions under pressure, often isolated, without enough context, and with no reusable playbook. When you change teams or companies, you start from scratch.

## The Solution

**Manager Operating System** is a structured collection of markdown files organized as an operating system:

- **KERNEL** — Your portable philosophy, decision protocols, and standards. Travels with you.
- **CONFIG** — Company mission and strategy. Inherited context.
- **DRIVERS** — Team-specific: squad, capacity, rituals. Swapped when you change teams.
- **PROCESSES** — Current quarter's roadmap. Replaced quarterly.
- **COMMANDS** — Named operations that run via AI copilots (ChatGPT / Gemini / Claude).

The key idea: **separate the logic (how you decide) from the data (where you work)**. The logic is portable. The data is replaceable.

---

## Quick Start

### Option A: AI-Guided Setup (Recommended — ~45 min)

1. Open ChatGPT (or Gemini / Claude)
2. Paste [SETUP_WIZARD.md](SETUP_WIZARD.md) as the first message
3. Upload all MOS files from this repository
4. Type **`start setup`** — the AI interviews you and generates your completed files
5. Copy the generated files into your OS folder
6. Paste [05_COMMANDS/system_prompt.md](05_COMMANDS/system_prompt.md) into Custom Instructions (static — never changes)
7. Type `init_week` and you're live

### Option B: Manual Setup

1. Read [00_BOOT/README.md](00_BOOT/README.md) — architecture, portability contract, all protocols
2. Fill in the `[bracket]` placeholders in each file (guided by `<!-- comments -->`)
3. Upload all `.md` files to a **ChatGPT Project**, **Gemini Gem**, or **Claude Project**
4. Paste [05_COMMANDS/system_prompt.md](05_COMMANDS/system_prompt.md) into Custom Instructions (static — never changes)
5. Type `init_week` and you're live

---

## File Structure

```
Manager Operating System/
├── 00_BOOT/           # System manual & architecture
├── 01_KERNEL/         # Portable: philosophy, decision protocol, Personal DNA
├── 02_CONFIG/         # Company: mission, strategy
├── 03_DRIVERS/        # Team: squad, capacity, player cards
├── 04_PROCESSES/      # Quarter: tactical plan, risks
├── 05_COMMANDS/       # Interface: commands + AI system prompt
└── 06_BOARDROOM/      # Advisory council: portable persona definitions
```

---

## Commands

| Category | Commands |
|----------|----------|
| **Lifecycle** | `init_week` · `init_day` · `shutdown_day` · `shutdown_week` |
| **People** | `prep_121 [name]` · `onboard [name]` |
| **Execution** | `prep_planning` · `capacity_check` · `retro` |
| **Decisions** | `stakeholder_request` · `escalate` · `quarterly_reset` |
| **Boardroom** | `boardroom [topic]` |
| **Maintenance** | `prep_refresh` · `version_upgrade [target_version]` |

Each command tells the AI which files to read, what to ask you, and what structured output to produce. See [05_COMMANDS/command_reference.md](05_COMMANDS/command_reference.md) for full definitions.

**File Freshness:** Commands check if files need refreshing based on their `Last Updated` date. When you see staleness warnings, run `prep_refresh` to refresh stale files and update their `Last Updated` headers automatically.

---

## Portability

Change teams? Change companies?

1. **Keep** `01_KERNEL/` + `05_COMMANDS/` + `06_BOARDROOM/` (your decision logic + advisory council)
2. **Update** `02_CONFIG/` (new company context)
3. **Replace** `03_DRIVERS/` + `04_PROCESSES/` (new team + roadmap)

Your playbook travels with you.

---

## Upgrading

New MOS version released? Upgrade while preserving your data:

1. **Download** new version template files
2. **Check** [CHANGELOG.md](CHANGELOG.md) to see what changed
3. **Run** `version_upgrade [target_version]` in your AI copilot
4. **Follow** the migration steps — AI preserves all your content
5. **Verify** with `init_week` command

Example: `version_upgrade 2026.08`

The upgrade command reads your current version from file headers, applies changes incrementally, and only asks about new/modified sections. Your existing data stays intact.

**Current Version:** Check any file header for `Version:` field.

---

## How to Customize

1. Start with `01_KERNEL/` — write your management philosophy, values, and standards
2. Fill in `01_KERNEL/personal_dna.md` — your identity, goals, fears, patterns
3. Copy your company's mission/values into `02_CONFIG/`
4. Document your team in `03_DRIVERS/` — squad, capacity, rituals
5. Create Player Cards for each team member
6. Write your quarterly plan in `04_PROCESSES/`
7. Upload everything to an AI copilot and test with `init_week`

Each file has instructions and placeholders marked with `[brackets]`.

---

## Documentation

All details live in [00_BOOT/README.md](00_BOOT/README.md):
- Architecture diagram
- Portability contract
- Logic vs. Data separation
- Key protocols (Rule Zero, Decision Protocol, Capacity Contract, Pressure Mode)
- AI platform setup and comparison
- Full command list with chaining

---

## License

MIT — see [LICENSE](LICENSE).
