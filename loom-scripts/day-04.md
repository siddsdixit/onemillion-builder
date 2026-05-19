# Day 4 — Stack + First Deploy

**Target length:** 12-15 minutes
**Energy:** Excited, paternal, "I want you to see this work"
**Priority:** P0 — record this first

---

## Why This Loom Matters Most

Simulation showed Maria (EA), Sarah (Executive), Priya (PM) all drop at Day 4. The text instructions aren't enough — they need to SEE someone hit a real error and fix it. This Loom is the difference between a course that works for engineers and one that works for everyone.

---

## Pre-Recording (15 min setup)

- [ ] Fresh project folder ready: `~/sid-loom-build/` (delete any old version)
- [ ] Terminal open in that folder, ready to type
- [ ] VS Code installed, ready to open
- [ ] GitHub account already authenticated via `gh auth login` (don't show this — assume the viewer already did Getting Started)
- [ ] Vercel account ready to deploy (logged in already)
- [ ] Claude Code authenticated (`claude --version` works)
- [ ] An idea ready ("DeliverableDash — freelance deliverable tracker")
- [ ] **Mac OR Windows pick one** — recommend Mac for first take (faster). You can re-record Windows-specific moments later if needed
- [ ] No browser tabs open except [vercel.com/new](https://vercel.com/new)
- [ ] Loom set to screen + face camera

---

## Cold Open (0:00 - 0:30)

Show your already-deployed `sid-onemillion-build.vercel.app` URL. Live. In a browser.

**Say:**
> "By the end of this video, you'll have a URL just like this one — your name on the internet, deployed in 30 seconds, free. This is Day 4. The biggest day of Week 1. Let's go."

**Switch to VS Code with terminal open.**

---

## Section 1 — npx create-next-app (0:30 - 3:30)

In terminal:
```bash
npx create-next-app@latest .
```

Answer each question OUT LOUD:

- "Use TypeScript? Yes — types make Claude generate better code."
- "Use ESLint? Yes — catches errors early."
- "Use Tailwind CSS? Yes — pre-styled, less work."
- "src/ directory? No — keeps it simple."
- "App Router? Yes — this is the modern Next.js way."
- "Turbopack? No — for compatibility."
- "Customize import alias? No — defaults are fine."

**While npm installs (~60 seconds), don't go silent. Say:**
> "While this installs — you're going to see a lot of text scroll. That's normal. Yellow text = warnings, ignore. Red text starting with 'ERR' = real errors. We don't have any right now."

When it finishes: scroll to top, point at warnings, say "see, ignore."

---

## Section 2 — npm run dev + customize (3:30 - 6:30)

```bash
npm run dev
```

**Say:**
> "This is your laptop running a real web server. Open localhost:3000."

Open browser to `localhost:3000`. See the default Next.js page.

**Say:**
> "That's the default. Boring. Let's make it ours."

Open Claude Code in a SECOND terminal:
```bash
cd ~/sid-loom-build
claude
```

Paste into Claude:
```
Edit app/page.tsx so it says: "Hi, I'm Sid. I'm building DeliverableDash 
for freelance UX designers. Day 4 of OneMillion."
Use Tailwind to center it nicely.
```

Watch Claude edit. Switch back to browser, hit refresh — text changes.

**Say:**
> "That's what hot reload does. Save the file, browser updates. You'll do this 100 times in the next 14 days."

---

## Section 3 — Git + GitHub + Vercel Deploy (6:30 - 11:00)

```bash
git init
git add .
git commit -m "Day 4: First commit"
```

**Say (briefly):**
> "Git is your time machine. Every commit is a save point."

Open [github.com/new](https://github.com/new) in browser. Create repo:
- Name: `sid-loom-build`
- Public
- DO NOT add README

Show the page where GitHub gives commands. Copy the second block. Paste in terminal:
```bash
git remote add origin https://github.com/siddsdixit/sid-loom-build.git
git branch -M main
git push -u origin main
```

**This is where you might hit an auth issue. LEAVE IT IN.** If `gh auth login` works seamlessly, great. If GitHub asks for password, say:

> "Classic — GitHub doesn't take passwords anymore. You need a Personal Access Token. The fastest way: `gh auth login`. Let me show you."

Run `gh auth login`. Show the flow.

Now Vercel. Open [vercel.com/new](https://vercel.com/new).

- Find your fresh repo → Import
- Don't change settings → Deploy
- Wait 60-90 seconds

**While waiting, say:**
> "Vercel reads your GitHub, runs `npm run build`, deploys to a CDN. You did nothing. That's the magic."

When done, click the URL. **Show your text live on the internet.**

---

## Section 4 — The Deploy Loop (11:00 - 13:30)

Back to VS Code. Edit `app/page.tsx`:
- Change "Day 4 of OneMillion." → "Day 4 of OneMillion — and somehow this works."

Save.

In terminal:
```bash
git add .
git commit -m "Update homepage"
git push
```

Switch to Vercel dashboard tab. **Show the new deployment starting.**

**While Vercel builds (30-60 sec), say:**
> "Right now, the code on your laptop is becoming the code on the internet. Automatically. No FTP, no SSH, no server admin. Just git push."

Refresh the deployed URL. New text appears.

**Say:**
> "That's the deploy loop. You'll do this 50 times in the next 14 days. Code → commit → push → live in 30 seconds. Get used to this feeling."

---

## ONE Real Moment To Leave In

If anything errors during this 12-min recording — npm install hiccup, GitHub auth issue, Vercel build error — **DO NOT CUT IT OUT.** Show yourself reading the error, narrating what it means, fixing it.

Builders need to see that **errors are normal and recoverable.** Polished perfection makes them feel inadequate when they hit their own first error.

Best moment to capture: GitHub auth (often fails first time, easy fix).

---

## Closing (13:30 - 15:00)

Back to your deployed URL.

**Say:**
> "Here's what you just did: you have a real domain, hosting an app, running on the internet, that you can send to anyone. You did it in under 15 minutes."

> "Day 5 we add auth. That's tomorrow. Today you celebrate this — send this URL to one person. A friend, a colleague, whoever. Don't explain it, just send the link. That's your public commitment."

> "I'm Sid. I'll see you tomorrow."

**Wait 2 seconds. Stop recording.**

---

## What To Save / Use Later

- This Loom URL → paste into `week-1-foundation/day-04-stack/loom.md`
- A 60-sec clip of the "Vercel deploys" moment → reuse on LinkedIn/X
- A screenshot of your live URL → use in MANIFESTO + landing page social

---

## Common Pitfalls (Don't Do These)

- ❌ Don't apologize for typos ("oh sorry, I meant...") — just continue
- ❌ Don't read the script word-for-word — talk like you're showing a friend
- ❌ Don't go faster than 1.0x speed — non-engineers need time to absorb commands
- ❌ Don't skip the "wait while npm installs" moment — fill it with explanation
- ❌ Don't edit out the deploy wait — that 60-sec moment IS the magic
- ❌ Don't speed up the video in post — natural pacing is more trustworthy
