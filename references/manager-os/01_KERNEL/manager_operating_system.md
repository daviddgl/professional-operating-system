# Manager Operating System (MOS)

> **Layer:** KERNEL  
> **Owner:** [Your Name]  
> **Version:** 2026.02  
> **Last Updated:** [YYYY-MM-DD]  
> **Portable:** Yes

---

## What Is This File?

**Manager Operating System** is your personal leadership playbook. It defines how you think, decide, and operate — your philosophy, standards, communication style, and protocols. This is the core of what makes you a manager, and it travels with you across teams and companies.

Every command reads sections from this file because it's your source of truth for:
- Philosophy and values (§1)
- Team expectations (§2)
- Decision protocols (§3, §8)
- Feedback style (§6)
- Engineering standards (§10)
- Self-management in stress (§12)

**Update frequency:** Rarely (once set, evolves over years, not quarters)  
**Used by:** ALL commands (most frequently: stakeholder_request, escalate, prep_121, init_week)  
**Most critical sections:** §1 (Philosophy), §3 (Capacity Contract), §12 (Pressure Mode)

---

## 1. The Kernel: Core Philosophy

**Purpose Statement:** [Write your management purpose in one sentence. What is your role? Who do you serve? What do you bridge?]

> *Example: "I serve the team by removing obstacles and facilitating tools, mindset, and guidance. I act as the bridge between technical execution and company goals."*

### Core Values (The DNA)

<!-- List 3-5 values that define how you lead. These should be non-negotiable principles that travel with you to any team. -->

1. **[Value 1]:** [Definition — what does this mean in practice?]
2. **[Value 2]:** [Definition]
3. **[Value 3]:** [Definition]
4. **[Value 4]:** [Definition]
5. **[Value 5]:** [Definition]

## 2. Team Expectations & Relationship Spec

**Goal:** [What kind of relationship do you want with your team?]

<!-- List the expectations you set for any team you lead. These are your non-negotiable working agreements. -->

* **[Expectation 1]:** [Description]
* **[Expectation 2]:** [Description]
* **[Expectation 3]:** [Description]
* **[Expectation 4]:** [Description]
* **[Expectation 5]:** [Description]

## 3. The Capacity Contract (Ops vs. Features)

**Goal:** Prevent the "Hidden Factory" of operations/maintenance from eating the roadmap.

### The Principle

* Every team I lead operates under a **Capacity Contract** — a predefined split between Planned Roadmap work and Operations/Maintenance. The specific ratio is defined in the **Team OS**.
* **The "Red Line" Trigger:** If Operations work consistently exceeds the contracted ratio:
  * **Action:** Initiate conversation with PM/stakeholder.
  * **Script:** *"We are currently operating at [X]% maintenance. To deliver Feature [Y], we must drop [Z] or accept a delay. Which do you prefer?"*

### The "No" Logic

When an urgent request arrives that threatens the plan:

* **IF** request is P0 (System Down) $\rightarrow$ **ACCEPT** immediately.
* **IF** request is "Important" but not P0 $\rightarrow$ **NEGOTIATE**.
  * *Question:* "If we add this, which existing item are we pausing?"

<!-- Customize the negotiation scripts above to match your communication style. -->

## 4. Communication Protocol

**Goal:** [What communication problem are you solving? e.g., "Eliminate useless meetings to regain focus time"]

### The Meeting Filter

A meeting is **automatically declined** if it does not meet these specs:

1. **Clear Agenda:** No "Quick syncs" without a topic.
2. **Desired Outcome:** Must state what decision or artifact will be produced.
3. **Async Check:** Could this have been a [chat thread / recorded video]?

### Meeting Execution

* **Strict Timeboxing:** Meetings end 5 minutes early to allow for context switching.
* **The Output Rule:** No meeting ends without:
  * **Decision Log:** What was agreed?
  * **Action Items:** Who does what by when? (Logged in [your task tracker]).

## 5. Leadership Mode Selector (Situational Logic)

**Goal:** Apply the right leadership style based on the context.

| Context | Leadership Mode | Behavior |
| :--- | :--- | :--- |
| **Standard / Growth** | **Coaching (Default)** | Ask questions. Let them own the solution. |
| **Crisis / Incident** | **Commanding** | Give clear, direct orders. Speed over consensus. |
| **New Roadmap** | **Visionary** | Set the "Why" and the "Destination." Leave the "How" to the team. |
| **Team Conflict** | **Affiliative** | Focus on people first. Clear the air before working. |
| **Consensus Needed** | **Democratic** | Gather input before deciding. Use for non-urgent, high-impact decisions. |

<!-- Adjust modes and behaviors to match your leadership style. Add or remove rows. -->

---

## 6. The Feedback Loop

**Goal:** Continuous improvement through concrete, actionable feedback.

### Outbound (You to Team)

* **Specificity Rule:** Feedback must be **concrete**.
  * *Bad:* "You need to communicate better."
  * *Good:* "In the standup, you didn't mention the blocker on [X]. That caused [Y] delay. Next time, flag blockers immediately."
* **Timing:** [Immediate? Weekly? In 1:1s?]

### Inbound (Team to You)

