# Day 11: Build — Foundation (Sprint S0)

**Time: 20 minutes | Phase: BUILD**

---

## Learn (5 min)

The BUILD agent is a Senior Full-Stack Engineer. It reads one sprint brief and executes everything in it — no hand-holding, no asking permission, no placeholder code.

Sprint S0 is special: it creates the project from scratch. By the end of S0 you'll have:
- Backend: FastAPI app with health endpoint, middleware chain, error handling, Sentry
- Frontend: Next.js app with MUI theme, API client, React Query provider, app shell
- Database: MongoDB Atlas connected
- Seed data: Your `seed-data.json` loaded — the app looks alive immediately

**Validation runs after every file change.** If the build fails validation, the agent fixes it before writing more code. You won't see broken states.

## Do (10 min)

1. Start the build:
   ```
   Continue to build
   ```

2. Watch the agent work. It will announce each sprint:
   ```
   ── Sprint S0: Foundation (1/N) ──
   ```

3. When S0 completes, the agent will print the verification gate. Run it:
   ```bash
   cd backend && uvicorn main:app --port 8000 &
   curl http://localhost:8000/api/v1/health
   # → {"status": "ok"}

   cd frontend && npm run dev &
   # Open http://localhost:3000 — you should see your app with seed data
   ```

4. Confirm S0 to advance to S1:
   ```
   S0 verified. Continue.
   ```

## Reflect (5 min)

**Assignment:** Describe what your app looks like right now. Does the seed data make it feel real? What would you want to change before showing it to a user?

---

**→ Next: [Day 12 — Build: Auth](../day-12/learn.md)**
