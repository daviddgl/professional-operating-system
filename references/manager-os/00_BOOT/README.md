# Manager Operating System (MOS) — [Your Name]

> **Layer:** BOOT  
> **Owner:** [Your Name]  
> **Version:** 2026.02  
> **Last Updated:** [YYYY-MM-DD]  
> **Portable:** Yes

---

## What Is This?

This repository is a **Manager Operating System (MOS)** — a decision-support framework that separates *how I think* (Kernel) from *where I work* (Config/Drivers) and *what I'm doing right now* (Processes).

**It is NOT a decision-maker.** It calculates trade-offs and surfaces the right context. Humans make the call. See **Rule Zero** in the Decision Protocol.

Prefer guided onboarding? Start with the root [SETUP_WIZARD.md](../SETUP_WIZARD.md).

---

## Architecture

```
┌─────────────────────────────────────────────────────┐
│  05_COMMANDS (Interface — how to interact)          │
│  ┌───────────────────────────────────────────────┐  │
│  │ command_reference          → Named            │  │
│  │                              operations       │  │
│  │ system_prompt              → AI copilot       │  │
│  │                              instructions     │  │
│  └───────────────────────────────────────────────┘  │
├─────────────────────────────────────────────────────┤
│  06_BOARDROOM (Portable — travels with you)         │
│  ┌───────────────────────────────────────────────┐  │
│  │ boardroom                  → Virtual advisory │  │
│  │                              council personas │  │
│  └───────────────────────────────────────────────┘  │
├─────────────────────────────────────────────────────┤
│  01_KERNEL (Portable — travels with you)            │
│  ┌────────────────────────────────────────────────┐ │
│  │ MOS                        → Philosophy,       │ │
│  │                              Standards, Values │ │
│  │ Decision Protocol          → Conflict          │ │
│  │                              Resolution Logic  │ │
│  │ personal_dna               → Identity, Goals,  │ │
│  │                              Constraints       │ │
│  └────────────────────────────────────────────────┘ │
├─────────────────────────────────────────────────────┤
│  02_CONFIG (Read Only — inherited from company)     │
│  ┌───────────────────────────────────────────────┐  │
│  │ company_operating_system   → Mission & Values │  │
│  │ company_strategy           → Current Goals    │  │
│  └───────────────────────────────────────────────┘  │
├─────────────────────────────────────────────────────┤
│  03_DRIVERS (Swappable — one per team)              │
│  ┌───────────────────────────────────────────────┐  │
│  │ team_operating_system      → Squad, Capacity, │  │
│  │                              Rituals, Partner │  │
│  │                              Teams            │  │
│  │ Player Cards               → Individual specs │  │
│  └───────────────────────────────────────────────┘  │
├─────────────────────────────────────────────────────┤
│  04_PROCESSES (Ephemeral — replaced quarterly)      │
│  ┌───────────────────────────────────────────────┐  │
│  │ tactical_plan              → Current roadmap  │  │
│  └───────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────┘
```

## File Reference Guide

Quick lookup for all template files in your MOS:

| File | Layer | Update Frequency | Purpose | Read By | Critical Sections |
| :--- | :--- | :--- | :--- | :--- | :--- |
| [personal_dna.md](../01_KERNEL/personal_dna.md) | KERNEL | Once (then review quarterly) | Your leadership identity, values, strengths, pressure triggers | All commands | §1–§7 (Identity, Pressure Mode detection) |
| [manager_operating_system.md](../01_KERNEL/manager_operating_system.md) | KERNEL | Once (evolve over career) | Your personal playbook: decision protocols, leadership modes, capacity model | All commands | §1–§13 (Complete decision framework) |
| [manager_decision_protocol.md](../01_KERNEL/manager_decision_protocol.md) | KERNEL | Once (refresh annually) | Conflict resolution logic, escalation matrix, Rule Zero | `stakeholder_request`, `escalate` | §0–§4 (Rule Zero, hierarchy, interaction rules, execution loops, decision speed) |
| [company_operating_system.md](../02_CONFIG/company_operating_system.md) | CONFIG | When company changes | Company mission, values, non-negotiables, org structure | `init_week`, `prep_121`, `prep_planning` | §1–§2 (Identity & Purpose, Core Values) |
| [company_strategy.md](../02_CONFIG/company_strategy.md) | CONFIG | Quarterly refresh | Q[N] strategy, OKRs, roadmap North Star, success metrics | `prep_planning`, `shutdown_week` | §1–§2 (Quarterly North Star, OKRs) |
| [team_operating_system.md](../03_DRIVERS/team_operating_system.md) | DRIVERS | Quarterly refresh | Team size, capacity model, rituals, norms, player rotation, partner teams | All commands | §1–§7 (Team structure, Capacity Contract, Partner Teams & Interfaces) |
| [player_card - [Name].md](../03_DRIVERS/player_card%20-%20%5BName%5D.md) | DRIVERS | Monthly refresh | Individual player profile, growth plan, on-call rotation | `prep_121`, `onboard` | §1–§3 (User Manual, Communication Preferences, Growth Goals) |
| [tactical_plan.md](../04_PROCESSES/tactical_plan.md) | PROCESSES | Every sprint | Current roadmap, team projects, milestone dates, dependencies | `init_week`, `init_day`, `shutdown_week` | §1–§2 (Roadmap, Risks) |
| [boardroom.md](../06_BOARDROOM/boardroom.md) | BOARDROOM | Quarterly review | Virtual advisory council — persona definitions, working principles, manager context | `boardroom` | §1–§3 (Overview, Chair, Personas) |

