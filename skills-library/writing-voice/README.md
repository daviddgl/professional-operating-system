# Writing Voice Skill

> **Type:** Universal — works for any profession variant  
> **Enables:** The AI copilot writes content that sounds like you

---

## What This Skill Enables

When you ask your AI copilot to draft a LinkedIn post, write a client email, create a proposal, or produce any written content on your behalf — without a voice profile, the output sounds generic. With this skill, the AI knows:

- Your tone (how formal or conversational you are)
- Your sentence patterns (how you open, close, paragraph)
- Your signature phrases and expressions
- What you avoid (jargon, corporate speak, hedging)
- How you relate to your audience (peer, mentor, expert, friend)

The result: AI-written content that sounds like you wrote it.

## Who Should Use This

Anyone who produces written content as part of their professional practice:
- **Coaches:** LinkedIn posts, client proposals, session recaps, programme descriptions
- **Managers:** Team updates, performance feedback, stakeholder communications, job descriptions
- **Any professional:** Any role that writes for an audience

## How to Generate Your Skill

1. Open the `generation_prompt.md` file in this directory
2. Copy the full prompt
3. Open your AI conversation (the same one where your OS is loaded)
4. Paste the prompt
5. Follow the instructions — you'll provide 3 writing samples
6. The AI will analyse your patterns and produce a complete `writing_voice.md` file
7. Save the output to `skills/writing_voice.md` in your reference folder
8. Re-run `bundle.sh` — your `skills_compiled.md` will be regenerated

## Activation

The skill has two activation paths:

- **Auto:** Ask naturally — "write a LinkedIn post about...", "draft an email to my client" — and the skill fires automatically
- **Explicit:** Say "write as me", "use my writing voice", or "use writing_voice" to invoke it directly

After each output, the AI appends `_Writing Voice skill applied._` so you always know when your voice profile is active.

To bypass the skill for a specific output, include "skip writing voice", "generic style", or "don't use my voice" in your request.
