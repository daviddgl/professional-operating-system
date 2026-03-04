# Player Card: [Name]

> **Layer:** DRIVERS  
> **Owner:** [Name] + [Your Name]  
> **Version:** 2026.02  
> **Last Updated:** [YYYY-MM-DD]  
> **Portable:** No — Team-specific instance

---

## What Is This File?

**Player Cards** are individual team member profiles — their superpowers, growth goals, communication preferences, and how they work best. One card per team member.

Commands use these to:
- Personalize 1:1s (`prep_121` — matches person's growth goal)
- Assign work aligned with growth (`init_week` — task to person matching their goal)
- Provide targeted onboarding (`onboard`)
- Make fair decisions in `stakeholder_request` (Gate 3: Which person benefits from this work?)

**Update frequency:** Quarterly + after discovery in 1:1s  
**Used by:** `prep_121`, `init_week`, `prep_planning`, `onboard`, `stakeholder_request`  
**Critical sections:** §1 (Superpower), §2 (Communication preferences), §3 (Growth goal)

---

**Role:** [e.g., Backend Engineer, Product Manager, Designer]
**Time Zone:** [e.g., CET, EST, PST]

## 1. My User Manual

* **My Superpower:** [What does this person do better than anyone else? Ask them.]
* **My Kryptonite:** [What drains their energy? What context makes them less effective?]
* **How to give me feedback:** [Their preferred feedback format — direct? Written first? In person?]

## 2. Communication Preferences

* **Urgent:** [Slack DM / Call / Text]
* **Discussion:** [Slack Thread / Schedule a Sync / Email]
* **Deep Work Hours:** [e.g., 09:00 - 12:00 — Do not disturb]

## 3. Growth Goals ([Current Quarter])

* [Growth goal 1 — e.g., "Lead the Python upgrade to prove seniority"]
* [Growth goal 2 — e.g., "Improve estimation accuracy"]

<!-- Fill this in together during 1:1s. Update quarterly. These are used by prep_121 and prep_planning commands. -->
