# Loom Script — Getting Started
**Priority:** P1
**Target length:** 8-10 minutes
**When to record:** Before Cohort 0 starts. This is the first thing every builder watches.

---

## What This Video Does

Removes the fear of the first day. A builder who has never opened a terminal should watch this and think "I can do this."

---

## Gear Check
- Screen + face cam (corner, small)
- Clean desktop (hide everything except the browser + terminal you'll open)
- Mic check before recording

---

## Cold Open (0:00–0:30)
*No intro music. Start mid-action — already in the terminal.*

> "Before you write a single line of code, you need three accounts and one tool installed. This takes about 15 minutes. I'm going to do it with you — from scratch, on a clean machine."

Show: a fresh terminal window. Nothing installed yet.

---

## Section 1 — The Three Accounts (0:30–2:30)

Open browser. Go to GitHub.com/signup.

> "First: GitHub. This is where your code lives. Pick a username you'd put on a resume — I went with `siddharthdixit`. Don't overthink it."

*Sign up. Show the confirmation email arriving.*

> "Two: Supabase. Click 'Continue with GitHub.' Done — it uses your GitHub account."

> "Three: Vercel. Same — 'Continue with GitHub.' These three are connected. One login to rule them all."

*Show all three tabs open, logged in.*

---

## Section 2 — Installing Claude Code (2:30–5:00)

> "Now the one tool you'll use for everything: Claude Code. It's an AI that lives in your terminal. Here's how to install it."

**Mac:**
```
brew install node
npm install -g @anthropic-ai/claude-code
```

*Show the install running. Show expected output — green checkmarks.*

> "If you see `claude --version` return a version number, you're set."

**Windows (show as alternative, don't dwell):**
> "Windows builders — open PowerShell as admin and run..."

```
winget install OpenJS.NodeJS
npm install -g @anthropic-ai/claude-code
```

> "Same result. Version number = you're ready."

**If it errors:**
> "The most common error is Node version too old. If you see that, run `node --version`. If it's below 18, update Node first. Link in the description."

---

## Section 3 — API Key (5:00–7:00)

> "Last piece: your Anthropic API key. Go to console.anthropic.com."

*Show the page. Navigate to API Keys.*

> "Click 'Create key.' Give it a name — I'm calling mine 'onemillion-dev'. Copy it."

> "Now set it as an environment variable. One command:"

```
export ANTHROPIC_API_KEY="your-key-here"
```

> "To make it permanent — so you don't have to run this every time you open a terminal:"

```
echo 'export ANTHROPIC_API_KEY="your-key-here"' >> ~/.zshenv
source ~/.zshenv
```

> "Now run `claude` in your terminal. If you see the Claude Code welcome screen — you're done."

*Show the welcome screen.*

---

## Section 4 — One Verification (7:00–8:30)

> "Let me show you the course folder structure so you know what you're working with."

Open the onemillion-builder GitHub repo. Show the README.

> "Each day has five files: learn, build, instructions, a video link, and extra resources. You work through them in that order. The instructions file is a prompt you paste into Claude — it verifies your work automatically."

> "You don't need to understand this now. Just know: every day has a checklist. Claude grades it. You pass and move on."

---

## Close (8:30–9:30)

> "You now have everything you need to build any product, anytime, forever. These tools — GitHub, Supabase, Vercel, Claude Code — are the same ones used to build real companies."

> "Day 1 is next. It's 30 minutes. No code. You pick your product idea."

> "Let's go."

---

## Post-Production Notes
- Thumbnail: terminal showing `claude --version` → green output. Text overlay: "Setup in 15 min."
- Description: link to getting-started.md, Node install docs, Anthropic console
- Chapters: 0:00 Accounts | 2:30 Claude Code | 5:00 API Key | 7:00 Course structure
