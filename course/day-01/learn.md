# Day 1: Install & Configure

**Time: 20 minutes | Phase: Setup**

---

## Learn (5 min)

Claude Code is a CLI that brings Claude into your terminal and editor. Unlike a chat interface, it has access to your filesystem, can run commands, write code, and call tools. The OneMillion agents extend it with specialist roles — each one optimized for a specific phase of product development.

Today you're installing the system and verifying it works.

## Do (10 min)

1. Follow [Getting Started](../getting-started.md) if you haven't yet.

2. Verify agents are installed:
   ```bash
   ls ~/.claude/agents/
   # Should show: orchestrator.md, idea.md, spec.md, design.md, plan.md, build.md, test.md, guard.md, ship.md, sell.md
   ```

3. Create your project directory and open Claude Code:
   ```bash
   mkdir my-product && cd my-product
   claude
   ```

4. Say hello to the orchestrator. Type:
   ```
   Hello, what can you help me build?
   ```

   The orchestrator should respond with 8 flow options. If it does, setup is complete.

5. Try the ASK agent on itself:
   ```
   /ask How do the agents hand off between phases?
   ```

## Reflect (5 min)

**Assignment:** In your build journal, write one paragraph answering: What product idea are you considering building? Don't commit to it yet — just brainstorm. What problem does it solve? Who has that problem?

---

**→ Next: [Day 2 — Understand the System](../day-02/learn.md)**
