# Day 6 — Core Feature CRUD

**Target length:** 15-20 minutes (Week 1's biggest day)
**Energy:** Builder mode — calm, focused, "let's ship the thing"
**Priority:** P0 — record after Day 5

---

## Why This Loom Matters

Day 6 is when Week 1 culminates. CRUD = Create / Read / Update / Delete. By end of day, the builder has a REAL feature on a REAL URL.

Without this Loom, builders ship buggy CRUD with missing auth checks. They miss the incognito RLS re-test. They cargo-cult React hooks.

---

## Pre-Recording (10 min setup)

- [ ] Day 5 project complete (`~/sid-loom-build/`) — auth works, RLS confirmed
- [ ] `deliverables` table exists with RLS policy from Day 5
- [ ] Both dev terminals running (`npm run dev`)
- [ ] Browser tabs ready: localhost:3000 (your app), Supabase dashboard
- [ ] Two test accounts ready (`sid+test1@gmail.com`, `sid+test2@gmail.com`) — from Day 5
- [ ] Incognito browser closed (you'll open it later — important: incognito stays clean)
- [ ] Claude Code open + authenticated

---

## Cold Open (0:00 - 0:45)

Show a finished version of your app — `/deliverables` page with a list, an "Add" form, items that can be marked done or deleted.

**Add an item live. Mark it done. Delete one. Show the list updating.**

**Say:**
> "By the end of this video, you'll have a real feature in your app — Create, Read, Update, Delete. Full CRUD. Working. Deployed. With proper security."

> "This is Day 6 — the biggest day of Week 1. Take your time. We'll go step by step. Let's go."

Switch to VS Code.

---

## Section 1 — The Data → API → UI Pattern (0:45 - 2:30)

Open a fresh page. Draw the pattern on screen (use a simple diagram, can be in Excalidraw or even just typed in a code comment):

```
User clicks button
  → Frontend sends request
    → API route handles it
      → Supabase query (CRUD)
        → Result back to API
          → API responds
            → Frontend updates
```

**Say:**
> "Every feature in every app follows this same pattern. Frontend triggers → API routes handle → Supabase does CRUD → results flow back. Get this pattern in your head — you'll use it 100 times."

> "Today I'm building it for `deliverables`. You're building it for YOUR main entity from your PRD."

---

## Section 2 — Big Bang Generate API Routes (2:30 - 7:00)

In Claude Code:
```
I'm on Day 6 of OneMillion. Generate full CRUD API routes for my 
"deliverables" entity in my Next.js + Supabase app.

Routes needed:
- POST /api/deliverables (create — auth required, set user_id from session)
- GET /api/deliverables (list current user's items — RLS filters)
- GET /api/deliverables/[id] (get one)
- PUT /api/deliverables/[id] (update one)
- DELETE /api/deliverables/[id] (delete one)

Each route:
- Use my server-side Supabase client (lib/supabase/server.ts)
- Check auth.getUser() → return 401 if no user
- For POST: insert with user_id = user.id
- Handle errors → return generic 500, don't leak internals

Show the plan first, then generate files.
```

When Claude responds, scan its plan. Approve.

**While Claude generates the files, narrate:**
> "Big-bang approach: I let Claude write all 5 routes at once. Other option is piece-by-piece — slower but you understand each route deeper. For engineers, big bang is faster. For first-timers, piece-by-piece is safer."

When files are written, open POST route. **Walk through it line-by-line:**

> "OK here's the POST route. Line 1: server Supabase client. Line 2: get user from session. Line 3: if no user, return 401. Line 4: parse request body. Line 5: insert into deliverables, set user_id to user.id from session — NOT from the request body. This is important. The user_id comes from the auth session. You can't trust what the request says."

This 60-sec walkthrough is the most valuable moment in the Loom.

---

## Section 3 — Build The UI (7:00 - 11:00)

In Claude:
```
Now build the UI for deliverables.

Create app/deliverables/page.tsx that:
1. Lists deliverables (call GET /api/deliverables)
2. Has a form at top to add new (calls POST)
3. Each item has a status dropdown that calls PUT
4. Each item has a delete button that calls DELETE
5. Handles loading state (skeleton)
6. Handles empty state ("No deliverables yet — add your first")
7. Handles error state ("Something went wrong")
8. Re-fetches after each mutation

Use React Server Components where possible, "use client" only on interactive parts.
Use Tailwind.
```

While Claude builds, **stop talking for a moment. Let the silence carry.** Then say:

> "Notice we didn't write a single line of code. We described what we wanted. Claude wrote it. THIS is agentic engineering. We're directors, not typists."

When done, open the file briefly to show it exists. Don't read every line.

---

## Section 4 — Test Locally (11:00 - 13:30)

Switch to browser, `localhost:3000/deliverables`.

**Empty state shows: "No deliverables yet."** Point at it.

> "Empty state. Most courses skip this. Real users see this BEFORE they see anything else. Make it welcoming."

Add a deliverable: "Acme website wireframes" / due 2026-06-15.

It appears in the list.

Change status to "in-progress" via dropdown. It updates instantly.

Add another. Delete the first.

**Say:**
> "All four CRUD operations working. Took us 11 minutes."

---

## Section 5 — 🚨 The Incognito Test (13:30 - 16:00)

THIS IS THE CRITICAL SECTION. Slow down. Be deliberate.

**Open incognito browser.** Navigate to `localhost:3000/signup`.

Sign up as the second test user.

Land on dashboard.

Navigate to `/deliverables`.

**Show: empty list. No data from User 1.**

Look at camera. Say:

> "This is the test that matters. User 2 in incognito sees NOTHING of User 1's data. That's RLS working. That's the database engine refusing to leak."

> "If User 2 had seen User 1's deliverables right now, your app is broken. You'd ship it, real users would sign up, see each others' data, and you'd be on the news for the wrong reasons."

> "Test this. Every. Time. Before you push."

---

## Section 6 — Deploy + Test Live (16:00 - 18:00)

Terminal:
```bash
git add .
git commit -m "Day 6: CRUD complete"
git push
```

Switch to Vercel dashboard. Watch the deploy.

**While waiting (~60 sec):**
> "What's about to happen: Vercel pulls the new code, runs npm install, runs npm run build, deploys to a CDN. By the time we look at our URL again, the new code is live."

Refresh your live URL. Test the same flow on production:
- Sign in
- Add a deliverable
- Mark done
- Delete

Confirm it works LIVE, not just localhost.

---

## ONE Real Moment To Leave In

If anything broken during this 15-min recording — keep it. Most likely culprits:
- Claude generates code that doesn't compile (TypeScript error)
- API route returns 401 because middleware isn't refreshing session
- UI doesn't re-fetch after mutation
- Cross-user test reveals RLS is broken somehow (this happened in the simulation — REAL bug)

Diagnose live. Fix live. Show the recovery.

---

## Closing (18:00 - 20:00)

Switch to your live URL. Take a beat.

**Say:**
> "Here's what you have right now: a real web app, with auth, with a database, with a full feature, with proper security, deployed at your URL. You shipped a real product. In 6 days."

> "Most courses haven't gotten you here in 6 weeks. You did it in 6 days."

> "Tomorrow is Week 2. We add AI. Today — take 10 minutes. Look at your URL. Send it to one person. You earned this."

> "I'm Sid. Day 7 we go AI. Welcome to the magic."

**Wait 2 sec. Stop.**

---

## What To Save / Use Later

- The "we didn't write a single line" moment → cross-post on LinkedIn / X
- The 60-sec API route walkthrough → re-use in a "Anatomy of an API route" mini-post
- The incognito RLS test moment → THE security clip
- A 90-sec demo of CRUD working → LinkedIn launch reel

---

## Common Pitfalls

- ❌ Don't rush the API route walkthrough — that's the most educational moment
- ❌ Don't skip the incognito test — it's the security gate
- ❌ Don't say "and Claude just generates magic" — explain WHAT Claude generated
- ❌ Don't celebrate prematurely — wait until the LIVE deploy test passes
- ❌ Don't apologize if Claude makes a mistake — diagnose + fix on camera, that's content
