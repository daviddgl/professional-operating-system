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

Once loaded, the skill activates automatically whenever you ask the AI to write content on your behalf. No command needed — just ask naturally ("write a LinkedIn post about...") and the AI applies your voice profile.
