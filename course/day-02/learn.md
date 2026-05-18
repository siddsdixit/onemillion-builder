# Day 2: Understand the System

**Time: 20 minutes | Phase: Setup**

---

## Learn (5 min)

Before building, understand what you're working with.

The 9-step flow is:
```
IDEA → SPEC → DESIGN → PLAN → BUILD → TEST → GUARD → SHIP → SELL
```

Each step is a specialist agent. The **Orchestrator** is the outer loop — it quality-checks each agent's output before advancing. It can run in three modes:

- **Supervised** (default): asks before advancing each phase
- **Semi-auto**: auto-advances planning, asks before build and ship
- **Autonomous**: runs the full flow, stops only for blockers

State is tracked in `.onemillion/state.json`. If you close Claude Code and reopen it, the Orchestrator reads state.json and resumes where you left off.

## Do (10 min)

1. Look at the orchestrator agent:
   ```bash
   cat ~/.claude/agents/orchestrator.md | head -50
   ```

2. Look at the state.json schema — this is what gets created when you run the flow:
   ```bash
   # The orchestrator will create this structure in your project
   # .onemillion/state.json
   ```

3. Ask the orchestrator to explain the flow:
   ```
   /ask Explain the full build flow — what does each agent produce and what does the orchestrator check between phases?
   ```

4. Read the tech stack to understand what you'll be building with:
   ```bash
   cat ~/.claude/skills/tech_stack/SKILL.md | head -80
   ```

## Reflect (5 min)

**Assignment:** Write: Do you want to build a web app, an AI agent, or a hybrid? What's the difference for your idea? (Hint: web app = browser-based UI, agent = AI automation, hybrid = web app with AI built in.)

---

**→ Next: [Day 3 — Capture Your Idea](../day-03/learn.md)**
