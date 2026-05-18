# Day 14: Build — Remaining Features (Sprint S3+)

**Time: 20 minutes | Phase: BUILD**

---

## Learn (5 min)

By now you have a working core loop. Today, the BUILD agent finishes the remaining MVP sprints — all the supporting features that make the product feel complete.

The BART loop (Build, Adapt, Resolve, Track) runs during this phase. If the agent discovers something can't be implemented exactly as specified, it tells you immediately with a concrete alternative. It never silently deviates.

After today, you'll have a functionally complete MVP. Every [MVP] feature from your spec will be implemented and tested.

## Do (10 min)

1. Continue the remaining sprints:
   ```
   Continue building remaining sprints
   ```

   The agent will work through S3, S4, etc. until all MVP sprints are complete.

2. Monitor todo.md for progress:
   ```bash
   cat .onemillion/todo.md
   ```

3. When all sprints complete, do a full verification:
   - Walk through every feature from your refined-prd.md
   - Test on mobile viewport (Chrome DevTools, 375px)
   - Check that the seed data makes every page look good

4. If something doesn't work, tell the debug agent:
   ```
   /debug [describe what's broken]
   ```

## Reflect (5 min)

**Assignment:** Your MVP is built. Rate each feature 1-5 for: (1) implementation quality and (2) user value. What's the gap between what you specified and what got built?

---

**→ Next: [Day 15 — Test Everything](../day-15/learn.md)**
