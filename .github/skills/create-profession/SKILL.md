---
name: create-profession
description: 'Generate a new Profession Operating System variant for a profession. Use when creating a new profession OS, building a profession variant, generating references/<profession>-os/, or replacing the GENERATOR_PROMPT workflow with a spec-compliant skill-driven process.'
argument-hint: 'Target profession, intended user role, and any known reference profession or constraints'
---

# Create Profession

Generate a complete, spec-compliant Profession Operating System variant for a new profession.

Use this skill when the user wants to create a new profession reference implementation under `references/<profession>-os/`, adapt the framework to a new professional role, or replace manual copy-and-edit work with a structured generation workflow.

This skill is not for personalizing an existing variant. It is for creating the profession variant itself.

## Outcome

Produce a full profession variant that is ready to personalize with a Setup Wizard.

Default output location:
- `references/<profession>-os/`

Expected outputs:
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
- `skills/` files if needed
- `scripts/bundle.sh`

If running in a workspace with write access, create or update these files directly instead of only proposing drafts.

## Expert Panel

Work as a coordinated panel of five experts throughout the generation process.

### 1. Domain Expert

Understands the target profession's cadences, vocabulary, decisions, constraints, and ethical boundaries.

Owns:
- profession fit assessment
- vocabulary mapping
- modes of operation
- pressure triggers
- profession-specific examples

### 2. Framework Architect

Knows `PROFESSION_SPEC.md` in detail and enforces every MUST requirement.

Owns:
- 7-layer integrity
- file naming
- command format compliance
- Rule Zero preservation
- final spec validation

### 3. Organizational Psychologist

Models human behavior, relationships, stress patterns, conflict, and recovery.

Owns:
- pressure mode design
- relationship expectations
- isolation breakers
- conflict and exception logic

### 4. End-User Advocate

Represents the professional who will use the OS weekly.

Owns:
- command ergonomics
- setup wizard pacing
- practicality of rituals and freshness checks
- whether the generated system is usable in real work

### 5. Decision Science Expert

Designs structured choices under uncertainty.

Owns:
- decision gates
- reversibility framework
- conflict resolution
- boardroom activation logic

Do not present these roles as disconnected essays. Use them to pressure-test decisions and converge on a single implementation.

## Required Repository Context

Before generating files, read these repository files inline from the workspace.

**All paths are relative to the repository root** (the directory where the skill is invoked):

- `PROFESSION_SPEC.md`
- `references/coach-os/SETUP_WIZARD.md`
- `references/coach-os/05_COMMANDS/command_reference.md`
- `references/coach-os/06_BOARDROOM/boardroom.md`
- `references/manager-os/SETUP_WIZARD.md`
- `references/manager-os/05_COMMANDS/command_reference.md`
- `references/manager-os/06_BOARDROOM/boardroom.md`
- `references/coach-os/01_KERNEL/coach_operating_system.md`
- `references/manager-os/01_KERNEL/manager_operating_system.md`
- `scripts/bundle.sh`

Use the two reference implementations to separate invariant structure from profession-specific vocabulary.

Load these skill references as needed:

- [Vocabulary template](./references/vocabulary-template.md)
- [Compliance checklist](./references/compliance-checklist.md)
- [Generation sequence](./references/generation-sequence.md)

## Operating Rules

1. Preserve every invariant from the framework spec.
2. Never change Rule Zero text.
3. Do not invent profession data the user has not provided. Use placeholders or example content where appropriate.
4. Mark all Tier 3 scaffolding with `<!-- EXAMPLE CONTENT: Replace with your actual data using the Setup Wizard -->`.
5. Prefer direct file creation in `references/<profession>-os/` when write access is available.
6. Use the existing reference implementations inline. Do not require the user to upload them if they already exist in the repo.
7. If the profession is a weak fit for the framework, say so clearly, explain why, and ask whether to proceed anyway.
8. Keep the resulting variant bundle-ready with the repository's existing bundling approach.

## Procedure

### Step 1: Confirm the Profession and Fit

Interview the user to identify:
- profession name
- role title of the end user
- who they serve, lead, or manage
- recurring cadences
- high-stakes recurring decisions
- capacity constraints
- portability pattern across contexts
- known ethical, legal, or regulatory constraints

Then evaluate the profession against `PROFESSION_SPEC.md §13` fit criteria:
- structured recurring cadences
- people relationships
- measurable goals and capacity constraints
- recurring high-stakes decisions
- contextual portability

If one or more criteria are weak, return:
- what is weak
- whether that is fatal or manageable
- what adjustments would make the profession variant still useful

