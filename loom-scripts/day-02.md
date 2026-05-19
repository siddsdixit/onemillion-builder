# Loom Script — Day 2: Problem + Mom Test
**Priority:** P1
**Target length:** 10-12 minutes
**When to record:** Before Cohort 0 starts.

---

## What This Video Does

Day 2 is about validating the problem before writing a single line of code. This video makes the Mom Test feel doable — not like a sales call, not like research, just like a conversation.

The audience risk here: non-technical builders (EAs, PMs) feel awkward doing "user research." This video normalizes it.

---

## Cold Open (0:00–0:45)
*Start with a screenshot of a real chat conversation — something like an iMessage to a colleague asking about their workflow.*

> "This is an actual conversation I had this week. I'm not selling anything. I'm not even pitching an app. I'm just asking someone about their job."

> "That's the Mom Test. And it's the single most important thing you'll do in Week 1."

---

## Section 1 — Why Most Builders Skip This (0:45–2:30)

> "Here's what most builders do: they have an idea, they think it's good, they build it. Six weeks later they demo it to 5 people and get... polite applause."

> "The problem isn't the code. The problem is they were solving a pain that wasn't painful enough to pay for. Or wasn't painful to enough people."

> "The Mom Test is how you check this before you write a line of code."

Draw or show:
```
BAD question: "Would you use an app that does X?"
GOOD question: "Tell me about the last time you had to do X. What was that like?"
```

> "Bad questions invite politeness. Good questions surface reality."

---

## Section 2 — The Three Conversation Types (2:30–5:00)

> "You need three conversations. They don't all have to be strangers."

**Conversation 1: Someone who has the problem**
> "Sarah's building a client update drafter. Who does she talk to? Another freelancer. Could be a Slack group, a Discord, a friend. Just someone who sends client emails."

**Conversation 2: Someone adjacent to the problem**
> "Her project manager friend. Someone who receives client emails. What do they actually want from those updates?"

**Conversation 3: Yourself**
> "Yes, yourself counts. If this is your own pain, document it honestly. When did this bother you last? What did you do instead? What would you have paid to fix it?"

> "You don't need a formal research setup. You need three honest conversations."

---

## Section 3 — The Actual Questions to Ask (5:00–7:30)

*Show the 5 questions from Day 2 build.md on screen.*

> "These are the five questions I use every time:"

1. "Tell me about the last time you had to do [the thing]."
2. "How did you handle it?"
3. "What was the worst part?"
4. "Have you tried anything else?"
5. "What would 'fixed' look like to you?"

> "Notice: none of these mention your app. You're a journalist, not a salesperson."

> "Watch for this signal: when someone gives you a specific story with specific frustration, you've found a real pain. When someone says 'yeah, that's a thing' and moves on — not real enough."

*Show a fake but realistic transcript of a "bad" response vs a "good" one.*

Bad: "Yeah, client emails are kind of annoying sometimes. I guess an app would help."

Good: "Oh man, last Tuesday I had four emails to write and I spent three hours on them. I kept second-guessing myself on the tone for one client who's been difficult. I almost just didn't send it."

> "See the difference? Specificity = real pain."

---

## Section 4 — Creating notes.md (7:30–9:30)

> "The deliverable today is a file: `.onemillion/notes.md`. Three conversation summaries."

*Open Claude Code. Show the prompt from build.md.*

> "Paste the Day 2 prompt. Tell Claude what you heard. It helps you write up the summary and extract the signal."

*Show the output being written to notes.md.*

> "Paste your raw notes. Claude formats them. Takes 5 minutes."

*Show final notes.md with 3 entries, each with: who, what they said, key insight.*

---

## Section 5 — The Pivot Moment (9:30–10:30)

> "Sometimes Day 2 tells you to pivot. Good. Better now than after two weeks of building."

> "If all three conversations show weak signal — the problem isn't painful enough, people have workarounds they're happy with — you can change your product idea now. Day 3 is when we lock in. Not Day 2."

> "If you're unsure: look for the conversation that had the most emotion. Build for that."

---

## Close (10:30–11:30)

> "Day 2 is done when you have three conversation records in notes.md and at least one strong signal."

> "Day 3 tomorrow: the PRD. We write down exactly what we're building. 5 sections, 45-90 minutes. After that, the spec is locked."

---

## Post-Production Notes
- Thumbnail: two speech bubbles — one with "would you use this?" (crossed out) and one with "tell me about last time..." Text overlay: "Talk to 3 people first."
- Description: link to day-02 learn.md, Mom Test book reference (Rob Fitzpatrick)
- Chapters: 0:00 Cold open | 0:45 Why builders skip this | 2:30 Three conversations | 5:00 Five questions | 7:30 Creating notes.md | 9:30 The pivot moment
- **Leave in:** a moment where you get a weak response and have to probe deeper. Show the follow-up question working.
