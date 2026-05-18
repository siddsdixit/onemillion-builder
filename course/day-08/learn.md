# Day 8: Refine the Design

**Time: 20 minutes | Phase: DESIGN (iteration)**

---

## Learn (5 min)

Design is iterative. The DESIGN agent is in collaborative mode — it proposes, you react, it refines. Today you make two or three targeted improvements to the design before locking it.

Focus on what will matter when you see the real app:
- Does the navigation pattern make sense on mobile?
- Does the empty state have a clear CTA?
- Does the card layout work with your actual data?

Once you approve the design, it's locked. The PLAN agent will inline design specs into every sprint brief so the BUILD agent never needs to guess about layout.

## Do (10 min)

1. Re-review the mockup at `http://localhost:8080`.

2. Make specific changes:
   ```
   Update the design:
   - Change the navigation to a bottom tab bar (mobile-first)
   - Make the card images taller (use 3:2 aspect ratio)
   - Add a better empty state for the main list with an illustration description
   ```

3. Check the seed data makes sense:
   ```bash
   cat .onemillion/seed-data.json | python3 -m json.tool | head -40
   ```

4. Approve the design:
   ```
   The design looks good. Lock it and continue to plan.
   ```

## Reflect (5 min)

**Assignment:** What does your app's design direction say about the product? If someone saw the mockup without any context, what would they assume the product is?

---

**→ Next: [Day 9 — Architect the System](../day-09/learn.md)**