**Legend:**
- **Layer** = Which OS folder the file lives in (see Architecture above)
- **Update Frequency** = How often to refresh this file's content
- **Read By** = Which commands query this file (see Command Reference for details)
- **Critical Sections** = Which parts of the file are essential for decision-making

**New Manager Workflow:**
1. Start with `personal_dna.md` — define who you are (one-time)
2. Fill in `company_operating_system.md` + `company_strategy.md` — understand your context (once per company)
3. Create `team_operating_system.md` + Player Cards — map your team (once per team)
4. Build `tactical_plan.md` — set your roadmap for the quarter (quarterly)
5. Run commands (e.g., `init_week`) — they read all files autonomously and produce recommendations

**Updating File Headers:**

When you run `prep_refresh` or `quarterly_reset` to refresh your files, update the `Last Updated` field:

```markdown
> **Last Updated:** [YYYY-MM-DD]
```

**Do NOT update** for minor edits (typos, small tweaks). Only update when doing a proper file refresh cycle (quarterly review or when `prep_refresh` flags files as stale).

**Version field:** Maintained by the framework, not by you. It reflects the MOS template release version (e.g., `2026.02` for February 2026).

The file freshness validation system uses `Last Updated` dates to detect when files are stale based on their expected update frequency (weekly for `tactical_plan`, quarterly for team files, etc.).

**Upgrading to New Versions:**

When a new MOS version is released, you have two upgrade paths:

**Option A — Remote upgrade (recommended for Gem/GPT users):**
1. **Run** `version_upgrade --remote` in your AI copilot
2. The AI will browse the MOS GitHub repository to fetch the latest CHANGELOG and changed template files
3. **Follow migration steps** — AI walks through each change, preserving your data
4. **Confirm bundle generation** — AI produces a complete `mos_compiled.md` you paste directly into your Gem/GPT knowledge file

**Option B — Manual upgrade:**
1. **Download new version files** from repository (or `git pull` if tracking)
2. **Check** [`CHANGELOG.md`](../CHANGELOG.md) for what changed between your version and target
3. **Run** `version_upgrade [target_version]` in your AI copilot (e.g., `version_upgrade 2026.08`)
4. **Follow migration steps** — The AI will:
   - Read your current version from file headers
   - Show summary of changes (Added/Changed/Removed)
   - Walk through each migration step
   - Preserve all your existing data
   - Only ask about new/modified sections
   - Update `Version` field in affected files

> **Platform note:** Remote fetch (`--remote`) requires web browsing capability. Supported by Gemini (Google Search), ChatGPT (web browsing), and Claude (web tools). If browsing is unavailable, the command falls back to asking you to paste the CHANGELOG manually.

**Example upgrade flow:**

```
You: version_upgrade --remote

AI:
# Version Upgrade — 2026.02 → 2026.08
Source: Remote GitHub fetch

## Change Summary
- Added: New §14 in MOS (Decision Delegation Framework)
- Changed: Team OS §6 renamed to "Strategic Alignment"
- Removed: Deprecated old "Weekly Report" template

## Migration Plan
Step 1: Add §14 to MOS
  [Shows template fetched from GitHub, asks you to fill it]
Step 2: Rename Team OS §6
  [Shows diff, asks you to adapt]
...

Generate updated bundle for your Gem/GPT? (Y/N)
```

