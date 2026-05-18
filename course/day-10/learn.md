# Day 10: Validate the Plan

**Time: 20 minutes | Phase: VALIDATE-PLAN**

---

## Learn (5 min)

The VALIDATE-PLAN agent stress-tests the architecture before a single line of code is written. It checks:

- **Feasibility:** Are banned technologies present? Is the 3-Service Rule respected?
- **Completeness:** Does every MVP feature appear in a sprint? Are all entity schemas present?
- **Sprint coherence:** Is each sprint self-contained? Are they sequenced correctly?

This is your last chance to catch architecture problems cheaply. Once BUILD starts, changing the architecture is expensive. Today, it's free.

## Do (10 min)

1. Run the plan validator:
   ```
   Continue to validate-plan
   ```

2. Read the validation report:
   ```bash
   cat .onemillion/validation-plan.md
   ```

3. Fix any FAILs by asking the plan agent to revise:
   ```
   Fix the plan: [describe the issue]
   ```

4. Ask the ASK agent to explain the tech stack constraints:
   ```
   /ask Why does the tech stack forbid Redis for MVP? What happens when I need a job queue?
   ```

5. Review todo.md — it now has your sprint checklist:
   ```bash
   cat .onemillion/todo.md
   ```

## Reflect (5 min)

**Assignment:** You're about to start building. What are you most nervous about? What feels unclear? Write it down — the BUILD agent will handle most of it, but naming your concerns now helps you spot issues early.

---

**→ Next: [Day 11 — Build: Foundation](../day-11/learn.md)**
