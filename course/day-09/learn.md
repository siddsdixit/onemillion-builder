# Day 9: Architect the System

**Time: 20 minutes | Phase: PLAN**

---

## Learn (5 min)

The PLAN agent is a Staff Software Architect. It reads the refined PRD, the design specs, and the locked tech stack, then produces two things:

1. **`architecture.md`** — system overview, folder tree, module list, API standards, env vars. Under 200 lines.
2. **Sprint briefs** — one file per sprint, each completely self-contained. The BUILD agent reads one sprint brief and has everything it needs to implement that sprint: entity schemas, endpoint specs, component designs, acceptance criteria, verification gate, and git commit message.

The sprint briefs are contracts. Every decision in a brief traces back to the spec.

## Do (10 min)

1. Continue to plan:
   ```
   Continue to plan
   ```

2. Review the architecture:
   ```bash
   cat .onemillion/architecture.md
   ```

3. Count the sprints:
   ```bash
   ls .onemillion/sprints/
   ```

4. Read one sprint brief to see the level of detail:
   ```bash
   cat .onemillion/sprints/S0-foundation.md
   ```

5. Ask the architect about a decision:
   ```
   /ask Why did the plan agent choose [specific architecture decision]? What would be the alternative?
   ```

## Reflect (5 min)

**Assignment:** How many sprints does your product have? What's in each one? Does the sprint sequencing make sense — do later sprints depend on earlier ones correctly?

---

**→ Next: [Day 10 — Validate the Plan](../day-10/learn.md)**
