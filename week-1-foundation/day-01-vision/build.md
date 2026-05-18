# Day 1 — Build Guide

**No code today.** This is your "set up your project folder and write down your idea" day.

If you've already done [getting-started.md](../../getting-started.md), you have all the tools. We're just creating a folder and a file.

---

## Before You Start

- [ ] Terminal is open (Mac: Terminal app. Windows: Git Bash.)
- [ ] You've decided on a `product_type` (web_app / ai_agent / hybrid) — see [learn.md](./learn.md) Part 2
- [ ] You've drafted an idea (2 sentences) — see [learn.md](./learn.md) Today's Assignment

---

## Step 1: Create Your Project Folder

In your terminal, navigate to where you want the project to live. Usually your home folder:

```bash
cd ~
```

Then create the project folder:

```bash
mkdir my-onemillion-build
cd my-onemillion-build
```

**You should see:** Your terminal prompt now shows you're inside `my-onemillion-build`.

> 💡 You can name the folder anything you want — `yoga-followup` or `client-tracker` or whatever fits your idea. The course uses `my-onemillion-build` as a placeholder.

---

## Step 2: Create The Hidden Course Folder

The course uses a folder called `.onemillion/` (the dot makes it hidden) to track your progress and store course-specific files. Create it:

```bash
mkdir .onemillion
```

**You should see:** Nothing visible if you run `ls`, because `.onemillion/` is hidden. Run `ls -la` to see all files including hidden ones.

---

## Step 3: Create `project.json`

This file holds the answers to "what am I building?" The verifier reads it on every day to check your progress.

Open your editor (VS Code, Cursor, Antigravity, whatever you picked):

```bash
code .            # opens VS Code in this folder
# OR
cursor .          # opens Cursor
```

In your editor, create a new file: `.onemillion/project.json`

Paste this in, then **edit the values** to match YOUR product:

```json
{
  "product_type": "web_app",
  "idea": "Yoga studio owners spend hours each week manually following up with clients who didn't rebook. I want a tool that automates the follow-up while letting the owner approve each message before it goes.",
  "builder_name": "Your Name",
  "started_at": "2026-05-18"
}
```

**Replace:**
- `product_type` → `web_app`, `ai_agent`, or `hybrid`
- `idea` → your 2-sentence idea from learn.md
- `builder_name` → your actual name
- `started_at` → today's date

Save the file.

---

## Step 4: Run Day 1 Verification

You're going to ask Claude Code to check your work. This is how every day ends — the AI verifies that you actually did what you were supposed to.

In your terminal, in `my-onemillion-build`:

```bash
claude
```

Claude Code starts. Once it's ready, paste the entire contents of [`ai-instructions-day-01.md`](./ai-instructions-day-01.md) into the chat.

**You should see:** Claude reads your `.onemillion/project.json`, checks each requirement, and reports back. Either:
- ✅ **Pass** — Day 1 complete, you can move on to Day 2
- ⚠️ **Needs revision** — specific feedback on what to fix

If needs revision, fix the issues and re-paste the verification prompt.

---

## What Should Be True After Day 1

- [ ] `~/my-onemillion-build/` folder exists
- [ ] `.onemillion/project.json` exists and is valid JSON
- [ ] `product_type` is one of `web_app`, `ai_agent`, or `hybrid`
- [ ] `idea` is 2 sentences with a specific user and specific pain
- [ ] Verification ran and returned "Pass" (or you've addressed all revision notes)

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| `mkdir: command not found` | You're on Windows in CMD. Switch to Git Bash. |
| `mkdir: cannot create directory: Permission denied` | You're trying to create in a protected folder. Run `cd ~` first to go to your home folder. |
| Editor command `code` not found | Open VS Code manually, then File → Open → navigate to your folder. Then in VS Code: Cmd/Ctrl+Shift+P → "Shell Command: Install 'code' command". |
| JSON syntax error in verification | Check for missing commas, missing quotes, or trailing commas. Use [jsonlint.com](https://jsonlint.com) to find the issue. |
| Claude says "I can't find project.json" | Make sure you're running `claude` from inside `my-onemillion-build`, not from your home folder. |
| `.onemillion/` folder not visible | It's hidden (starts with `.`). Use `ls -la` to see it, or in VS Code use Cmd+Shift+. to toggle hidden files. |

---

→ **Done with Day 1?** Move to [Day 2 — Problem + Mom Test](../day-02-problem/learn.md).
