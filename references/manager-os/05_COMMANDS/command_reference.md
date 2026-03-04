# Command Reference

> **Layer:** COMMANDS  
> **Owner:** [Your Name]  
> **Version:** 2026.02  
> **Last Updated:** [YYYY-MM-DD]  
> **Portable:** Yes

---

**Purpose:** This file defines the Manager Operating System (MOS) command layer — named operations that an AI copilot executes using the OS files as context. Commands are structured prompts that tell the AI which files to read, what questions to ask, and what output to produce.

**How to use:** Type the command name (e.g., `init_week`) in your AI conversation. The AI reads this reference, loads the specified OS files, asks for missing inputs, and produces the structured output.

---

## Command Categories

1. **Lifecycle** — Daily and weekly bookends (init/shutdown cycles)
2. **People** — Team member interactions (1:1s, onboarding)
3. **Execution** — Planning and capacity management
4. **Decision Support** — Stakeholder requests, escalations, and boardroom advisory sessions
5. **Maintenance** — System refresh and file updates

---

## 📋 LIFECYCLE COMMANDS

### `init_week`

**Trigger:** Monday morning
**Purpose:** Prepare for the week ahead

**OS Files to Read:**
- `04_PROCESSES/tactical_plan.md` — §1 Roadmap (filter by this week's dates), §2 Risks
- `03_DRIVERS/team_operating_system.md` — §2 Squad (capacity board), §4 Capacity Contract, §5 Rituals (which ones this week?), §6 Strategic Translation, §7 Partner Teams (cross-team sync opportunities)
- `02_CONFIG/company_strategy.md` — §1 North Star
- `01_KERNEL/manager_operating_system.md` — §8 Managing Up (exec summary template), §9 Success Metrics, §12 Pressure Mode (baseline check)
- `01_KERNEL/personal_dna.md` — Goals (Top 3 for 90 days)
- **All player_cards** — §3 Growth Goals

**Ask User For:**
- Team availability/PTO this week
- Carryover items from last week's `shutdown_week` output
- Any known blockers or schedule changes

**Critical Files for Freshness:**
- 🔴 `tactical_plan.md` — 0-day grace (must be updated this week)
- 🟡 `team_operating_system.md` — 3-day grace (quarterly refresh)
- 🟡 `company_strategy.md` — 3-day grace (quarterly refresh)

**Output Format:**
```
# Week of [Date]

## Priorities (Ranked)
1. [Priority based on Tactical Plan + North Star alignment]
2. [...]
3. [...]

## Per-Person Focus
- **[Name]:** [Task from Tactical Plan] (Growth goal: [from Player Card])
- [...]

## Risk Watchlist
- [Risk from Tactical Plan §2 relevant this week]

## Rituals This Week
- [List from Team OS §5]

## Capacity Pre-Check
- **Contracted:** [X/Y from Team OS §4] (Features/Ops)
- **Watch for:** [Any constraint from Squad table]

## Friday Exec Summary (Draft Skeleton)
- **Roadmap Status:** [Prepare Red/Yellow/Green for Friday]
- **Top Risk:** [To be updated Friday]
- **The Ask:** [To be determined]

## Pressure Mode Baseline
- [ ] Stress indicators self-check
```

**Chains With:** Previous `shutdown_week` (carryover) → This command → This week's `shutdown_week`

---

### `init_day`

**Trigger:** Each morning
**Purpose:** Prepare for today

**OS Files to Read:**
- `04_PROCESSES/tactical_plan.md` — §1 (filter by today's date)
- `03_DRIVERS/team_operating_system.md` — §5 Rituals
- `01_KERNEL/manager_operating_system.md` — §4 Communication Protocol (Meeting Filter), §12 Pressure Mode (Activation Triggers)
- `01_KERNEL/personal_dna.md` — Constraints & Fears

**Ask User For:**
- Today's calendar (list of meetings)
- Any overnight updates or blockers
- Carryover from yesterday's `shutdown_day` output

**Critical Files for Freshness:**
- 🔴 `tactical_plan.md` — 0-day grace (must be current)
- 🟡 `team_operating_system.md` — 3-day grace (quarterly refresh)

**Output Format:**
```
# [Day of Week], [Date]

## Top 3 Priorities
1. [From Tactical Plan + init_week priorities]
2. [...]
3. [...]

## Pressure Mode Self-Assessment
- [ ] Making decisions without applying the Decision Protocol?
- [ ] Saying yes to avoid conflict?
- [ ] Skipping Kernel process?
- [ ] Working excessive hours for non-P0?
- [ ] Avoiding difficult conversations?
- [ ] Feeling isolated with decisions?

**Status:** [0-1 = OK | 2+ = ACTIVATE PRESSURE MODE]

## Meeting Audit
| Meeting | Agenda? | Outcome? | Async Alternative? | **KEEP/DECLINE** |
|---------|---------|----------|-------------------|------------------|
| [Name]  | [Y/N]   | [Y/N]    | [Y/N]             | [Decision]       |

## Standup Draft
- **Done yesterday:** [...]
- **Today:** [Top 3 priorities]
- **Blockers:** [None / or list]

## Carryover from Yesterday
- [Items from shutdown_day]
```

**Chains With:** Previous `shutdown_day` (carryover) → This command → Today's `shutdown_day`

---

### `shutdown_day`

**Trigger:** End of day
**Purpose:** Wrap up and prepare for tomorrow

**OS Files to Read:**
- `01_KERNEL/manager_operating_system.md` — §4 Communication Protocol (Output Rule), §9 Success Metrics (Work-Life Boundary), §12 Pressure Mode (Recovery)
- `01_KERNEL/personal_dna.md` — Constraints & Fears (avoidance check)

**Ask User For:**
- What got done today vs. `init_day` priorities
- Open threads or decisions pending
- Any meetings today without Decision Logs or Action Items
- Any feedback given or received

**Critical Files for Freshness:**
- ✅ All files are reference-only; no freshness requirements

**Output Format:**
```
# End of Day — [Date]

## Done / Not Done / Blocked
- ✅ **Done:** [List]
- ⏸️ **Not Done (carryover):** [List]
- 🚫 **Blocked:** [List + blocker details]

## Open Items for Tomorrow
1. [Item]
2. [...]

## Meeting Output Audit
- [Meeting X]: Decision Log ✅ | Action Items ✅
- [Meeting Y]: ⚠️ Missing outcomes (follow up needed)

## Pressure Mode End-of-Day Check
**Decisions made under pressure today:**
- [None / or list with: What → Why → Review at 24h?]

**Decompression:**
- [ ] Any difficult conversations avoided? (Schedule for tomorrow)
- [ ] Any "just this once" exceptions granted? (Pattern log candidate)

## Work-Life Boundary
**Time to stop:** [Recommend based on hours worked + P0 status]
- [ ] No P0s pending → **GO HOME** 🏡
```

**Chains With:** Today's `init_day` (priorities) → This command → Tomorrow's `init_day` (carryover)

---

### `shutdown_week`

**Trigger:** Friday afternoon
**Purpose:** Close the week and prepare executive summary

**OS Files to Read:**
- `01_KERNEL/manager_operating_system.md` — §8 Managing Up ("No Surprises" template), §9 Success Metrics, §12 Pressure Mode (Recovery + Pattern Log)
- `03_DRIVERS/team_operating_system.md` — §4 Capacity Contract (Circuit Breaker check)
- `04_PROCESSES/tactical_plan.md` — §1 Roadmap (planned vs actual), §2 Risks
- `02_CONFIG/company_strategy.md` — §1 North Star
- `01_KERNEL/personal_dna.md` — Success Metrics

**Ask User For:**
- Ops tickets vs feature tickets this week (count or hours)
- Any incidents or production issues
- Team morale pulse
- What from `init_week` was completed vs not
- Last week's ops ratio (for Circuit Breaker 2-week trend)

**Critical Files for Freshness:**
- 🔴 `tactical_plan.md` — 0-day grace (compare planned vs actual)
- 🟡 `team_operating_system.md` — 3-day grace (Capacity Contract + Circuit Breaker)
- 🟡 `company_strategy.md` — 3-day grace (North Star check)

**Output Format:**
```
# Week of [Date] — CLOSED

## "No Surprises" Executive Summary (Ready to Send)

**To:** [Your manager / leadership]
**Subject:** Weekly Update — [Team Name]

**Roadmap Status:** 🟢 Green / 🟡 Yellow / 🔴 Red
- **Completed:** [List items from tactical_plan]
- **In Progress:** [List]
- **Blocked/Delayed:** [List with reason]

**Top Risk:** [Risk from tactical_plan or new risk identified]
- **Mitigation:** [Action being taken]

**The Ask:** [What you need from leadership]

---

## Ops Ratio Report
- **This week:** [X]% ops / [Y]% features
- **Contracted:** [From Team OS §4]
- **Last week:** [X]% ops (for trend)
- **Circuit Breaker Status:** [OK / ⚠️ TRIGGERED (2 weeks exceeding contract)]

**If triggered:**
> Recommended action: Pause [lowest priority roadmap item] to address [root cause of ops overflow]
> Pre-filled negotiation script from MOS §3

## North Star Contribution
**Goal:** [From company_strategy §1]
**This week's contribution:** [How did completed work serve this goal?]

## Carryover for Monday
1. [Incomplete items from init_week]
2. [New blockers to address]

## Pressure Mode Weekly Review
**Patterns observed:**
- [Any repeated stress scenarios? Add to Pattern Log in MOS §12]
```

**Chains With:** This week's `init_week` (comparison) → This command → Next Monday's `init_week` (carryover)

---

## 👥 PEOPLE COMMANDS

### `prep_121 [name]`

**Trigger:** Before 1:1 meeting with team member
**Purpose:** Prepare personalized agenda

**OS Files to Read:**
- `03_DRIVERS/player_card - [name].md` — §1 User Manual, §2 Communication Preferences, §3 Growth Goals
- `03_DRIVERS/team_operating_system.md` — §2 Squad (person's allocation)
- `04_PROCESSES/tactical_plan.md` — §1 (tasks assigned to this person)
- `01_KERNEL/manager_operating_system.md` — §5 Leadership Mode Selector, §6 Feedback Loop, §2 Team Expectations
- `01_KERNEL/personal_dna.md` — Constraints & Fears (avoidance tendency)

**Ask User For:**
- Previous 1:1 notes / action items
- Pending feedback (positive or constructive)
- Any performance concerns or wins
- Blockers this person has raised

**Critical Files for Freshness:**
- 🜟 `player_card - [name].md` — 7-day grace (monthly refresh)
- 🔴 `tactical_plan.md` — 0-day grace (for current work assignment)

**Output Format:**
```
# 1:1 Agenda — [Name]

## Context
- **Role:** [From Player Card]
- **Allocation:** [From Team OS Squad table]
- **Current work:** [From Tactical Plan]

## Leadership Mode
**Recommended:** [Coaching / Commanding / Visionary / Affiliative / Democratic]
**Why:** [Based on situation from user input]

## Agenda

### 1. Growth Goal Check-In
**Current Goal:** [From Player Card §3]
**Questions:**
- How are you feeling about progress on [goal]?
- What support do you need from me?
- [Current work from Tactical Plan] — does this help you practice [goal skill]?

### 2. Feedback (Radical Candor)

**Positive (Praise Individual):**
- [Specific example with impact]

**Constructive (if any):**
- **Observation:** [Concrete behavior — MOS §6 specificity rule]
- **Impact:** [What happened because of it]
- **Request:** [What to do differently]

**Format per Player Card:** [From §1 — how they prefer to receive feedback]

### 3. Inbound Question (Standard)
> "What is one thing I'm doing that is slowing you down?"

### 4. Open Action Items
- [From previous 1:1]

### 5. Current Blockers
- [From user input]

## Self-Awareness Flag
- [ ] Am I avoiding a difficult conversation? (Constraints & Fears check)
```

---

### `onboard [name]`

**Trigger:** New team member joining
**Purpose:** Generate welcome materials and Player Card

**OS Files to Read:**
- `03_DRIVERS/player_card - [Name].md` — Template structure
- `03_DRIVERS/team_operating_system.md` — §1 Identity & Mission, §2 Squad, §3 Principles, §4 Capacity Contract, §5 Rituals
- `01_KERNEL/manager_operating_system.md` — §1 Core Philosophy, §2 Team Expectations, §5 Leadership Mode (Coaching), §6 Feedback Loop, §10 Engineering Standards
- `02_CONFIG/company_operating_system.md` — §1 Identity, §2 Core Values
- `02_CONFIG/company_strategy.md` — §1 North Star
- `04_PROCESSES/tactical_plan.md` — §1 Roadmap
- `01_KERNEL/personal_dna.md` — Identity

**Ask User For:**
- New hire's name, role, timezone
- Background / experience level
- Strengths (if known from interview)
- Communication preferences
- First-week goals

**Critical Files for Freshness:**
- 🟡 `team_operating_system.md` — 3-day grace (team context)
- 🟡 `company_strategy.md` — 3-day grace (company goals)
- 🔴 `tactical_plan.md` — 0-day grace (first tasks)

**Output Format:**
```
# Onboarding — [Name]

## Draft Player Card
[Generate from template with user input filled in §1 and §2; §3 Growth Goals to define together in first 1:1]

## Updated Squad Table
| Resource | Role | Allocation | Focus Area |
|----------|------|------------|------------|
| [Existing team...] |
| **[Name]** | [Role] | [%] | [Area from user input] |

## Welcome Brief (Share with [Name])

### Who We Are
[From Team OS §1]

### What We're Building Right Now
[From Tactical Plan §1]

### How We Work
**Core Principles:** [From Team OS §3]
**Capacity Contract:** [From Team OS §4]
**Rituals:** [From Team OS §5]
**Engineering Standards:** [From MOS §10]

### My Leadership Style
[From MOS §1 — Purpose + Core Values summary]
**Expectations:** [From MOS §2]
**Feedback:** [From MOS §6]

### Company Context
**Mission:** [From Company OS §1]
**Current Goal:** [From Company Strategy §1]

### First Week Agenda
- **Day 1:** Team intro, tool access
- **Day 2-3:** Codebase walkthrough, read key docs
- **Day 4-5:** [Suggested starter task from Tactical Plan]
- **End of week:** First 1:1 (define Growth Goals)

## Leadership Mode
**For onboarding:** Coaching (default)
```

---

## ⚙️ EXECUTION COMMANDS

### `prep_planning`

**Trigger:** Before sprint planning meeting
**Purpose:** Prepare sprint scope with capacity applied

**OS Files to Read:**
- `04_PROCESSES/tactical_plan.md` — §1 Roadmap (what's next), §2 Risks
- `03_DRIVERS/team_operating_system.md` — §2 Squad (capacity + constraints), §4 Capacity Contract, §6 Strategic Translation (priority logic), §7 Partner Teams (surface dependencies)
- `02_CONFIG/company_strategy.md` — §1 North Star
- `01_KERNEL/manager_decision_protocol.md` — §1 Hierarchy of Precedence, §3 New Task Loop
- `01_KERNEL/manager_operating_system.md` — §10 Engineering Standards (Spec-Driven)
- **All player_cards** — §1 Superpower, §3 Growth Goals

**Ask User For:**
- Backlog items (candidate tickets for sprint)
- Sprint length (weeks)
- Carryover from previous sprint
- Current ops queue size (estimate)
- Team availability (PTO, focus days)

**Critical Files for Freshness:**
- 🔴 `tactical_plan.md` — 0-day grace (roadmap planning)
- 🟡 `team_operating_system.md` — 3-day grace (capacity + constraints)
- 🟡 `company_strategy.md` — 3-day grace (North Star alignment)

**Output Format:**
```
# Sprint Planning — [Sprint Name/Date]

## Capacity Calculation
**Sprint length:** [X weeks]
**Team size:** [Y people] (adjusted for constraints from Squad table)
**Total capacity:** [Hours/Points]
**Reserved for ops:** [From Team OS §4 contract]
**Available for features:** [Remaining]

## Suggested Sprint Scope (Contract Applied)

### Features
| Ticket | Owner | Estimate | Rationale |
|--------|-------|----------|-----------|
| [Item from Tactical Plan] | [Name — matched to Player Card] | [Est] | [North Star alignment] |

### Ops Reserved
- Bug fixes (queue size: [from user input])
- On-call rotation
- Maintenance / buffer

## Task-to-Person Assignment
**[Person 1]:**
- [Task A] — matches Superpower: [from Player Card §1]
- [Task B] — advances Growth Goal: [from Player Card §3]
[Repeat for each person...]

## Dependency Map
- [Task X] blocks [Task Y]
- [Resource constraints from Squad table]

## Risk Flags
- [From Tactical Plan §2]

## Items Needing Specs (Engineering Standards)
- [Complex items requiring spec before sprint entry]

## Alignment Check
**North Star:** [From Company Strategy §1]
**This sprint contributes:** [How]
```

---

### `capacity_check`

**Trigger:** Any time ops work feels overwhelming
**Purpose:** Calculate ratio and trigger Circuit Breaker if needed

**OS Files to Read:**
- `03_DRIVERS/team_operating_system.md` — §4 Capacity Contract (ratio + Circuit Breaker), §2 Squad (bottleneck identification), §7 Partner Teams (cross-team work consuming capacity)
- `01_KERNEL/manager_operating_system.md` — §3 Capacity Contract (negotiation script), §8 Managing Up (Solution Rule)
- `04_PROCESSES/tactical_plan.md` — §1 Roadmap (what's at risk)
- `01_KERNEL/manager_decision_protocol.md` — §2 Rule B (Conflict Function)

**Ask User For:**
- Current period data (ops ticket count vs feature ticket count, or hours)
- Previous period ops ratio (for 2-period trend)
- Any incidents consuming time

**Critical Files for Freshness:**
- 🟡 `team_operating_system.md` — 3-day grace (Capacity Contract, Circuit Breaker)
- 🔴 `tactical_plan.md` — 0-day grace (roadmap at risk)

**Output Format:**
```
# Capacity Check — [Date]

## Current Ratio
- **Features:** [X]%
- **Ops:** [Y]%

**Contracted:** [From Team OS §4]
**Status:** [✅ Within contract / ⚠️ Ops elevated / 🚨 Breached]

## Trend Analysis
- **Last period:** [X]% ops
- **This period:** [Y]% ops
- **Circuit Breaker:** [OK / ⚠️ TRIGGERED (2 consecutive periods exceeding contract)]

## Bottleneck Analysis
[From Squad table — which resources are maxed out?]

## If Circuit Breaker Triggered

### Recommended Action
**Pause:** [Lowest priority roadmap item from Tactical Plan §1]
**Reason:** Address root cause of ops overflow
**Root cause:** [Analyze from ticket data]

### Pre-Filled Negotiation Script
[From MOS §3 — populated with current numbers]

### Escalation Brief (If Needed)
[Use Managing Up Solution Rule template from MOS §8]
```

---

### `retro`

**Trigger:** Per team retrospective cadence
**Purpose:** Prepare retrospective agenda

**OS Files to Read:**
- `03_DRIVERS/team_operating_system.md` — §5 Rituals (retro format), §4 Capacity Contract (ops ratio review), §6 Strategic Translation
- `04_PROCESSES/tactical_plan.md` — §1 Roadmap (planned vs actual), §2 Risks
- `01_KERNEL/manager_operating_system.md` — §6 Feedback Loop, §5 Leadership Mode (Democratic), §7 Failure Protocol (Safe Fail), §1 Core Values
- `02_CONFIG/company_operating_system.md` — §2 Core Values

**Ask User For:**
- Sprint metrics (velocity, completion rate)
- What went well (specific examples)
- What went poorly (specific examples)
- Previous retro action items and their status
- Any incidents or production issues

**Critical Files for Freshness:**
- 🔴 `tactical_plan.md` — 0-day grace (planned vs actual)
- 🟡 `team_operating_system.md` — 3-day grace (team context)

**Output Format:**
```
# Retro Agenda — [Period]

## Ground Rules (Reminder)
- Attack problems, not people
- Everyone's input needed (Democratic mode — MOS §5)
- [Team-specific principles from Team OS §3]

## Data Summary
**Planned vs Delivered:**
- Completion rate: [X]%

**Ops Ratio:**
- This period: [X]% ops / [Y]% features
- Within contract? [Yes/No]

## Previous Action Items (Status Check)
- [Action 1]: [Done / In Progress / Not Started]

## Discussion Prompts
### What Went Well? (Celebrate)
### What Went Poorly? (Improve)
### Trade-Off Evaluation (Strategic Translation)
### Safe-Fail Experiments (Failure Protocol)

## Action Items (To Define in Meeting)
- [Team will create these]
```

---

## 🎯 DECISION SUPPORT COMMANDS

### `stakeholder_request [description]`

**Trigger:** When a stakeholder asks for something
**Purpose:** Run Decision Protocol and produce recommendation

**OS Files to Read:**
- `01_KERNEL/manager_decision_protocol.md` — §1 Hierarchy of Precedence (all 3 levels), §2 Interaction Rules, §3 New Task Loop, §4 Decision Speed
- `03_DRIVERS/team_operating_system.md` — §4 Capacity Contract, §2 Squad, §7 Partner Teams (context for requesting team)
- `02_CONFIG/company_strategy.md` — §1 North Star
- `04_PROCESSES/tactical_plan.md` — §1 Roadmap (what gets displaced?)
- `01_KERNEL/manager_operating_system.md` — §3 The "No" Logic
- **All player_cards** — §1 Superpower, §3 Growth Goals

**Ask User For:**
- Full description of the request
- Who is requesting (stakeholder + priority level they claim)
- Estimated effort
- Current sprint capacity utilization
- Is this reversible or irreversible?

**Critical Files for Freshness:**
- 🔴 `manager_decision_protocol.md` — 30-day grace (conflict logic)
- 🟡 `company_strategy.md` — 3-day grace (North Star gate)
- 🟡 `team_operating_system.md` — 3-day grace (Capacity Contract gate)
- 🔴 `tactical_plan.md` — 0-day grace (roadmap displacement)

**Output Format:**
```
# Decision Protocol — Stakeholder Request

## Request Summary
- **Request:** [Description]
- **Requester:** [Name + Priority claim]
- **Estimate:** [Effort]
- **Reversible?** [Yes/No — from Decision Speed §4]

---

## Gate 1: Team Capacity (Level 1)
**Check:** Current sprint utilization + Capacity Contract
**Result:** [✅ PASS / ❌ FAIL]

**If FAIL → Invoke "No" Logic:**
- Is this P0? [Yes → ACCEPT / No → NEGOTIATE]
- Negotiation script from MOS §3

---

## Gate 2: Company Strategy (Level 2)
**North Star:** [From Company Strategy §1]
**Analysis:** [How does this serve/hurt the goal?]
**Result:** [✅ ALIGNED / ⚠️ NEUTRAL / ❌ MISALIGNED]

---

## Gate 3: Individual Match (Level 3)
| Person | Superpower Match | Growth Match | Current Load | **Score** |
|--------|------------------|--------------|--------------|-----------|
| [Name] | [Y/N] | [Y/N] | [%] | [H/M/L] |

**Best match:** [Name]

---

## RECOMMENDATION: [ACCEPT / NEGOTIATE / REJECT]

### If ACCEPT
- Assign to: [Name] | Swap out: [Roadmap item]

### If NEGOTIATE
[Pre-filled script from MOS §3 with current numbers]

### If REJECT
[Reason + constructive communication using MOS §8 Solution Rule]

---

## Rule Zero Check
- [ ] Is this decision ambiguous? → Recommend synchronous conversation
```

---

### `escalate [topic]`

**Trigger:** When you need to escalate to leadership
**Purpose:** Prepare professional escalation with data

**OS Files to Read:**
- `01_KERNEL/manager_operating_system.md` — §3 The "No" Logic, §8 Managing Up (Solution Rule), §5 Leadership Mode
- `01_KERNEL/manager_decision_protocol.md` — §0 Rule Zero, §1 Hierarchy of Precedence, §4 Decision Speed
- `03_DRIVERS/team_operating_system.md` — §4 Capacity Contract (evidence), §7 Partner Teams (use defined escalation path)
- `02_CONFIG/company_strategy.md` — §1 North Star
- `01_KERNEL/personal_dna.md` — Constraints & Fears (conflict avoidance flag)

**Ask User For:**
- Topic/issue to escalate
- Current capacity numbers
- Who the stakeholder is
- Impact on existing roadmap
- Historical context

**Critical Files for Freshness:**
- 🔴 `manager_decision_protocol.md` — 30-day grace (escalation logic)
- 🟡 `company_strategy.md` — 3-day grace (context)

**Output Format:**
```
# Escalation Brief — [Topic]

## Self-Awareness Flag
> From Personal DNA — check if escalating to avoid conflict vs. legitimate need

## Escalation Using Solution Rule (MOS §8)

**To:** [Leadership]

### The Problem
[Concise description]

### Current Situation
- Team capacity: [data]
- Roadmap impact: [what gets dropped]

### My Recommendation: Option A
[Detailed recommendation with reasoning]

### Alternative: Option B
[Trade-offs stated]

### Request
Which option should we proceed with?

## Rule Zero Consideration
- [ ] Complex enough for face-to-face? (Recommend if yes)
```

---

### `quarterly_reset`

**Trigger:** End of quarter
**Purpose:** System maintenance and file refresh

**OS Files to Read:**
- **All files** (full system review)
- `00_BOOT/README.md` — Quarterly maintenance section

**Ask User For:**
- Previous quarter's outcome data
- New quarter's company strategy
- New quarter's roadmap
- Team changes (joiners, leavers)
- Any company value or mission updates

**Critical Files for Freshness:**
- ⚠️ All files will be updated during this reset
- The command refreshes the entire system for the new quarter

**Output Format:**
```
# Quarterly Reset — [Q(X) → Q(X+1)]

## Quarter Retrospective
- OKRs: [Results]
- Roadmap delivery: [%]
- Ops ratio average: [%]
- Team health: [Trend]

## File-by-File Update Checklist

### 01_KERNEL/ (review only)
- [ ] MOS: Review values, update Pressure Mode Pattern Log, refresh §11
- [ ] Decision Protocol: Any new patterns to codify?
- [ ] Personal DNA: Update Goals (next 90 days)

### 02_CONFIG/ (replace if needed)
- [ ] Company Strategy: Archive old, create new with North Star
- [ ] Company OS: Check for updates

### 03_DRIVERS/ (update)
- [ ] Team OS: Update Squad, rewrite §6 Strategic Translation, review §7 Partner Teams
  - [ ] Mark "Carries Over: Yes" entries to keep across team changes
  - [ ] Remove "Carries Over: No" entries from previous team
- [ ] Player Cards: Update all §3 Growth Goals

### 04_PROCESSES/ (replace)
- [ ] Tactical Plan: Archive old, create new from roadmap

## Diff Summary
- Company goal: [Old] → [New]
- Team focus: [Old] → [New]
- Capacity ratio: [Old] → [New]
- Team size: [Old] → [New]
```

---

## 🔧 MAINTENANCE COMMANDS

### `prep_refresh`

**Trigger:** When file freshness warnings appear, or monthly maintenance
**Purpose:** Scan all OS files for staleness and refresh stale sections

**OS Files to Read:**
- **All files** — scan headers for Last Updated field (automatic check)

**Ask User For:**
- *Determined by command logic* — only asks about files that are stale based on freshness table

**Critical Files for Freshness:**
- Scans all 8 template files for staleness
- Prioritizes by grace period overdue (0-day grace first, then 3-day, then 7-day, then 30-day)

**Output Format:**
```
# File Refresh — [Date]

## Staleness Audit
| File | Last Updated | Expected Refresh | Days Overdue | Priority |
|------|--------------|------------------|--------------|----------|
| [File 1] | [YYYY-MM-DD] | [Frequency] | [#] days | 🔴 / 🟡 / 🟢 |
| [Order by priority] |

---

## Files Requiring Refresh (Priority Order)

### 🔴 [Most Urgent File]

**What happened since [last update date]?**

**Targeted questions (select which to answer):**
- If `tactical_plan.md`: What changed in the roadmap? Any new risks? Milestone updates?
- If `player_card - [Name].md`: Changes in growth goals? New strengths? Communication updates?
- If `team_operating_system.md`: Roster changes? Capacity ratio still accurate? New rituals?
- If `company_strategy.md`: Has the North Star changed? New OKRs?
- If `manager_operating_system.md`: New patterns to log? Values evolved? New protocols?
- If `personal_dna.md`: Goals still accurate? New fears/constraints? Avoidance patterns changed?
- If `company_operating_system.md`: Mission/values updated? New reporting structure?

**Updated section:**
[Provide summary of what changed — user fills this in]

---

### 🟡 [Second Priority File]
[Repeat above structure]

---

### 🟢 [Low Priority Files]
[List any approaching refresh windows]

---

## Updated File Headers (Ready to Paste)

```markdown
> **Last Updated:** [TODAY in YYYY-MM-DD]
```

**Apply this date to all files you just refreshed.**

## What NOT to Change

Only update what changed. Do **not** re-interview the entire file unless using `quarterly_reset` (which does a full overhaul).

**Examples:**
- ✅ Changed tactical plan? Update §1 Roadmap + §2 Risks only
- ✅ Changed player card? Update §3 Growth Goals + §2 Communication Prefs only
- ❌ Don't rewrite the entire file
```

**Chains With:** Output feeds into next command execution (e.g., `init_week`, `prep_121`) which will then see fresh "Last Updated" dates and won't flag warnings

---

### `version_upgrade`

**Trigger:** When new MOS framework version is released — either because the user typed `version_upgrade`, `version_upgrade [target_version]`, or `version_upgrade --remote`
**Purpose:** Upgrade from your current version to a newer version while preserving all user data. Supports two modes:
- **Local mode** (default): reads CHANGELOG already loaded in the conversation
- **Remote mode** (`--remote` flag, or when CHANGELOG is missing/outdated): fetches `CHANGELOG.md` and changed template files directly from the MOS GitHub repository via web browsing

**OS Files to Read:**
- **All files** — detect current version from headers
- `CHANGELOG.md` — read all entries between current and target version (local or remote)

**External Tools / Live Data:**
- **GitHub raw file access** (Remote mode only) — browse the following URLs:
  - CHANGELOG: `https://raw.githubusercontent.com/[mos-repo-owner]/[mos-repo-name]/main/CHANGELOG.md`
  - Individual changed template files: same base URL + file path (e.g., `.../main/03_DRIVERS/team_operating_system.md`)
  - File list derived from CHANGELOG `### Added` / `### Changed` entries
  - Fallback: if browsing fails, ask user to paste the new `CHANGELOG.md` content manually

**Ask User For:**
- Target version to upgrade to (e.g., `2026.08`) — or detect latest from remote CHANGELOG
- Confirm remote fetch from GitHub (Y/N) — prompted if `--remote` flag used or CHANGELOG appears outdated
- Confirmation before applying each migration step
- Generate inline bundle after migration (Y/N) — for bundled-deployment users (Gemini Gems, ChatGPT GPTs)

**Critical Files for Freshness:**
- All files will be updated with new Version field during upgrade
- Last Updated field is preserved (user's refresh dates remain accurate)

**Output Format:**
```
# Version Upgrade — [Current Version] → [Target Version]

## Current State
- **Your Version:** [Detected from file headers]
- **Latest Version:** [From CHANGELOG — local or remote]
- **Versions to Apply:** [List intermediate versions if any]
- **Source:** Local CHANGELOG / Remote GitHub fetch

---

## Change Summary

### Added (New content)
- [List of new files, commands, or sections from CHANGELOG]

### Changed (Modified content)
- [List of renamed/restructured items from CHANGELOG]

### Removed (Deprecated content)
- [List of removed features from CHANGELOG]

---

## Migration Plan

Total steps: [#]

---

### Step 1: [Action from CHANGELOG Migration Steps]

**Type:** Added / Changed / Removed

**What's changing:**
[Description from CHANGELOG]

**Your action:**
- If Added: [Show template section — fetched from GitHub if Remote mode, otherwise from CHANGELOG — ask user to fill in their data]
- If Changed: [Show diff between old structure and new template, ask user to adapt their content]
- If Removed: [Confirm archival, show what to remove]

**Ready to proceed?** (yes/no)

---

### Step 2: [Next Action]
[Repeat above structure for each migration step]

---

## Final Update

**Version field updates:**
```markdown
> **Version:** [Target Version]
```

**Apply this to all affected files:**
- [List of files that need Version updated]

**Your Last Updated dates are preserved** — only Version field changes.

---

## Verification Checklist

After upgrade:
- [ ] All new sections filled in with your data
- [ ] Changed sections adapted to new structure
- [ ] Removed sections archived or deleted
- [ ] Version field updated in all affected files
- [ ] Last Updated fields unchanged (your refresh dates preserved)
- [ ] Test with `init_week` command to verify

---

## Rollback Instructions

If something breaks:
1. Keep your old files backed up before running this command
2. Restore old version files
3. Report issue to MOS maintainers with version numbers

---

## Inline Bundle Generation (Bundled-Deployment Users)

If the user confirms bundle generation (or uses `--remote bundle`), after all migration steps are complete:

1. Assemble the complete `mos_compiled.md` inline from the migrated file contents (user data merged with new framework structure)
2. Follow the same concatenation order as `scripts/bundle.sh`:
   - `00_BOOT/README.md`
   - `01_KERNEL/manager_operating_system.md`, `manager_decision_protocol.md`, `personal_dna.md`
   - `02_CONFIG/company_operating_system.md`, `company_strategy.md`
   - `03_DRIVERS/team_operating_system.md`, `player_card - [Name].md` (one per team member)
   - `04_PROCESSES/tactical_plan.md`
   - `05_COMMANDS/command_reference.md`
   - `05_COMMANDS/system_prompt.md`
   - `06_BOARDROOM/boardroom.md`
3. Wrap each file with: `<!-- SOURCE FILE: [relative_path] -->`
4. **Include** `system_prompt.md` in the bundle — it is read by the AI from the knowledge file (not pasted separately)
5. Output the full bundle as a single code block
6. Instruct the user: replace the existing `mos_compiled.md` knowledge file in their Gem/GPT/Project with this new bundle — no need to run `bundle.sh` manually

> **Platform note:** If the generated bundle exceeds the platform's output limit, split into 2–3 parts with clear instructions on paste order. Remind the user that `00_BOOT/bootstrap_prompt.md` in Custom Instructions stays unchanged — only the knowledge file needs replacing.

---

## How to Check Your Current Version

Look at any file header — the `Version:` field shows your MOS template version.

Example:
```markdown
> **Version:** 2026.02
> **Last Updated:** 2026-02-10
```

In this case, you're on v2026.02.
```

**Chains With:** 
- Often follows `prep_refresh` (get files fresh before upgrading)
- After upgrade, run `init_week` or `quarterly_reset` to verify system works
- If inline bundle was generated: user replaces their Gem/GPT knowledge file with the bundle — no need to run `bundle.sh` separately

---

## 🎙️ BOARDROOM COMMANDS

### `boardroom [topic]`

**Trigger:** When you're uncertain how to handle a high-stakes management situation and want structured, adversarial input from multiple perspectives
**Purpose:** Convene your virtual advisory council — activate the most relevant boardroom personas for the given topic, get each persona's take and probing questions, then synthesise the divergent views into a decision-ready output

**OS Files to Read:**
- `06_BOARDROOM/boardroom.md` — §1 Working Principles, §2 Manager's Chair, §3 All Personas
- `01_KERNEL/personal_dna.md` — Goals, Constraints & Fears, Avoidance Patterns
- `01_KERNEL/manager_operating_system.md` — §12 Pressure Mode (check if session is stress-driven)

**Ask User For:**
- `[topic]` — The situation, decision, or challenge to bring to the boardroom (1–3 sentences of context)
- Session depth: **Quick scan** (3 personas, 5-min read) or **Full session** (4–5 personas, deeper analysis)

**Persona Selection Logic:**

Auto-select 3–4 personas based on topic type. Use this mapping as a guide:

| Topic Type | Activate |
| People / team dynamics / trust | People Coach + Vulnerability Anchor + Challenger |
| Delivery / performance / output | Execution Engine + Principles Force + Challenger |
| Strategy / communication / direction | Narrative Strategist + Execution Engine + Challenger |
| Complex / multi-faceted decision | All 4: Execution Engine + People Coach + Principles Force + Challenger |
| Manager wellbeing / pressure / burnout | Vulnerability Anchor + Narrative Strategist + People Coach |

Always include the **Challenger** persona unless the topic is explicitly wellbeing-focused.

**Output Format:**
```
# Boardroom Session — [Topic Summary]
**Date:** [Today]
**Session Depth:** [Quick / Full]

---

## Personas Activated
[List 3–4 personas selected, with one-line rationale for why each was chosen for this topic]

---

## [Persona 1 Name] — [Role]
> *"[Their worldview quote]"*

**Their Take:**
[2–4 sentences of their perspective on the topic, voiced in their style]

**They Ask:**
1. [Probing question 1]
2. [Probing question 2]

---

## [Persona 2 Name] — [Role]
[same structure]

---

[repeat for each activated persona]

---

## Integrated Synthesis
**Where they agree:**
- [Point of consensus 1]
- [Point of consensus 2]

**Where they diverge:**
- [Persona A] wants [X] — [Persona B] pushes back with [Y]
- [Note the tension and what it means for your decision]

**Recommended next action:**
[One concrete, actionable step the manager can take today based on the boardroom discussion]

---

> ⚠️ **Rule Zero:** The boardroom advises. You decide.
> Run `stakeholder_request` or `escalate` if this decision requires a formal protocol.
```

**Critical Files for Freshness:**
- 🟢 `06_BOARDROOM/boardroom.md` — review quarterly (no hard staleness trigger)
- 🟢 `01_KERNEL/personal_dna.md` — 30-day grace

**Chains With:**
- Precedes `stakeholder_request [description]` — boardroom clarifies your position before running the decision protocol
- Precedes `escalate [topic]` — boardroom helps you think through whether to escalate and how
- Follows any command where Pressure Mode is detected — boardroom provides a structured debrief

---

## Command Chaining & Session Memory

Commands build on each other. The AI retains outputs within the same conversation:

```
Monday:     init_week → [output stored]
  Tuesday:    init_day → shutdown_day → [stored]
  Wednesday:  init_day → shutdown_day → [stored]
  ...
Friday:     shutdown_week → [references init_week for comparison]

Next Monday: init_week → [references shutdown_week for carryover]
```

---

## Usage Instructions

1. **Upload all OS files** to your AI platform (ChatGPT Project / Gemini Gem / Claude Project) — or use `scripts/bundle.sh` to compile into a single `mos_compiled.md`
2. **Paste `00_BOOT/bootstrap_prompt.md`** into Custom Instructions (static — paste once, never changes between versions)
3. **Type command name** in conversation (e.g., `init_week`)
4. **AI will:** read this reference → load OS files → ask for inputs → produce output
5. **Store command outputs** in the session for chaining

---

**Note:** Your full operating instructions (`system_prompt.md`) are bundled inside the knowledge files. `00_BOOT/bootstrap_prompt.md` is the static pointer that tells the AI where to find them.