After upgrade, run `init_week` to verify the system works with updated files.

**Version checking:** Look at any file header — the `Version:` field shows your current MOS template version.

## The Portability Contract

**If you change teams:**
1. `/01_KERNEL/` — **Keep.** This is who you are as a leader.
2. `/02_CONFIG/` — **Keep** (unless changing companies).
3. `/03_DRIVERS/` — **Archive and replace.** Install new Team OS + Player Cards.
4. `/04_PROCESSES/` — **Delete and replace.** New tactical plan for new context.
5. `/05_COMMANDS/` — **Keep.** Commands are portable; they adapt to any team's data.
6. `/06_BOARDROOM/` — **Keep.** Your advisory council travels with you. Review personas quarterly.

## Logic vs. Data

| What | Where | Rule |
| :--- | :--- | :--- |
| **How we work** (Logic) | These Markdown files | Source of Truth for principles, protocols, and standards |
| **What we work on** (Data) | [Your task tracker] | Source of Truth for task status and execution |
| **What we plan** (Strategy) | [Your planning tool] | Source of Truth for roadmap visualization |
| **What we know** (Knowledge) | [Your wiki/docs] | Source of Truth for decisions and specs |
| **What we say** (Comms) | [Your chat tool] | Ephemeral — must be committed to task tracker or docs |

## Key Protocols

| Protocol | File | Purpose |
| :--- | :--- | :--- |
| **Commands** | Command Reference | Named operations — `init_week`, `prep_121`, `stakeholder_request`, etc. |
| **Rule Zero** | Decision Protocol §0 | Human override — when in doubt, talk face-to-face |
| **Capacity Contract** | MOS §3 + Team OS §4 | Protect roadmap from hidden ops work |
| **Pressure Mode** | MOS §12 | Self-management when stress compromises judgment |
| **Leadership Modes** | MOS §5 | Situational leadership selector (default: Coaching) |
| **The "No" Logic** | MOS §3 | How to negotiate/reject requests that break the plan |

## How to Use This System

### Manual Usage (Read the files)
1. **Daily:** Use the Kernel Decision Protocol for trade-off decisions. Check Pressure Mode indicators.
2. **Weekly:** Review Team OS capacity against actual ops load. Update Managing Up summary.
3. **Quarterly:** Replace Company Strategy file. Update Team OS Strategic Translation. Create new Tactical Plan.
4. **On team change:** Archive `/03_DRIVERS/` and `/04_PROCESSES/`. Create new Driver files.

### AI Copilot Integration (Recommended)

**Platform:** ChatGPT Project or Gemini Gem

**Setup (5 minutes):**
1. **Upload all OS files** to your AI platform
2. **Paste the System Prompt:** Copy `05_COMMANDS/system_prompt.md` into Custom Instructions
3. **Test:** Type `init_week` and verify the AI asks for team availability and produces the structured output

**Bundled Upload (Optional consolidation):**

If you prefer a single consolidated file instead of managing individual OS files, use the bundle script:

```bash
scripts/bundle.sh
```

This generates a single `mos_compiled.md` file in `bundle/` containing all MOS content (including `system_prompt.md`). Upload this one file + paste `00_BOOT/bootstrap_prompt.md` into Custom Instructions. Same functionality, simpler knowledge management.

**Platforms compared:**

| Feature | ChatGPT Project | Gemini Gem | Claude Project |
|---|---|---|---|
| Knowledge files (OS docs) | ✅ Up to 20 files, 512MB each | ✅ Supports bundled single file | ✅ Project knowledge files |
| Custom instructions | ✅ System Prompt (or Bootstrap Prompt for bundle) | ✅ System Prompt (or Bootstrap Prompt for bundle) | ✅ System Prompt (or Bootstrap Prompt for bundle) |
| Calendar integration | ❌ Must paste manually | ✅ Native Google Calendar | ❌ Must paste manually |
| Scheduling | ❌ Reactive only | ✅ Gemini Agent (experimental) | ❌ Reactive only |

**Recommendation:** Use individual files for easier editing/updates, or use `scripts/bundle.sh` for simplified single-file deployment. Both approaches work on all platforms.

---

*"This OS is a decision-support tool, not a decision-maker."*
