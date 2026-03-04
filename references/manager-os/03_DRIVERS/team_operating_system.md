# TEAM OS: [Team Name]

> **Layer:** DRIVERS  
> **Owner:** [Your Name]  
> **Version:** 2026.02  
> **Last Updated:** [YYYY-MM-DD]  
> **Portable:** No — replaced when you change teams

---

## What Is This File?

**Team Operating System** is your team's rulebook — who they are, how they work, their capacity, their rituals. It's the interface between company strategy and individual work.

Commands use this to:
- Understand team capacity and constraints (`capacity_check`)
- Allocate work to people (`prep_121`, `init_week`)
- Enforce the Capacity Contract (ops vs. features ratio)
- Sync rituals and communication (`init_day`)
- Make decisions aligned with team principles (`stakeholder_request`, `escalate`)

**Update frequency:** Quarterly (capacity changes, new rituals) + on team changes  
**Used by:** ALL commands (most heavily: init_week, prep_planning, capacity_check, prep_121, stakeholder_request)  
**Critical sections:** §2 (Squad/Capacity), §4 (Capacity Contract), §6 (Strategic Translation), §7 (Partner Teams)

---

## 1. Identity & Mission

**Who We Are:** [One-line team identity]
**Mission:** [What does this team deliver? To whom?]

* **What We Own:**
  * [Product/service 1]
  * [Product/service 2]
* **What We Deliver:**
  * [Deliverable 1]
  * [Deliverable 2]
* **Who We Serve:**
  * [Primary customer/user]
  * [Secondary customer/user]

## 2. The Squad (Capacity Board)

*The human resources available to execute this OS.*

| Resource | Role | Allocation | Focus Area |
| :--- | :--- | :--- | :--- |
| **[Your Name]** | Lead | [X]% Maker / [X]% Mgr | [Focus areas] |
| **[Name]** | [Role] | [X]% | [Focus areas] |
| **[Name]** | [Role] | [X]% | [Focus areas] |
| **[Name]** | [Role] | **[X]% (Constraint)** | [Focus areas] |

<!-- Mark shared or part-time resources as Constraints. This is critical for capacity_check and prep_planning commands. -->

## 3. Core Operating Principles

> *Note: Universal principles (your portable values) live in the Kernel → Manager Operating System. This section contains only team-specific principles.*

* **[Team Principle 1]:** [Why this is specific to THIS team — e.g., "Data Integrity: We are the custodians of customer data. Accuracy > Speed."]

<!-- Only add principles that wouldn't apply to a different team you might lead. Everything else belongs in the Kernel. -->

## 4. The Capacity Contract

**We acknowledge that "Hidden Work" exists.**

* **The Ratio:** We allocate **[X]%** capacity to Planned Roadmap (Features) and **[Y]%** to Operations (Bugs, On-call, Maintenance).
* **The Circuit Breaker:** If Operations exceed [Y]% for two consecutive weeks, we **pause** the lowest priority roadmap item to fix the root cause. We do not "work harder"; we fix the system.

## 5. Rituals (Sync vs. Async)

<!-- Define your team's recurring meetings and async rituals. -->

* **Daily Standup ([Sync/Async]):** [Format, time, channel]
* **Weekly Sync ([Sync/Async]):** [Duration, focus]
* **Retro ([Sync/Async]):** [Frequency, format]

## 6. Strategic Translation ([Current Quarter])

*How we translate Company Strategy into Team Actions this quarter.*

<!-- Read Company Strategy §1 (North Star) and write your team's interpretation below. -->

* **Priority Logic:** [How does the company goal translate to YOUR team's priorities?]
* **The Trade-off Rule:** [When time is tight, what do you CUT and what do you KEEP?]

| Company Value (Static) | Team OS Implementation (This Quarter) |
| :--- | :--- |
| **[Value 1]** | → [How your team implements this value this quarter] |
| **[Value 2]** | → [How your team implements this value this quarter] |
| **[Value 3]** | → [How your team implements this value this quarter] |

## 7. Partner Teams & Interfaces

*Who we collaborate with and how we work together.*

<!-- This section tracks cross-team dependencies, shared goals, and communication channels. Update quarterly via prep_refresh, or when new partnerships begin. -->

> **Portability note:** Partner teams within the same company are listed here. The `Carries Over` column marks relationships that survive a team change within your current company — update these during `quarterly_reset`, keep ones marked "Yes" and discard ones marked "No" when changing teams.

| Partner Team | Key Contact | Shared Goal / Interface | Comm Channel | Escalation Path | Carries Over |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **[Team Name]** | [Contact, role] | [What we jointly own or deliver] | [Slack channel, email, weekly sync] | [Who escalates to whom—e.g., "My Lead → Their Lead"] | Yes/No |
| **[Team Name]** | [Contact, role] | [Shared responsibility or dependency] | [Channel] | [Escalation path] | Yes/No |
| **[Team Name]** | [Contact, role] | [Project or area of overlap] | [Channel] | [Escalation path] | Yes/No |

**How to use this table:**
- **List every team** your team regularly syncs with (platform, design, data, product, QA, etc.)
- **Carries Over:** Mark "Yes" if this relationship (or the key contact) survives your next team change within the company; mark "No" if it's specific to your current team
- **Update frequency:** Refresh quarterly when running `prep_refresh` or `quarterly_reset`, or add rows when new partnerships start
- **Commands that use this:** `stakeholder_request` (context for incoming asks), `prep_planning` (surface cross-team dependencies), `init_week` (flag sync opportunities), `escalate` (use defined escalation path), `capacity_check` (cross-team commitments consume capacity)
