# Day 5: Engineering Requirements

**Time: 20 minutes | Phase: SPEC**

---

## Learn (5 min)

The SPEC agent transforms your PRD into engineering requirements. Its superpower is the **CRUD chain** — for every entity (Recipe, User, Comment, Order...) it asks: can it be Created? Read? Updated? Deleted? Listed?

Entities that should have "delete" but the PRD forgot to mention it? The SPEC agent adds it automatically, tagged [MVP].

It also writes **Given/When/Then acceptance criteria** — testable statements that tell you exactly when a feature is "done." Not "user can create a recipe" but "Given a logged-in user, When they submit the create recipe form with valid data, Then a new recipe appears in their list with a 201 response."

## Do (10 min)

1. Continue the flow (or switch to spec directly):
   ```
   Continue to spec
   ```

2. The SPEC agent reads your PRD and generates `refined-prd.md`. Watch it:
   - How many entities did it find?
   - What CRUD operations did it add that weren't explicit in the PRD?
   - How many acceptance criteria are there?

3. Review the output:
   ```bash
   cat .onemillion/refined-prd.md | head -100
   ```

4. Ask the SPEC agent to explain one of its decisions:
   ```
   /ask Why did the spec agent add [specific operation] for [entity]?
   ```

## Reflect (5 min)

**Assignment:** Count your entities and CRUD operations. Write: "My product has [N] entities. The SPEC agent added [N] operations I hadn't explicitly specified. The most important acceptance criterion is: [paste your most critical Given/When/Then]."

---

**→ Next: [Day 6 — Validate the Spec](../day-06/learn.md)**
