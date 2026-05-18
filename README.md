# 🚀 OneMillion Builder System

_Created by [Sid Dixit](https://onemillion.build)_

---

You've seen people ship full products in days using AI. They have Claude Code wired up with agents for every phase — ideation, spec, design, build, test, security, deployment, launch. You try to copy it. You're missing half the context. Three hours in, you're debugging a system you don't understand.

**This fixes that.**

- **18 days, one phase at a time.** No information overload. You build one thing each day and understand it before moving on.
- **20 minutes per day.** Short enough to fit into any schedule.
- **A real product, shipped to production.** By the end, you'll have a working app live on the internet — built by you, with AI as your co-founder.
- **Free forever.** No subscriptions. Bring your own API key.
- **Uses the tool to learn the tool.** The agents read the course files and guide you through building. Meta and effective.

---

## 🧠 What Is This?

**OneMillion Builder System** is an open-source collection of Claude Code agents that guide you through a complete product development lifecycle — from raw idea to shipped, marketed product.

Nine specialized agents. One orchestrator. Eighteen days.

```
💡 IDEA → 📝 SPEC → 🏗️ PLAN → 🎨 DESIGN → 💻 BUILD → 🧪 TEST → 🔒 GUARD → 🚀 SHIP → 📣 SELL
```

Each agent knows its job deeply. The orchestrator knows the whole picture.

---

## 🛠️ What You Need

- [Claude Code](https://claude.ai/code) (CLI or VS Code extension)
- An [Anthropic API key](https://console.anthropic.com) (Claude Sonnet is sufficient)
- Node.js 20+ and Python 3.11+ (the course walks you through this)
- 20 minutes per day for 18 days

---

## 📚 Course Days

| Day | What You Build |
|-----|----------------|
| [Day 1: Install & Configure](./course/day-01/learn.md) | Claude Code running with OneMillion agents loaded |
| [Day 2: Understand the System](./course/day-02/learn.md) | The 9-step flow, orchestrator logic, and how agents hand off |
| [Day 3: Capture Your Idea](./course/day-03/learn.md) | A real PRD from a single sentence — using the IDEA agent |
| [Day 4: Refine Your Vision](./course/day-04/learn.md) | Edit your PRD, define scope, and lock your MVP hypothesis |
| [Day 5: Engineering Requirements](./course/day-05/learn.md) | A CRUD chain for every entity using the SPEC agent |
| [Day 6: Validate the Spec](./course/day-06/learn.md) | Catch ambiguities before they become bugs |
| [Day 7: Design Your Product](./course/day-07/learn.md) | Screen specs, design system, and seed data using DESIGN agent |
| [Day 8: Refine the Design](./course/day-08/learn.md) | HTML mockup preview and design iteration |
| [Day 9: Architect the System](./course/day-09/learn.md) | Architecture doc and sprint briefs using the PLAN agent |
| [Day 10: Validate the Plan](./course/day-10/learn.md) | Stress-test architecture before writing a single line of code |
| [Day 11: Build — Foundation](./course/day-11/learn.md) | Sprint S0: repo, DB, health endpoint, auth scaffold |
| [Day 12: Build — Auth](./course/day-12/learn.md) | Sprint S1: register, login, JWT, protected routes |
| [Day 13: Build — Core Feature](./course/day-13/learn.md) | Sprint S2: your product's primary feature, end to end |
| [Day 14: Build — Remaining Features](./course/day-14/learn.md) | Sprint S3+: finish the MVP feature set |
| [Day 15: Test Everything](./course/day-15/learn.md) | Backend tests, E2E Playwright, accessibility — using TEST agent |
| [Day 16: Security Audit](./course/day-16/learn.md) | OWASP Top 10, secrets scan, SAST — using GUARD agent |
| [Day 17: Ship to Production](./course/day-17/learn.md) | Deploy backend + frontend, smoke tests, monitoring — SHIP agent |
| [Day 18: Launch](./course/day-18/learn.md) | Landing copy, social posts, SEO, investor deck — SELL agent |

---

## 🚀 Quick Start (5 minutes)

```bash
# 1. Clone this repo
git clone https://github.com/your-org/onemillion-builder
cd onemillion-builder

# 2. Copy agents to Claude config
cp -r agents/* ~/.claude/agents/
cp -r skills/* ~/.claude/skills/

# 3. Open Claude Code in your project directory
mkdir my-product && cd my-product
claude

# 4. Start the flow
# Type: "I want to build [your idea]"
# The orchestrator will take it from there.
```

Or follow the [18-day course](./course/README.md) for the structured path.

---

## 🤖 The 9 Agents

| Agent | Role | When It Runs |
|-------|------|--------------|
| **Orchestrator** | Outer-loop brain — routes, quality-checks, adapts | Always active |
| **IDEA** | Startup Product Advisor — PRD from any input | Day 3-4 |
| **SPEC** | Principal PM — CRUD chains, acceptance criteria | Day 5-6 |
| **DESIGN** | Lead Designer — design system, screens, seed data | Day 7-8 |
| **PLAN** | Staff Architect — architecture doc, sprint briefs | Day 9-10 |
| **BUILD** | Senior Engineer — executes one sprint at a time | Day 11-14 |
| **TEST** | VP QA — backend tests, E2E, accessibility | Day 15 |
| **GUARD** | Security Engineer — OWASP Top 10, secrets, SAST | Day 16 |
| **SHIP** | DevOps — deploy, verify, monitor, rollback test | Day 17 |
| **SELL** | Growth Marketing — copy, social posts, SEO, deck | Day 18 |

**Anytime helpers:** ASK (questions), DEBUG (bugs), REFACTOR (code cleanup), REVIEW (spec drift)

---

## 🏗️ The Locked Tech Stack

Every product built with this system uses the same proven stack — optimized for zero DevOps overhead:

- **Frontend:** Next.js + TypeScript + MUI (Material Design 3)
- **Backend:** Python + FastAPI + Pydantic v2
- **Database:** MongoDB Atlas (free tier)
- **Auth:** JWT + Argon2
- **Deploy:** Vercel (frontend) + Railway (backend)
- **Testing:** pytest + Playwright + axe-core
- **Monitoring:** Sentry (free tier)

Three infrastructure services. Proven at scale. Zero migration overhead.

---

## 📁 Repository Structure

```
onemillion-builder/
├── README.md              ← You are here
├── CLAUDE.md              ← Wires agents into Claude Code
├── agents/                ← 17 specialist agents
│   ├── orchestrator.md
│   ├── idea.md
│   ├── spec.md
│   └── ...
├── skills/                ← Shared reference skills
│   ├── tech_stack/
│   ├── checklist_security/
│   └── ...
├── course/                ← 18-day structured course
│   ├── README.md
│   ├── day-01/
│   └── ...
└── certification/         ← Completion criteria + badge
```

---

## 🎓 Certification

Complete the 18-day course and ship a real product to get your **OneMillion Builder** certificate. See [certification/README.md](./certification/README.md).

---

## 🤝 Contributing

- Found a bug in an agent? Open an issue or PR.
- Built something cool? Share it — tag `#OneMillion` on X.
- Want to add a skill? Check the [skill format](./skills/) and submit a PR.

---

## 📄 License

MIT. Free to use, fork, and build on. If you share it, credit the source.

---

## 💬 Community

- **X / Twitter:** [@onemillionbuild](https://x.com/onemillionbuild)
- **Website:** [onemillion.build](https://onemillion.build)
- **Docs:** [docs.onemillion.build](https://docs.onemillion.build)

---

_The million starts with one. Let's build._
