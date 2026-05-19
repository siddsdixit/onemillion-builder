# Loom Script — Day 1: Vision + Mental Map
**Priority:** P1
**Target length:** 10-12 minutes
**When to record:** Before Cohort 0 starts.

---

## What This Video Does

Day 1 is all non-code. The risk: builders feel like they're not making progress. This Loom makes the mental map tangible. By the end they've picked a product idea and understand what they're building for the next 17 days.

---

## Cold Open (0:00–0:45)
*Start with a blank `.onemillion/` folder already open in VS Code or Finder.*

> "Day 1. No code. I know — it's tempting to skip ahead. Don't. The builders who skip this are the ones who build the wrong thing for two weeks and start over."

> "Today is 30-45 minutes. You pick your product. You understand the mental map. You commit to the next 17 days."

---

## Section 1 — The Mental Map (0:45–3:30)

*Open a whiteboard or draw in Keynote — the three-layer diagram.*

> "Here's how to think about every product you'll ever build with AI. Three layers."

Draw:
```
[ USER ]
   ↓ types something
[ YOUR APP ]  ← you build this
   ↓ calls the AI
[ CLAUDE ]
   ↓ returns text/data
[ YOUR APP ]  ← displays it
   ↓
[ USER ]  ← sees the result
```

> "Your job isn't to build AI. Claude is the AI. Your job is to build the app that sits in the middle. The app that takes user input, calls Claude with the right context, and shows the result in a useful way."

> "That's it. That's what we're building for 18 days."

---

## Section 2 — Three Product Types (3:30–6:30)

> "When I talk to builders, I hear the same three ideas over and over. And they map to three types of products."

*Show a simple table or diagram:*

| Type | What it does | Example |
|------|-------------|---------|
| Tool | Saves time on a repeating task | Email drafter, meeting summarizer |
| Tracker | Helps you see patterns in your own data | Habit tracker, goal journal |
| Feed | Surfaces relevant info from a stream | Reading list, lead monitor |

> "Which one is yours? Pause here and write it down. Seriously — pause the video."

*[PAUSE BEAT — 3 seconds of silence]*

> "Here's the exercise. Think about one task you do repeatedly at work or in life that feels like it shouldn't be that hard. What is it?"

> "I'm going to use Sarah as my example throughout this course. Sarah's a freelance UX designer. She spends 30 minutes every week writing status update emails to clients. She hates it. She always forgets what she mentioned last time. The emails feel formulaic but she still rewrites them from scratch."

> "That's the pain. Tool: a client update drafter. Done."

---

## Section 3 — What Gets Built on Day 1 (6:30–8:00)

*Open terminal. Navigate to project folder.*

> "Today's deliverable is not code. It's a file: `.onemillion/project.json`."

> "Let me show you how to create it. Open Claude Code in your project folder:"

```
mkdir my-product && cd my-product
claude
```

> "Then paste the Day 1 prompt from `build.md`. Claude will ask you questions and create the file."

*Show the file being created. Show the content.*

```json
{
  "product_name": "Client Update Drafter",
  "product_type": "tool",
  "core_pain": "Freelancers spend 30 min/week writing client status emails",
  "target_user": "Sarah, freelance UX designer, 30 clients"
}
```

> "Four fields. That's the whole deliverable."

---

## Section 4 — The Verification (8:00–9:30)

> "Every day ends with a verification. Paste the Day 1 AI instructions into Claude. It reads your file and checks it. Pass = you're done. Needs revision = it tells you exactly what to fix."

*Show the paste. Show the pass result.*

> "When you pass, you get a Day 1 badge in your `.onemillion/` folder. That's your record."

---

## Close (9:30–11:00)

> "Here's what just happened: you committed to an idea. Not forever — you can change it. But for the next 17 days, this is your product. Focused builds ship. Diffuse builds stall."

> "Day 2 tomorrow: the Mom Test. You'll talk to 2-3 real people about your idea. Not to sell it — to stress-test it. Probably the most important day in Week 1."

> "30-45 minutes. Do it today if you can."

---

## Post-Production Notes
- Thumbnail: `.onemillion/project.json` on screen with a checkmark. Text overlay: "Pick your product."
- Description: link to day-01 learn.md, mental map diagram
- Chapters: 0:00 Why this day matters | 0:45 Mental map | 3:30 Three product types | 6:30 Creating project.json | 8:00 Verification
- **Leave in:** the moment when Claude asks a follow-up question and you have to think for 5 seconds. That's real. Don't cut it.
