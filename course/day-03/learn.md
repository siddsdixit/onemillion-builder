# Day 3: Capture Your Idea

**Time: 20 minutes | Phase: IDEA**

---

## Learn (5 min)

The IDEA agent is a Startup Product Advisor. Give it a sentence — or ten — and it produces a complete PRD (Product Requirements Document) covering: persona, features, market research, and MVP hypothesis.

The key insight: the PRD captures WHAT to build, never HOW. No technology mentions, no database schemas, no API design. Just what users need and why.

Every feature gets tagged [MVP] or [POST-MVP]. [POST-MVP] doesn't mean "cut" — it means "ship later." The scope budget for a 2.5-week build is 5 MVP user stories.

## Do (10 min)

1. In your project directory, run Claude Code:
   ```bash
   cd my-product && claude
   ```

2. Tell the orchestrator your idea:
   ```
   I want to build [your idea here]
   ```

   The orchestrator will detect a new product idea and route to the IDEA agent.

3. The IDEA agent may ask 1-3 clarifying questions. Answer them directly.

4. The agent generates a PRD and writes it to `.onemillion/prd.md`. Review it:
   ```bash
   cat .onemillion/prd.md
   ```

5. Check the state:
   ```bash
   cat .onemillion/state.json
   ```
   You should see `"current_phase": "idea"`, `"status": "completed"`.

## Reflect (5 min)

**Assignment:** Read your PRD. Is the persona accurate? Is the MVP hypothesis testable? Write: "My product solves [X] for [Y persona] by [Z mechanism]. I can validate this by shipping [specific features]."

---

**→ Next: [Day 4 — Refine Your Vision](../day-04/learn.md)**
