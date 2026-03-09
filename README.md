# Profession Operating System

> An AI-native framework for structured decision-making across professions.
> Give your AI copilot the full context of your role, your team, your organisation,
> and your values — so it can help you make better decisions under pressure.

Created by **David Garcia Lopez**.

- Contact: [CONTACT.md](CONTACT.md)
- Contributing: [CONTRIBUTING.md](CONTRIBUTING.md)
- Authors: [AUTHORS.md](AUTHORS.md)

---

## What Is This?

A **Profession Operating System** is a set of structured markdown files that encode how you think, decide, and operate in your profession. Upload them to an AI platform (ChatGPT, Gemini, Claude) and get a personalised decision-support copilot that knows your values, your team or clients, your organisation's strategy, and your current quarter.

The key idea: **separate the logic (how you decide) from the data (where you work)**. The logic is portable — it travels with you across teams, companies, and client cohorts. The data is replaceable.

---

## Choose Your Path

### I want to USE a pre-built profession

| Profession | Status | Get Started |
|-----------|--------|------------|
| Engineering Manager | ✅ Available | [references/manager-os/](references/manager-os/) |
| Career Coach | ✅ Available | [references/coach-os/](references/coach-os/) |
| Product Manager | 🔜 Coming soon | — |

**How it works:**
1. Navigate to the profession directory
2. Read `README.md` for a quick start
3. Paste `SETUP_WIZARD.md` into your AI tool
4. Answer the questions — the AI fills in your personal data
5. Run `scripts/bundle.sh` to compile, upload to your AI platform
6. Type `init_week` and you're live

### I want to CREATE a new profession variant

1. Read [PROFESSION_SPEC.md](PROFESSION_SPEC.md) — the structural rules every OS must follow
2. Invoke the `create-profession` skill in your AI tool — it interviews you and generates all files for your profession
3. Review, refine, validate against the spec, and publish

---

## Architecture (All Professions)

Every Profession OS follows the same 7-layer structure:

| Layer | Folder | Lifecycle | Portable | Purpose |
|-------|--------|-----------|----------|---------|
| 00 | `00_BOOT/` | Permanent | Yes | System manual — read this first |
| 01 | `01_KERNEL/` | Permanent | Yes | Your portable philosophy and decision logic |
| 02 | `02_CONFIG/` | Per-context | No | Your current organisation or practice |
| 03 | `03_DRIVERS/` | Per-roster | No | Your current team or clients |
| 04 | `04_PROCESSES/` | Per-quarter | No | Your current quarterly plan |
| 05 | `05_COMMANDS/` | Permanent | Yes | The AI command interface |
| 06 | `06_BOARDROOM/` | Permanent | Yes | Your virtual advisory council |

**The portability model:** Change companies? Keep KERNEL + COMMANDS + BOARDROOM, update CONFIG, replace DRIVERS + PROCESSES. Your decision playbook travels with you; your context does not.

See [PROFESSION_SPEC.md](PROFESSION_SPEC.md) for the full specification governing all profession variants.

---

## Repository Structure

```
profession-operating-system/
├── PROFESSION_SPEC.md         # Framework specification (structural rules)
├── README.md                  # This file
├── CONTRIBUTING.md            # How to contribute
├── LICENSE                    # MIT
│
├── references/
│   ├── manager-os/            # Engineering Manager OS — reference implementation
│   │   ├── 00_BOOT/ through 06_BOARDROOM/
│   │   ├── scripts/bundle.sh
│   │   ├── bundle.conf
│   │   └── SETUP_WIZARD.md, README.md, ARCHITECTURE.md, CHANGELOG.md
│   │
│   └── coach-os/              # Career Coach OS — reference implementation
│       └── (same structure)
│
└── scripts/
    └── bundle.sh              # Parameterized bundle generator (works for any profession)
```

Each reference in `references/` is a fully standalone, self-contained OS. You can use it independently without any other files from this repository.

---

## The Bundle Script

Every profession repo contains `scripts/bundle.sh` and a `bundle.conf` file. Running the script compiles all OS files into a single markdown document for easy AI platform upload.

```bash
# From any profession directory:
cd references/coach-os
./scripts/bundle.sh
# → Outputs: bundle/cos_compiled.md

cd references/manager-os
./scripts/bundle.sh
# → Outputs: bundle/mos_compiled.md
```

The root `scripts/bundle.sh` is the canonical version — identical to the per-reference copies. See [PROFESSION_SPEC.md §13](PROFESSION_SPEC.md) for the spec compliance checklist.

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to contribute improvements to the framework or submit a new profession variant.

---

## License

MIT — see [LICENSE](LICENSE).
