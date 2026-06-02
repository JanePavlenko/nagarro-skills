# Chat Projects — Setup Guide

These files let you use Nagarro writing skills directly in **regular Claude chat** — no Claude Code needed.

Each file is a ready-made instruction set for a **Claude Project**.

---

## What is a Claude Project?

A Project is a space in Claude.ai where you set custom instructions and upload knowledge files. Every conversation inside that Project automatically follows those instructions — so Claude always knows the Nagarro brand rules without you having to explain them.

---

## How to set one up (5 minutes)

### Step 1 — Create a new Project

1. Go to [claude.ai](https://claude.ai)
2. Click **Projects** in the left sidebar
3. Click **New Project**
4. Give it a name — e.g. `Nagarro LinkedIn Posts`

### Step 2 — Add the instructions

1. Inside the project, click **Edit project instructions** (or **Custom instructions**)
2. Open the matching file from this folder:
   - LinkedIn posts → `linkedin-post.md`
   - Internal letters → `internal-comms.md`
   - Marketing campaigns → `marketing-campaign.md`
3. Copy the entire content and paste it into the instructions field
4. Save

### Step 3 — Upload the brand files

1. In the same project, click **Add content** or **Upload files**
2. Upload these two files from the `brand/` folder:
   - `brand/tone-of-voice.md`
   - `brand/positioning.md`
3. Save

### Step 4 — Start a conversation

Open a new chat inside the project and just describe what you need:

> "Write a LinkedIn post about our new AI project in Vienna"

> "Draft an all-hands email about the leadership change"

> "Plan a campaign to promote our cloud services to retail clients"

Claude will ask you the brief questions, then produce the result — fully on-brand, no setup needed each time.

---

## Projects to create

| Project name | Instruction file | What it does |
|---|---|---|
| Nagarro LinkedIn Posts | `linkedin-post.md` | Writes LinkedIn posts in Nagarro voice |
| Nagarro Internal Comms | `internal-comms.md` | Writes internal letters and announcements |
| Nagarro Marketing Campaign | `marketing-campaign.md` | Plans external marketing campaigns |

---

## What about decks, banners, and Figma?

Those still require Claude Code — they generate files and connect to Figma, which isn't possible in regular chat. See the main README for how to use those skills.
