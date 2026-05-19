# Day 5 — Auth + Database + RLS

**Target length:** 12-15 minutes
**Energy:** Confident, slightly serious (security topic), but reassuring
**Priority:** P0 — record after Day 4

---

## Why This Loom Matters

3 of 6 personas flag Day 5 as a config-overload nightmare: `.env.local` + Vercel env vars + Supabase keys + RLS policies + auth pages. Without seeing it done live, builders cargo-cult code without understanding. They ship broken RLS. Real security holes.

This Loom prevents that.

---

## Pre-Recording (10 min setup)

- [ ] Day 4 project from previous Loom is ready (`~/sid-loom-build/`)
- [ ] Local dev server running (`npm run dev` in terminal 1)
- [ ] Supabase account ready, signed in
- [ ] **A FRESH Supabase project** — don't reuse an existing one, viewers need to see project creation
- [ ] Vercel dashboard tab open, your project visible (for env var step)
- [ ] Claude Code ready in terminal 2
- [ ] Have 2 test email addresses ready (e.g., `sid+test1@gmail.com`, `sid+test2@gmail.com`)
- [ ] Incognito browser window ready (for the cross-user test at end)
- [ ] Phone or second device handy

---

## Cold Open (0:00 - 0:30)

Switch to your already-finished demo app where you have signup/login working.

**Say:**
> "I'm going to sign up as a user. Now I'm in. Add some data. Now I sign out. Now I sign IN as a DIFFERENT user — and watch — I see none of the first user's data. That's what we're building today. Auth + database + the security rule that makes it real."

> "This is Day 5. Most courses save security for week 4. We do it on day 5. Let's go."

Switch to VS Code + terminal.

---

## Section 1 — Create Supabase Project (0:30 - 3:30)

Open [supabase.com](https://supabase.com). Sign in.

**Click through live:**
- New project
- Name: `sid-loom-build`
- Database password: type a real one, say "writing this down in 1Password"
- Region: pick yours
- Create

**While project provisions (~2 min):**
> "Supabase is giving you a real PostgreSQL database, an auth system, and an API — all free. While it provisions: this is what most products spend their first month building. We get it in 2 minutes."

When ready: Settings → API. Show the Project URL + anon key.

> "Two things you need: the Project URL and the anon key. Anon key is safe to expose to the browser — that's what it's designed for. Service role key, also on this page — NEVER put that in your app. Treat it like your AWS root password."

---

## Section 2 — Env Vars (3:30 - 5:30)

Switch to VS Code. Create `.env.local`:

```
NEXT_PUBLIC_SUPABASE_URL=https://abc123.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=eyJ...
```

Paste real values. Save.

**Say:**
> "These keys are in YOUR `.env.local`. Now — and this is where 80% of builders break — you ALSO have to add them to Vercel. Watch."

Switch to Vercel dashboard → your project → Settings → Environment Variables.

Add both. Save.

> "If you skip this, your app works on your laptop and breaks in production. The Vercel deploy will succeed, the page will load, signup will silently fail. This is the #1 Day 5 mistake. Don't make it."

---

## Section 3 — Install Supabase + Let Claude Build Auth (5:30 - 9:30)

In terminal 2:
```bash
npm install @supabase/supabase-js @supabase/ssr
```

Open Claude Code, paste:
```
I'm on Day 5 of OneMillion. Build me Supabase auth in my Next.js App Router.

Need:
1. lib/supabase/client.ts (browser client)
2. lib/supabase/server.ts (server client)
3. middleware.ts at project root (session refresh)
4. /signup page with email+password form
5. /login page with email+password form  
6. /auth/callback route handler
7. /dashboard page that requires auth + shows logged-in user's email
8. A Sign Out button

Use @supabase/ssr (NOT @supabase/auth-helpers). Use Tailwind for styling.
Aim for ~150 lines total. Show me plan before generating.
```

**While Claude responds, narrate what it's about to do.** Don't be silent.

When Claude generates: scroll through ONE file (e.g., `middleware.ts`) and explain in 30 sec what it does:

> "This middleware runs on every request. It checks if the user has a valid session token. If yes — refresh it so they stay logged in. If no — they're treated as anonymous. This is what keeps you logged in across page loads."

Don't explain every file. Just hit one to show the pattern.

---

## Section 4 — Disable Email Confirmation + First Table + RLS (9:30 - 12:00)

Switch to Supabase dashboard.

**Authentication → Providers → Email → toggle "Confirm email" OFF.**

> "For dev, turn this off so you can test fast. Re-enable for production."

**Table Editor → New Table:**
- Name: `deliverables`
- Enable RLS: ✅ KEEP CHECKED
- Add columns: `name` (text), `status` (text, default 'todo'), `user_id` (uuid, foreign key → auth.users.id)
- Save

Now the critical moment. **Click your new table → Policies → New Policy → For full customization.**

- Name: `Users see their own deliverables`
- Allowed operation: ALL
- USING: `auth.uid() = user_id`
- WITH CHECK: `auth.uid() = user_id`
- Save

**Stop. Look at camera. Say:**
> "This rule. THIS rule right here. Without it: anyone with your anon key can read your entire database. WITH it: a user can only see rows that belong to them. PostgreSQL enforces this in the database engine. You can't bypass it. Even if your code is wrong, the database is right."

> "Enable RLS on every table. Add a policy. Every time. No exceptions."

---

## Section 5 — Test Locally (12:00 - 14:00)

Switch to browser → `http://localhost:3000/signup`.

Sign up as `sid+test1@gmail.com`. Land on dashboard. Show your email displayed.

Sign out.

Sign in. Land on dashboard.

**Quick incognito test (THE Critical moment):**

Open incognito browser. Go to `http://localhost:3000/signup`. Sign up as `sid+test2@gmail.com`. Land on dashboard.

In incognito, try to navigate to anything that User 1 had. Confirm nothing leaks.

**Say (looking at camera):**
> "This is the test that matters. If User 2 saw any of User 1's data, RLS is broken. Always test this before you ship. ALWAYS."

---

## ONE Real Moment To Leave In

The most common Day 5 bug: forgot to add env vars to Vercel. If you forget during recording, push code, deploy fails — leave it in. Diagnose live:

> "OK so my Vercel just failed. Why? Right — I added env vars to .env.local but not to Vercel. Let me fix it real quick."

This single moment saves 200 builders the same mistake.

---

## Closing (14:00 - 15:00)

**Say:**
> "Today you got: a database, auth, and the most important security rule in your app. You're 50% of the way to a real product."

> "Day 6 we build your first CRUD feature — the main thing your product DOES. That's tomorrow."

> "If your incognito test passed, you're good. If not, fix RLS before tomorrow. See you."

**Wait 2 sec. Stop.**

---

## What To Save / Use Later

- 60-sec clip of "this rule. RLS. enforced in the database engine." → cross-post on LinkedIn as security education
- Screenshot of Supabase Policy creation UI → use in social posts
- The incognito test moment → post separately as "the test most builders skip"

---

## Common Pitfalls

- ❌ Don't paste the actual anon key in the recording without thinking — it's "safe" for browser use but viewers may see it. Use a redacted one or rotate after recording.
- ❌ Don't speed past the RLS explanation — this is THE moment of Day 5
- ❌ Don't skip the incognito test — that's the security gate
- ❌ Don't claim "this is unhackable" — RLS is necessary but not sufficient. Say "this is the foundation"
