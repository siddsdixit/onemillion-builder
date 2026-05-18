# Day 6: Validate the Spec

**Time: 20 minutes | Phase: VALIDATE-SPEC**

---

## Learn (5 min)

Before design begins, the VALIDATE-SPEC agent does a quality gate. It checks:
- **Completeness:** Are all features from the PRD in the spec? Does every entity have a full CRUD chain?
- **Consistency:** Are field names consistent? Do entity relationships make sense in both directions?
- **Buildability:** Are acceptance criteria actually testable? Does the auth model make sense?

The verdict is PASS, WARN, or FAIL. FAIL blocks advancement to design. WARN lets you advance with noted caveats.

This step exists because catching ambiguity before design is cheap. Catching it during build is expensive.

## Do (10 min)

1. Run the spec validator:
   ```
   Continue to validate-spec
   ```

2. Read the validation report:
   ```bash
   cat .onemillion/validation-spec.md
   ```

3. If there are FAILs, fix them:
   ```
   Fix the spec: [describe the issue found in validation]
   ```
   Then re-run validate-spec.

4. Ask the ASK agent about any WARN items:
   ```
   /ask The validate-spec found a WARN about [issue]. Should I fix it now or is this acceptable?
   ```

## Reflect (5 min)

**Assignment:** What did the validator catch that you missed? What's the hardest spec decision you had to make today?

---

**→ Next: [Day 7 — Design Your Product](../day-07/learn.md)**
