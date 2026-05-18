# Day 4: Refine Your Vision

**Time: 20 minutes | Phase: IDEA (edit)**

---

## Learn (5 min)

The IDEA agent has an edit mode. If you say "add a feature" or "change the persona" or "rename the app," it modifies the existing PRD in place — it doesn't regenerate from scratch.

Today you'll review the PRD critically and make changes. Real PRDs go through multiple iterations. The goal is to end Day 4 with a PRD you'd confidently hand to an engineer.

Ask yourself:
- Is every feature specific enough to implement? (not "good UX" but "card grid with pagination")
- Is the persona specific enough to test? (not "busy professional" but "marketing manager at 20-person SaaS company")
- Are the [MVP] features the absolute minimum to validate the hypothesis?

## Do (10 min)

1. Re-read `.onemillion/prd.md` critically.

2. Make edits by telling the agent what to change:
   ```
   Update the PRD: add a feature for [X]. Also, the persona should be more specific — she's a [specific role] at [specific context].
   ```

3. Ask the IDEA agent what it thinks:
   ```
   /ask Looking at my PRD, are there any implied features I'm missing? Are my MVP features truly the minimum?
   ```

4. Lock the scope. Ask:
   ```
   /ask Given my idea, what's the single riskiest assumption in my MVP hypothesis?
   ```

5. When satisfied, tell the orchestrator:
   ```
   The PRD looks good. Continue to the next phase.
   ```

## Reflect (5 min)

**Assignment:** What is the riskiest assumption in your MVP? What's the fastest way to test it?

---

**→ Next: [Day 5 — Engineering Requirements](../day-05/learn.md)**