* **Synchronous:** [How do you invite feedback? e.g., "What is one thing I'm doing that is slowing you down?"]
* **Asynchronous:** [Do you use anonymous forms? Retrospectives? How do you make it safe?]

## 7. Failure & Risk Protocol

**Goal:** Encourage risk-taking without jeopardizing the roadmap.

### The "Safe Fail" Timebox

* **Concept:** Team members can try new approaches/tech, BUT strictly timeboxed.
* **The Rule:** *"You have [X Days] to prove this works. If not, we revert to the safe path."*
* **Early Warning System:** Bad news must travel fast.
  * *Constraint:* Delays are acceptable **only if** communicated *before* the deadline.

## 8. Managing Up (The Leadership Interface)

**Goal:** Build trust with leadership to earn autonomy.

### The "No Surprises" Executive Summary

* **Frequency:** [Weekly / Biweekly]
* **Format:**
    1. **Roadmap Status:** Red / Yellow / Green.
    2. **Top Risk:** What might bite us? + *Mitigation Plan*.
    3. **The Ask:** What do I need from you to succeed?
* **The "Solution" Rule:** Never present a problem without a proposed solution.
  * *Template:* *"We have a problem with [X]. My recommendation is [Option A] because [Reason]. We could also do [Option B]. Thoughts?"*

## 9. Success Metrics (KPIs)

<!-- Define 3-5 metrics that tell you "things are going well." These should be YOUR metrics, not just company KPIs. -->

* **[Metric 1]:** [Description and target]
* **[Metric 2]:** [Description and target]
* **[Metric 3]:** [Description and target]

---

## 10. Engineering Standards (Portable)

> *These standards travel with you to any team. They are not team-specific.*

<!-- Customize these to your engineering philosophy. Remove or add as needed. -->

* **[Standard 1]:** [Description — e.g., "We do not code without a plan. Complex features require a technical spec before implementation."]
* **[Standard 2]:** [Description — e.g., "Code merged + Tested + Monitored + Documented = Done."]
* **[Standard 3]:** [Description — e.g., "Leave the codebase cleaner than you found it."]

## 11. Company Values → Engineering Translation

> *Your personal interpretation of your company's core values for engineering teams. Update this when you change companies.*

| Company Value | Your Engineering Translation |
| :--- | :--- |
| **[Value 1]** | [How you implement this in your team] |
| **[Value 2]** | [How you implement this in your team] |
| **[Value 3]** | [How you implement this in your team] |

## 12. Pressure Mode Protocol (Self-Management)

> *The system assumes the manager is rational. This section exists for when that assumption breaks.*

### Activation Triggers (Stress Indicators)

If **two or more** of these are true, activate Pressure Mode:

- [ ] Making decisions without applying the Kernel Decision Protocol
- [ ] Saying yes to everything to avoid conflict
- [ ] Skipping the Capacity Contract negotiation ("just this once")
- [ ] Working past hours for non-P0 issues
- [ ] Avoiding a difficult conversation
- [ ] Feeling isolated — "no one understands the trade-offs I'm making"

<!-- Add your own stress indicators — what patterns do YOU exhibit under pressure? -->

### Pressure Mode Rules

1. **SLOW DOWN:** Take 2 minutes before any decision. Write it down before saying it.
2. **GET SECOND OPINION:** Never make a consequential decision alone under pressure. Use Isolation Breakers (below).
3. **DOCUMENT REASONING:** Write why you're choosing X over Y — if you can't articulate it, invoke Rule Zero.
4. **SET REVIEW POINT:** "Let's revisit this in 24 hours" is always a valid response for non-P0 issues.

### Isolation Breakers

*When you feel alone with a decision, pick an advisor by decision type:*

| Decision Type | Who to Call | Format |
| :--- | :--- | :--- |
| **Technical** | [Peer leads / Staff engineers] | 3-bullet context + specific question |
| **People** | [HR / trusted peer] | Framing: "I need a sounding board on [situation]" |
| **Product/Priority** | [PM / Product leadership] | Use Capacity Contract data as the conversation starter |
| **Career/Strategic** | [Mentor / skip-level manager] | 15-min request with clear ask |

### Recovery

After any decision made under pressure:

* **Document:** What was decided → What Kernel rule was applied → What alternatives existed
* **Review at 24h:** Was this the right call? Would calm-you have decided differently?
* **Pattern Log:** If the same pressure scenario repeats, add it to this section as a known pattern.

## 13. System I/O & Memory (External Resources)

> *This OS processes logic, but stores data in external tools. Markdown files = Code (how we work). External tools = Database (what we work on).*

* **Task Memory ([Your task tracker]):**
    * *Role:* The Source of Truth for *Status* and *Execution*.
    * *Rule:* If it's not in [task tracker], it's not being worked on.
* **Strategic Memory ([Your planning tool]):**
    * *Role:* The Source of Truth for *Roadmap Visualization*.
    * *Rule:* Used for high-level planning and stakeholder views.
* **Documentation ([Your wiki/docs]):**
    * *Role:* Permanent knowledge base for decisions, specs, and architecture.
    * *Rule:* Decisions made elsewhere must be committed here.
* **Communication ([Your chat tool]):**
    * *Role:* Ephemeral communication and context.
    * *Rule:* Decisions made here must be committed to task tracker or docs. Chat is not a source of truth.
