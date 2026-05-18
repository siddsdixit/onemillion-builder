# Day 15: Test Everything

**Time: 20 minutes | Phase: TEST**

---

## Learn (5 min)

The TEST agent runs 5 phases:

1. **Backend tests** — runs the test files the BUILD agent wrote for each sprint
2. **Cross-cutting tests** — data integrity, security (401/403, IDOR), performance benchmarks
3. **E2E tests with Playwright** — browser-based tests that actually click through your UI
4. **Accessibility** — axe-core scans every page for WCAG violations
5. **CI setup** — GitHub Actions workflow that runs all tests on every push

The BUILD agent writes per-sprint tests. The TEST agent runs them, catches what was missed, and adds the browser-level tests that unit tests can't catch.

## Do (10 min)

1. Run the test agent:
   ```
   Continue to test
   ```

2. Watch the phases run. Note the coverage percentage at the end of Phase 2.

3. When Phase 3 (E2E) runs, Playwright will open a browser and click through your app. Watch it.

4. Review the test results:
   ```bash
   cat .onemillion/test-results.md
   ```

5. If tests fail, the agent will fix them. If it can't fix in 2 attempts, it flags the issue. Check for unresolved failures.

## Reflect (5 min)

**Assignment:** What did the tests catch that you didn't notice during manual testing? What's your test coverage percentage? Is there a test case you wish existed but doesn't?

---

**→ Next: [Day 16 — Security Audit](../day-16/learn.md)**
