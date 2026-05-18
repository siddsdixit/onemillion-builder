# Day 13: Build — Core Feature (Sprint S2)

**Time: 20 minutes | Phase: BUILD**

---

## Learn (5 min)

Sprint S2 is your product's primary feature — the thing that makes it worth using. This is where your product stops being a shell and starts being something real.

The BUILD agent implements the full stack for each feature: backend (repository → service → router) and frontend (page → components → hooks → forms). It follows the patterns established in S0: same API client, same query hooks, same error handling.

After S2, a user can: log in, create the primary resource, view it, edit it, and delete it. That's the core loop.

## Do (10 min)

1. Continue to S2:
   ```
   Continue to sprint S2
   ```

2. When S2 completes, test the core flow:
   - Log in as your test user
   - Create a resource (your product's primary entity)
   - View it in the list
   - Click into the detail view
   - Edit it
   - Delete it

3. Check the test file that was written:
   ```bash
   cat backend/tests/test_api/test_s2_*.py
   ```

4. Run the tests:
   ```bash
   cd backend && PYTHONPATH=. pytest tests/test_api/ -q
   ```

## Reflect (5 min)

**Assignment:** Walk through the core flow as a new user. What feels smooth? What feels broken or confusing? Write down 3 things you'd improve.

---

**→ Next: [Day 14 — Build: Remaining Features](../day-14/learn.md)**
