# Loom Script — Day 3: PRD — Lock Your Scope
**Priority:** P1
**Target length:** 12-15 minutes
**When to record:** Before Cohort 0 starts.

---

## What This Video Does

The PRD is the most important document in the whole course. Everything in Weeks 2 and 3 flows from it. Builders who write a vague PRD spend Week 2 confused. This Loom shows the difference between a vague PRD and a good one — with Sarah's example as the reference.

---

## Cold Open (0:00–0:45)
*Start with two side-by-side PRD excerpts — blurred, but clearly different lengths and specificity.*

> "Both of these are from Day 3 submissions. One of them will ship a product in 15 days. One of them will still be rewriting features in Day 12."

> "The difference isn't intelligence. It's specificity. Let me show you what that means."

---

## Section 1 — What a PRD Is (and Isn't) (0:45–2:30)

> "PRD stands for Product Requirements Document. Enterprise companies write 50-page ones. We write a one-pager with five sections."

> "It's not a wish list. It's a contract with yourself: this is what I'm building. This is what I'm NOT building. If I think of something cool during Week 2, it goes in the Out Of Scope list — not into the build."

> "The PRD is why OneMillion builders ship. They know exactly what done looks like."

---

## Section 2 — The Five Sections (2:30–6:30)

*Open Sarah's PRD from the course examples. Walk through each section.*

**Section 1: Problem**
> "One paragraph. The specific pain. Real user. Real context. No solutions yet."

Show:
> "Sarah, a freelance UX designer managing 15+ clients, spends 30-45 minutes each week writing status update emails. She dreads it, often delays it, and the emails feel inconsistent — more confident with some clients, apologetic with others. The result: some clients feel informed and happy; others feel in the dark and churn."

> "See what's in there: a specific person, a specific time cost, a specific emotional cost, a specific consequence. That's a Problem section."

**Section 2: User**
> "Who is this for? One sentence. Not 'users who need this.' A real person."

> "Sarah: 28-35, freelance UX/product designer, 10-20 active clients, works from home, uses Gmail and Notion, squeezed for time."

**Section 3: Three Features (core only)**
> "Not a roadmap. Just the three things that make the product useful. If it's a client email drafter:"

1. Deliverable tracker (what's in progress, what's done, what's overdue)
2. Draft generator (one click → draft email for any deliverable)
3. History view (past emails sent per client — so you don't repeat yourself)

> "Three features. Not four. Not five. Three."

> "The hardest part of the PRD is deleting feature #4. Do it anyway."

**Section 4: Out Of Scope**
> "This section is as important as the features. Write down everything you thought of but decided not to build."

Show a list:
- Auto-send emails (manual review always required)
- Mobile app (web only in v1)
- Team collaboration (one user only)
- CRM integration (v2)
- Email templates library (v2)

> "When you're tempted to add something in Week 2 — and you will be — you check this list. If it's here, you don't build it. If it's not here, add it and don't build it."

**Section 5: Definition of Done**
> "When is this product 'done' enough to launch? Be specific."

> "Sarah's Definition of Done: A logged-in user can add a deliverable, generate a draft email for it, edit the draft, and the email appears in their history. That's it. The first user who signs up and does this — we're done."

---

## Section 3 — Common Mistakes (6:30–9:00)

*Show three "before/after" examples side by side.*

**Mistake 1: Vague problem**
- Before: "People struggle with email"
- After: "Sarah spends 30-45 min/week writing client status emails. She dreads it."

**Mistake 2: Feature list instead of 3 features**
- Before: 8-bullet feature list
- After: Exactly 3. The rest in Out Of Scope.

**Mistake 3: No Out Of Scope**
- Before: "Out Of Scope: (nothing listed)"
- After: 6 items. The temptations you're saying no to.

> "If your Out Of Scope section is empty, your PRD isn't done. Forcing yourself to list what you're NOT building is how you keep Week 2 focused."

---

## Section 4 — Writing It With Claude (9:00–11:30)

*Open Claude Code. Show the Day 3 prompt from build.md.*

> "Copy the prompt from build.md. Paste your notes from Day 2. Claude will draft the PRD section by section."

> "Here's the key: push back on vagueness. If Claude writes 'users who struggle with email' — tell it to use Sarah's name and her specific situation."

*Show a back-and-forth. Claude drafts → you push back → Claude tightens.*

> "This takes 15-20 minutes of iteration. Normal. It's the most important 15 minutes in Week 1."

*Show the final file being saved to `.onemillion/prd.md`.*

---

## Section 5 — The Verification (11:30–13:00)

> "Paste the Day 3 AI instructions into Claude. It reads your PRD and checks each section."

*Show the verification running. Show the checklist output.*

> "Common feedback: 'Out Of Scope has fewer than 4 items.' Add them. 'Problem section is not specific to one user.' Add Sarah's name."

> "Once you pass — the PRD is locked. No changes without a deliberate reason. The course depends on this."

---

## Close (13:00–14:00)

> "You now have a locked scope. Most people who fail at side projects fail because they keep expanding scope. You've made that literally impossible for the next two weeks."

> "Day 4 tomorrow: first line of code. You deploy a working app. Not a complex one — but real, live, on the internet. 1-2 hours."

> "If you're non-technical: that's the honest estimate. Give yourself the full 2 hours. It's worth it."

---

## Post-Production Notes
- Thumbnail: `.onemillion/prd.md` open with "3 features. Not 4." circled. Text overlay: "Lock your scope."
- Description: link to day-03 learn.md, link to Sarah example PRD
- Chapters: 0:00 Cold open | 0:45 What a PRD is | 2:30 Five sections | 6:30 Common mistakes | 9:00 Writing with Claude | 11:30 Verification
- **Leave in:** the moment where you have to push Claude to be more specific. Show that iteration is normal.
- **Critical moment:** When you're listing Out Of Scope items and you say "this one hurts to cut." Keep that in — it's relatable.
