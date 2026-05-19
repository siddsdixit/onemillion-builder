# Loom Outlines — Week 2 (Days 7-12) + Week 3 (Days 13-18)
**Priority:** P2 — Record after P0 (Days 4-6) and P1 (Getting Started, Days 1-3) are done.
**Format:** These are scene-level outlines, not full scripts. Expand to full script when recording.

---

## Day 7 — What Is An AI Feature (10-12 min)

**Core message:** The 3 patterns. Pick wrong → build the wrong thing for a week.

**Scenes:**
1. Cold open: "Before you touch AI code, you need to answer one question: what *kind* of AI feature is this?"
2. Pattern A (Text Generation): Show Sarah clicking "Draft Update" → email appears. AI writes, human uses.
3. Pattern B (Decision-Maker): Show inbox with 30 emails. AI says "These 5 need replies." Human acts.
4. Pattern C (Agent): Show calendar invites auto-accepted while you sleep. AI acts, human reviews.
5. The spec: Walk through `ai-feature.md` sections. Show the "What It Does" section — name the user, name the input, name the output.
6. Quality Criteria demo: Show the difference between "output sounds good" (unmeasurable) vs "output is 80-200 words AND mentions client name" (verifiable).
7. Verification: Paste Day 7 instructions. Show pass result.

**Critical moment:** The moment you decide between A and B. Show the thinking out loud.

---

## Day 8 — First AI Call + Prompt Design (12-15 min)

**Core message:** Prompt design is the whole game. Bad prompt = bad output, no matter how good the code.

**Scenes:**
1. Cold open: Show the same code with two different prompts. One produces garbage, one produces usable output.
2. The 5-part prompt structure: Role → Goal → Tone → Constraints → Format. Write each one for Sarah's use case.
3. The API route: Show creating `/api/generate-update/route.ts`. Walk through the Vercel AI SDK call.
4. Testing in the browser: Show the first real AI output. Good and bad responses both — don't cut the bad one.
5. Iteration: Change one constraint. Show how the output changes.
6. Verification: Show the Day 8 check — API route exists, returns text.

**Critical moment:** First real AI call working. Keep the reaction in.

---

## Day 9 — Streaming UI (8-10 min)

**Core message:** Streaming isn't optional — non-streaming AI feels broken to users.

**Scenes:**
1. Cold open: Show non-streaming (user stares at blank screen for 4 seconds). Show streaming (text appears word by word). "Which would you trust?"
2. How streaming works: SSE explained in 60 seconds. You don't need to understand the protocol — just the API.
3. `streamText` server side: Show the route change. 3 lines different from Day 8.
4. `useCompletion` client side: Show the hook. Skeleton loading state while streaming starts.
5. Demo: Full streaming flow in the browser. Real-time text appearing.
6. Error state: What happens when streaming fails. Show the error UI.

---

## Day 10 — Tool Use (AI Takes Actions) (12-15 min)

**Core message:** Tool use is how AI stops being a text generator and starts being useful.

**Scenes:**
1. Cold open: "Yesterday the AI generated text. Today it can read your database."
2. What tool use is: AI calls a function → function queries DB → AI uses the result. Not magic — just function calling.
3. Define the tool: Show `getClientHistory` tool definition. Name, description, parameters.
4. The route update: Show adding `tools` to the `streamText` call.
5. Demo: AI now references real client history in the draft email. "Following up on the homepage redesign I mentioned on March 15th..."
6. The safety boundary: AI can READ. It cannot WRITE without you explicitly building that. Keep that separation.

**Critical moment:** When the AI first uses the tool and references real data — show the "oh wow" moment.

---

## Day 11 — RAG: AI Reads User Data (12-15 min)

**Core message:** RAG makes AI personal. Without it, AI gives generic answers. With it, AI knows your user.

**Scenes:**
1. Cold open: Two emails — one generic, one that knows Sarah's history with the client. Same prompt, different context.
2. What RAG is: Retrieve → Augment → Generate. Not a vector database lecture — just: "pull relevant data, shove it in the prompt."
3. Building the retrieval: Show querying Supabase for client history before the AI call.
4. The context window: How much data to include. Show the token math — 1000 tokens = ~750 words.
5. Prompt augmentation: Show adding retrieved data to the system prompt.
6. Demo: Email draft that knows the last 3 interactions with the client.

---

## Day 12 — Lock the AI Feature (8-10 min)

**Core message:** You can always make AI better. Ship what works now; improve in v2.

**Scenes:**
1. Cold open: "By now your AI feature probably works 80% of the time. Today we define what 80% means and lock it."
2. Acceptance criteria: Walk through `ai-acceptance-criteria.md`. Each test case: input → expected output → pass/fail.
3. Cost audit: Show how to read Anthropic usage. Calculate: calls/day × cost/call = monthly burn.
4. The 20% problem: What to do when AI gives wrong output. Show the fallback copy + error handling.
5. Locking: "Anything that's not in the acceptance criteria is out of scope for v1. Write it down. Don't build it."
6. Final verification.

