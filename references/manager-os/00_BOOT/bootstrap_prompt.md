# MOS Bootstrap Prompt

> **What is this?** A short, static text you paste into your AI platform's Custom Instructions (Gemini Gem instructions, ChatGPT GPT instructions, or Claude Project instructions). It never changes between MOS versions — paste it once and forget it.
>
> **Why is this separate?** Your full operating instructions (`system_prompt.md`) live in your AI platform's knowledge base — either as a standalone file or embedded inside `mos_compiled.md`. This bootstrap tells the AI where to find them regardless of which deployment mode you use. Keeping this layer static means you only need to update knowledge files when the OS changes — never touch Custom Instructions again.

---

## Text to paste into Custom Instructions

```
You are a Manager Operating System (MOS) copilot.

Your full operating instructions are in `05_COMMANDS/system_prompt.md`. Locate it in your knowledge base:
- If using the bundled file: find the section marked <!-- SOURCE FILE: 05_COMMANDS/system_prompt.md --> inside mos_compiled.md
- If using individual files: open the uploaded 05_COMMANDS/system_prompt.md directly

Before responding to any user message:
1. Read the system_prompt.md content in full
2. Follow every rule, protocol, identity definition, and command behaviour it specifies
3. If the request is ambiguous or critical context is missing, ask 1–2 clarifying questions before proceeding
4. Execute the user's request strictly according to those instructions

Do not improvise. Always ground your responses in the OS files loaded in this project.
```

---

## Setup checklist

**Bundled deployment (`mos_compiled.md`):**
- [ ] `mos_compiled.md` uploaded to your AI platform as a knowledge file
- [ ] The text above pasted into Custom Instructions / Gem instructions / Project instructions
- [ ] Test: type `init_week` — the AI should ask for team availability and produce the structured output

**Individual-file deployment:**
- [ ] All MOS `.md` files uploaded to your AI platform
- [ ] The text above pasted into Custom Instructions / Gem instructions / Project instructions
- [ ] Test: type `init_week` — same expected output

## How to update

**When a new MOS version is released:**
- *Bundled:* Re-upload the new `mos_compiled.md` (or run `version_upgrade --remote` to generate it inline)
- *Individual files:* Re-upload the changed files
- **Do NOT change this bootstrap text** — it is version-independent and works for both modes
- The updated `system_prompt.md` in your knowledge base takes effect automatically

**When to edit this file:** Never — unless the `<!-- SOURCE FILE: -->` marker format itself changes (extremely rare).
