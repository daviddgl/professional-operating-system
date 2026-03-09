# GENERATOR_PROMPT.md — Replaced by Skill

> **Status:** Replaced by the project skill at `.github/skills/create-profession/`
>
> The profession-generation workflow now lives in a reusable skill instead of a
> standalone prompt stub. Use the `create-profession` skill to generate a full,
> spec-compliant Profession Operating System variant directly into
> `references/<profession>-os/`.
>
> The skill reads the framework spec and both reference implementations inline,
> builds the vocabulary map, designs the decision model, generates the files,
> and validates the result against the compliance checklist.

---

## Use This Instead

Use:
- `.github/skills/create-profession/SKILL.md`

Supporting skill references:
- `.github/skills/create-profession/references/vocabulary-template.md`
- `.github/skills/create-profession/references/compliance-checklist.md`
- `.github/skills/create-profession/references/generation-sequence.md`

## Expected Workflow

1. Invoke the `create-profession` skill with the target profession.
2. Confirm the profession fit and vocabulary map.
3. Approve the proposed design choices.
4. Generate the full variant directly under `references/<profession>-os/`.
5. Validate the result against the framework checklist.

## Framework Sources

The skill uses these repository sources as canonical inputs:
- `PROFESSION_SPEC.md`
- `references/coach-os/`
- `references/manager-os/`
- `scripts/bundle.sh`