---

## Day 13 — Production Hygiene (10-12 min)

**Core message:** One leaked API key = your Anthropic bill goes from $5/month to $500 in a weekend.

**Scenes:**
1. Cold open: Screenshot of a real Anthropic bill spike (anonymized). "This happened because one key ended up on GitHub."
2. Secrets audit: Run `git log --all -p | grep ANTHROPIC`. Show what you're looking for.
3. RLS final check: The incognito test. One more time. Non-negotiable.
4. Rate limiting: Show the middleware addition. 10 AI calls per user per hour — explain the reasoning.
5. Error handling: What users see when AI fails. Not a blank screen — a clear message.
6. The audit checklist: Walk through it item by item.

**Critical moment:** When you find a secret that slipped through. Keep that in — it's a teaching moment.

---

## Day 14 — Custom Domain + SSL (6-8 min)

**Core message:** The step from `yourapp.vercel.app` to `yourapp.com` takes 15 minutes and changes everything about how it feels.

**Scenes:**
1. Cold open: Show both URLs side by side. "Which one would you pay for?"
2. Buying a domain: Namecheap/Cloudflare. Pick one. Show the purchase.
3. DNS setup in Vercel: Screenshot-by-screenshot. Add domain → copy DNS records → paste in registrar.
4. SSL: Vercel handles it. Show the green lock.
5. Propagation wait: "It takes 10-30 minutes. Come back. Don't refresh 40 times."
6. Verification: curl check → 200 + valid cert.

---

## Day 15 — Monitoring (8-10 min)

**Core message:** You can't fix what you can't see.

**Scenes:**
1. Cold open: "On Day 18 you share your product with the world. The next morning you want to know: did anyone use it? Did it break?"
2. Sentry setup: 5 minutes. Show the integration. Show your first error showing up.
3. Vercel Analytics: Already installed. Show the dashboard. What to look for.
4. UptimeRobot: Free tier. Show setting up a monitor. Show the "your site is down" email format.
5. The dashboard view: All three open. "This is your cockpit."

---

## Day 16 — Landing Page (12-15 min)

**Core message:** The landing page is a sales argument. Five sections = five steps of the argument.

**Scenes:**
1. Cold open: Show a bad landing page vs a good one. What makes the difference?
2. The 5 sections: Hero → Problem → Solution → Proof → CTA. Build each live.
3. Hero: One sentence. What the product does + who it's for. Not "powered by AI." "Sarah writes client emails in 30 seconds instead of 30 minutes."
4. Problem: Make the user feel the pain before you offer the solution.
5. Solution: Screenshots. Not features — outcomes.
6. Proof: One testimonial (your own Day 2 conversation can count). One number if you have it.
7. CTA: "Try it free." Not "Sign up." Not "Learn more." "Try it free."
8. Demo: The landing page live.

---

## Day 17 — First 10 Users (10-12 min)

**Core message:** The first 10 users won't find you. You find them.

**Scenes:**
1. Cold open: "Your product is live. Zero users. This is normal. Here's what you do today."
2. The message: Show the exact DM format. No pitch. Just: "I built something for [their pain]. Could I show you for 5 minutes?"
3. Who to message: The people from your Day 2 conversations. Your network. 1-2 LinkedIn posts.
4. The feedback session: Screen share. Watch them use it. Don't explain — just watch. Take notes.
5. Writing it up: `feedback.md`. What they loved. What confused them. One thing to fix.
6. The mindset: "Day 17 is not about 10 users. It's about 1 real signal."

---

## Day 18 — Demo Day (8-10 min)

**Core message:** The 5-minute Loom is your proof of work. It stays up forever.

**Scenes:**
1. Cold open: "Today you record a 5-minute Loom and share it. That's your Builder #N."
2. The 5-minute structure: 30s intro → 90s problem → 2min demo → 30s what's next → 30s call to action.
3. Live demo: Walk through your product, narrating for a first-time viewer. Stay under 5 minutes.
4. The Builder #N submission: Run `/verify all`. Show the output. Submit the PR.
5. The share: LinkedIn post format. "#BuildingWith1M Builder #N: [one sentence about what you built]."
6. Close: "You built a real AI product. Deployed. Real users. That's it. That's what OneMillion is."

**Final moment:** "What did you build? Tell me. I read every reply."

---

## Recording Priority Order

| Priority | Day | Why |
|----------|-----|-----|
| P0 | Days 4, 5, 6 | Highest abandonment without video |
| P1 | Getting Started, Days 1, 2, 3 | Foundation — every builder watches these |
| P2 | Day 7, 8, 13, 16, 18 | AI week kickoff, production, launch, demo day |
| P3 | Days 9, 10, 11, 12, 14, 15, 17 | Remaining — record between cohort 0 and cohort 1 |

**Total Looms to record:** 19 (getting-started + 18 days)
**Estimated record + edit time:** ~20 hours
**Suggested pace:** 3-4 per weekend = done in 5-6 weekends
