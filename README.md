# Nagarro Skills

Standalone Claude skills for producing Nagarro-branded outputs.
Each skill guides you through a brief, applies the Nagarro brand automatically, and delivers a finished result.

**All skills run in Claude Code only.**

---

## What's available

| Skill | Command | What it produces |
|---|---|---|
| `nagarro-linkedin-post` | `/nagarro-linkedin-post` | LinkedIn post |
| `nagarro-internal-comms` | `/nagarro-internal-comms` | Internal letter or announcement |
| `nagarro-marketing-campaign` | `/nagarro-marketing-campaign` | Campaign strategy brief |
| `nagarro-pptx-deck` | `/nagarro-pptx-deck` | PowerPoint `.pptx` file |
| `nagarro-figma-deck` | `/nagarro-figma-deck` | Figma presentation deck |
| `nagarro-email-cover` | `/nagarro-email-cover` | Email / event banner in Figma |

---

## How to use

### Step 1 — Open the repo in Claude Code

**Option A — Browser only (recommended)**

No terminal. No install. Just a browser.

1. Go to [claude.ai](https://claude.ai)
2. Click **Code** in the left sidebar
3. Click **Connect repo** → search for `JanePavlenko/nagarro-skills` → connect
4. Done — all skills load automatically

---

**Option B — Local (for developers)**

Requires [Git](https://git-scm.com/downloads) and Claude Code CLI installed (`npm install -g @anthropic-ai/claude-code`).

**First time — download the repo:**
```bash
git clone https://github.com/JanePavlenko/nagarro-skills
cd nagarro-skills
claude
```

**Next time — just open it:**
```bash
cd nagarro-skills
claude
```

---

### Step 2 — Run a skill

Type the `/command` and hit enter. Claude launches the skill immediately.

```
/nagarro-linkedin-post
/nagarro-pptx-deck
/nagarro-figma-deck
```

---

### Step 3 — Answer the brief questions

Every skill asks a few questions before building — topic, audience, key messages, etc.

```
What is this post about?
Who is the audience?
What's the one thing you want people to take away?
```

Answer the questions, then the skill produces your deliverable.

---

### Step 4 — Review and approve

For decks, the skill shows a slide plan before building:

```
PLAN:
1. Cover — "Nagarro AI Capabilities"
2. About Nagarro — At a Glance
3. Our Services — Icon Grid
4. Outro

Does this look right?
```

Say **yes** to build, or tell it what to change.

---

### Step 5 — Get your deliverable

| Skill | What you get |
|---|---|
| `/nagarro-linkedin-post` | Copy-paste ready post text |
| `/nagarro-internal-comms` | Finished letter or email, ready to send |
| `/nagarro-marketing-campaign` | Structured campaign brief with channel plan |
| `/nagarro-pptx-deck` | `.pptx` file saved in `output/` |
| `/nagarro-figma-deck` | New page in the Presentations Skill Figma file |
| `/nagarro-email-cover` | Figma frame at 1400×400px, ready to export |

---

## Skills in detail

### 💼 `/nagarro-linkedin-post`
Writes a LinkedIn post in the Nagarro voice — direct, human, no buzzwords. Reviews the draft against the tone of voice guide before returning the final copy.

**You'll need:** topic, key message, purpose (win, announcement, thought leadership, etc.)

---

### ✉️ `/nagarro-internal-comms`
Writes internal letters and company-wide announcements — all-hands, org changes, leadership news, policy updates. Always leads with people, not process.

**You'll need:** what the news is, who it's going to, who is signing it

---

### 📣 `/nagarro-marketing-campaign`
Plans an external marketing campaign — audience, single message, hook options, channel plan, and a list of content to produce.

**You'll need:** campaign goal, target audience, strongest proof point, channels

---

### 📊 `/nagarro-pptx-deck`
Builds a branded `.pptx` using Nagarro section templates. Every slide is copied from a pre-built template — nothing built from scratch.

**You'll need:** deck topic, audience, project/client name, key messages (3–5 points)

---

### 🎨 `/nagarro-figma-deck`
Builds a branded presentation deck in Figma. Clones slides from the official Presentations Skill template file, populates content, and sets the footer.

**You'll need:** deck topic, audience, project/client name, key messages (3–5 points)

---

### 🖼 `/nagarro-email-cover`
Creates a 1400×400px email or event banner in Figma — deep purple gradient, Nagarro AI Sandbox Sessions style.

**You'll need:** event or session title, optional category tag, date, speaker name

---

## Brand foundation

All skills draw from shared docs in `brand/` — loaded automatically, you don't need to read them.

| Doc | Used by |
|---|---|
| `brand/tone-of-voice.md` | LinkedIn, internal comms, marketing campaign |
| `brand/design-system.md` | Figma deck, PowerPoint deck, email cover |
| `brand/positioning.md` | All skills |

---

## Tips

- **Be specific in your first message** — the more context you give, the fewer follow-up questions
- **For decks** — always review the slide plan before approving; faster to adjust the plan than rebuild slides
- **For LinkedIn posts** — include any real stats, names, or quotes; the skill won't invent them
- **For campaigns** — the skill returns a brief, not finished content; use the other skills to execute each piece