### Step 2: Build the Vocabulary Map

Use [Vocabulary template](./references/vocabulary-template.md).

Fill every abstract placeholder from `PROFESSION_SPEC.md §11`, including:
- profession role
- abbreviation
- context
- entities and entity
- entity card
- roster
- roster operating system or portfolio
- context strategy
- plan type
- interaction
- request command
- onboarding command
- boundary command
- planning command

Show the vocabulary map to the user for confirmation before generating files.

### Step 3: Design the Core Profession Model

Using the expert panel, define:
- 4 to 6 core values
- relationship expectations section
- capacity contract categories
- communication protocol
- 4 to 6 situational modes
- success metrics
- profession standards section
- profession-specific external tools and memory system

Reuse the structure of the existing references, but rewrite the content for the target profession.

### Step 4: Design the Decision Protocol

Using the Decision Science Expert and Organizational Psychologist:
- define Gate 1, Gate 2, and Gate 3 in local-to-global order
- define pass condition, fail condition, and source of truth for each gate
- define override, conflict, and exception rules
- define the new request loop
- classify 5 to 7 common profession decisions as fast or slow
- identify which decisions become slower in Pressure Mode

Rule Zero must be copied verbatim.

### Step 5: Design Pressure Mode

Define profession-specific:
- triggers
- slowdown protocol
- second-opinion paths
- documentation expectations
- recovery actions
- exit criteria
- pattern log format

This section should feel realistic for the profession, not generic.

### Step 6: Design the Boardroom

Map the six archetype slots to profession-appropriate personas.

For each persona, define:
- name and archetype label
- worldview quote
- focus areas
- two probing questions

Also define:
- working principles
- activation logic by topic type
- standard boardroom session format
- the profession chair context block

### Step 7: Design the Command System

Generate the required minimum command categories from `PROFESSION_SPEC.md §8.2`:
- lifecycle
- people
- execution
- decision support
- maintenance

For each command:
- use the exact field order from the spec
- choose realistic command names for the profession
- declare live inputs under Ask User For
- declare freshness requirements using 🔴, 🟡, and 🟢
- specify exact markdown output templates
- define chaining logic where useful

The command system must be practical enough that a real user would actually run it.

### Step 8: Generate the Files in Order

Use [Generation sequence](./references/generation-sequence.md).

Write the files directly into:
- `references/<profession>-os/`

Recommended order:
1. `bundle.conf`
2. `README.md`
3. `CHANGELOG.md`
4. `ARCHITECTURE.md`
5. `SETUP_WIZARD.md`
6. `00_BOOT/README.md`
7. `00_BOOT/bootstrap_prompt.md`
8. `01_KERNEL/*`
9. `02_CONFIG/*`
10. `03_DRIVERS/*`
11. `04_PROCESSES/*`
12. `05_COMMANDS/*`
13. `06_BOARDROOM/boardroom.md`
14. `skills/*` if needed
15. `scripts/bundle.sh`

Use the root `scripts/bundle.sh` as the base for the profession-local script.

### Step 9: Generate the Setup Wizard

Create a profession-specific `SETUP_WIZARD.md` that:
- interviews in phases
- asks 3 to 5 questions per round
- gives examples for abstract questions
- accepts URLs
- confirms before generating files
- outputs complete files
- tracks progress visually
- supports `skip`
- never invents data

The phases should mirror the profession's real workflow and produce all Tier 3 content cleanly.

### Step 10: Validate Against the Spec

Use [Compliance checklist](./references/compliance-checklist.md).

Before finishing, verify:
- all 7 layers exist
- required files exist
- headers follow the standard
- decision protocol sections are complete
- commands cover all required categories
- boardroom is complete
- freshness system is applied
- `bundle.conf` exists
- bundling path is intact

If there are gaps, fix them before presenting the result as complete.

## Response Pattern

When running this skill, use this sequence unless the user asks for a different interaction style:

1. State the target profession and whether it appears to fit the framework.
2. Run the discovery interview.
3. Present the vocabulary map.
4. Present the design choices that need explicit user approval.
5. Generate files directly when approved.
6. Run the compliance check.
7. Summarize what was created and what the user should validate next.

## Quality Bar

The generated profession must feel like it was designed by:
- a real expert in the profession
- a maintainer of this framework
- someone who understands how professionals actually work under pressure

The result should not read like a thin search-and-replace of coach or manager. It should preserve the framework while clearly expressing the logic, tradeoffs, vocabulary, and rhythms of the new profession.