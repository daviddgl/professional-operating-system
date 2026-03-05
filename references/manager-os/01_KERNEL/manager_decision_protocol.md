# Manager Decision Protocol

> **Layer:** KERNEL  
> **Owner:** [Your Name]  
> **Version:** 2026.02  
> **Last Updated:** [YYYY-MM-DD]  
> **Portable:** Yes — travels with the manager across all contexts

---

## What Is This File?

**Decision Protocol** is your conflict resolution logic — how you choose between competing priorities when they clash. It defines the 3-gate hierarchy (Capacity → Strategy → Individual Match) and enforcement rules.

This file is used when:
- Handling `stakeholder_request` — which new work to accept
- Running `escalate` — how to resolve conflicts
- Planning `prep_planning` — prioritizing backlog

**Update frequency:** Rarely (foundational; built during SETUP_WIZARD)  
**Used by:** `stakeholder_request`, `escalate`, `prep_planning`  
**Core concept:** Rule Zero ("When in doubt, talk in person") + 3-gate hierarchy

---

**Purpose:** To resolve conflicts and guide execution using the Manager Operating System (MOS) files.

### §0 — Rule Zero

The OS is a decision-SUPPORT tool. It does not make decisions.

When OS rules produce any of the following:
- Conflicting outputs from two or more gates
- A recommendation that feels wrong in context
- Ambiguity that cannot be resolved by re-reading the relevant files
- A "bad gut feeling" that persists after analysis

**Stop. Invoke Rule Zero. Have a synchronous human conversation.**

Rule Zero supersedes all other rules. Any human can invoke it at any time, including
the AI copilot if it detects unresolvable ambiguity. It cannot be overridden by
any other rule in the OS.

The action is always the same: talk to a human, directly, before deciding.

---

### §1 — Hierarchy of Precedence (Order of Operations)

When making a decision, apply constraints in this specific order (Local $\rightarrow$ Global):

1. **Level 1: The Team Contract (Local Context)**
    * *Why?* The team is the execution unit. Their immediate health and capacity determine *if* we can work.
    * *Rule:* If a request violates the team's **Capacity Contract** (defined in Team OS), it is blocked, regardless of Company priority (unless P0).
2. **Level 2: Company Strategy (Global Direction)**
    * *Why?* If the Team has capacity, we must align with the Company.
    * *Rule:* Choose the path that maximizes the **Company Strategy**.
3. **Level 3: Individual Needs (Personal Context)**
    * *Why?* Long-term sustainability requires individual growth.
    * *Rule:* Match the task to the person's **"Player Card"** (Strengths/Goals).

### §2 — Interaction Rules (The API)

### Rule A: The "Override" Function

* **Scenario:** Company Value says "Move Fast," but Team Value says "Reliability First."
* **Logic:** The **Team OS** overrides the Company OS for *implementation details*.
  * *Result:* We move fast on *features*, but we do not compromise *quality gates*.

### Rule B: The "Conflict" Function

* **Scenario:** Two roadmap items compete for the same resource.
* **Logic:**
    1. Check **Company Strategy**: Which item impacts the current Company Goal more?
    2. Check **Team OS**: Does one item reduce "Hidden Factory" (ops) work?
    3. **Decision:** Prioritize the intersection of High Impact + Debt Reduction.

### Rule C: The "Exception" Function

* **Scenario:** A P0 Incident (System Down).
* **Logic:** **Suspend all MOS Rules.**
  * Switch to **Commanding Leadership** (MOS §5).
  * Ignore Capacity Contract Split.
  * Restore standard rules immediately after resolution.

### §3 — New Request Loop (Iteration Protocol)

**Purpose:** Define how to handle a new work request, scope change, or opportunity through the 3-gate hierarchy — including what to do when a gate fails and how to re-enter the loop.

### The Loop

```
1. RECEIVE request (stakeholder, leadership, or self-identified opportunity)
2. RUN Gate 1 — Team Capacity
   → PASS: proceed to Gate 2
   → FAIL (exceeds Capacity Contract): REJECT or NEGOTIATE scope reduction.
     If not negotiable → ESCALATE to leadership. Loop ends.
3. RUN Gate 2 — Company Strategy
   → PASS (aligned with current Company Goal): proceed to Gate 3
   → FAIL (misaligned): DEPRIORITIZE or DEFER to next planning cycle. Loop ends.
4. RUN Gate 3 — Individual Match
   → PASS (matches Player Card strengths/goals): ASSIGN and execute
   → FAIL (poor match): REASSIGN to a better-matched team member or NEGOTIATE scope
5. DOCUMENT outcome — log gate results in tactical plan or team operating system
6. REVIEW at next retro — were DEFERRED or NEGOTIATED items revisited?
```

### Re-Entry Rules

* A DEFERRED request re-enters the loop at Gate 2 only (Capacity already cleared at time of deferral).
* A NEGOTIATED request re-enters the loop at the gate that triggered negotiation.
* A REJECTED request does NOT re-enter — a re-scoped version from the same stakeholder is treated as a fresh evaluation.
* Maximum three re-entry cycles per request. If no path to acceptance after three cycles, escalate or close.

### Rule Zero Override

* If any gate produces a conflict that analysis cannot resolve — or if the outcome feels wrong despite a logical pass — invoke Rule Zero: stop the loop and have a direct conversation with the relevant stakeholder before proceeding.

---

### §4 — Decision Speed (Reversibility Framework)

**Purpose:** Match decision pace to decision weight. Move fast on reversible things; slow down on irreversible ones.

### The Test

> *"If I get this wrong, can I correct it within 30 days without significant cost to the team, the business, or an individual's career?"*

| Answer | Classification | Speed |
|--------|--------------|-------|
| Yes, easily | **Reversible** | Decide fast — bias toward action |
| Yes, with effort | **Partially reversible** | Decide within 48 hours with at least one input |
| No | **Irreversible** | Decide slow — mandatory Rule Zero check + Boardroom consult if high stakes |

### Examples by Category

| Decision | Reversible? | Speed Rule |
|----------|------------|------------|
| Try a new meeting format or team ritual | ✅ Yes | Decide in the next standup |
| Shift a sprint priority mid-cycle | ✅ Yes | Bias toward action — document rationale |
| Assign a stretch assignment to a player | ⚠️ Partial | 48-hour rule — check Player Card first |
| Change a team process or delivery standard | ⚠️ Partial | 48-hour rule — run it by the team |
| Accept a new long-term commitment for the team | ❌ No | Run full 3-gate loop. Slow down. |
| Put someone on a performance plan | ❌ No | Rule Zero + Boardroom. Write it out before any conversation. |
| Restructure team responsibilities or roles | ❌ No | Rule Zero. Align with leadership first. Not an OS decision alone. |

### Pressure Mode Interaction

* Under pressure (P0 incident, leadership escalation, tight deadline), the bias toward fast decisions is **suspended for irreversible choices**.
* All decisions above "Reversible" require explicit written reasoning before acting.
* Rule C (Exception Function in §2) is the only bypass: P0 incidents suspend all MOS rules temporarily. Restore standard protocol immediately after resolution.
