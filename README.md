# Nagarro Skills

Standalone Claude skills for producing Nagarro-branded outputs — decks, posts, covers, campaigns, and internal comms. Each skill is self-contained: it guides you through a brief, applies the Nagarro brand automatically, and delivers a finished result.

---

## How to use

### Step 1 — Open the repo in Claude Code

1. Go to [claude.ai](https://claude.ai) and open **Claude Code** (the cloud version)
2. Click **Open repo** and connect `JanePavlenko/nagarro-skills`
3. That's it — all skills load automatically. No install, no setup.

> **Local alternative:** Clone the repo and open it in Claude Code CLI.
> ```bash
> git clone https://github.com/JanePavlenko/nagarro-skills
> cd nagarro-skills
> claude
> ```

---

### Step 2 — Tell Claude what you want

Just describe what you need in plain language. Claude picks the right skill automatically.

| What you say | Skill that runs |
|---|---|
| "Build me a deck about Nagarro for a new client" | `nagarro-figma-deck` or `nagarro-pptx-deck` |
| "Create a PowerPoint about our AI capabilities" | `nagarro-pptx-deck` |
| "Make a Figma presentation for the design team" | `nagarro-figma-deck` |
| "Create an event banner for our AI workshop" | `nagarro-email-cover` |
| "Write a LinkedIn post about our new project" | `nagarro-linkedin-post` |
| "Plan a campaign to promote our cloud services" | `nagarro-marketing-campaign` |
| "Draft an all-hands email about the org change" | `nagarro-internal-comms` |

You can also name the skill directly: `"Use nagarro-linkedin-post to write a post about X"`

---

### Step 3 — Answer the brief questions

Every skill asks you a few questions before it starts building — audience, topic, key messages, etc.

You'll see a quick menu like this:

> **Who is the audience?**
> - New prospect — doesn't know Nagarro
> - Existing client or partner
> - Internal team
> - C-suite / leadership

Answer the questions, then the skill builds your deliverable.

---

### Step 4 — Review and approve

For decks and visual outputs, the skill shows you a slide plan before building:

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
| `nagarro-figma-deck` | A new page in the Presentations Skill Figma file with all slides |
| `nagarro-pptx-deck` | A `.pptx` file saved in the `output/` folder |
| `nagarro-email-cover` | A Figma frame at 1400×400px, ready to export |
| `nagarro-linkedin-post` | Copy-paste ready post text |
| `nagarro-marketing-campaign` | A structured campaign brief with channel plan |
| `nagarro-internal-comms` | A finished letter or email, ready to send |

---

## Skills at a glance

### 🎨 nagarro-figma-deck
Builds a branded Nagarro presentation deck in Figma. Clones slides from the official template file, populates content, and sets the footer. Follows all Nagarro design system rules.

**Use when:** You need a Figma-native deck — for sharing, presenting, or handing off to design.

**You'll need to provide:**
- Deck topic and audience
- Project/client name
- Key messages (3–5 points)

---

### 📊 nagarro-pptx-deck
Builds a branded `.pptx` using Nagarro section templates. Every slide is copied from a pre-built template file — no slides are built from scratch.

**Use when:** You need a PowerPoint to send by email or present offline.

**You'll need to provide:**
- Deck topic and audience
- Project/client name + month/year for the footer
- Key messages (3–5 points)

---

### 🖼 nagarro-email-cover
Creates a 1400×400px email or event banner in Figma with a deep purple gradient background — the Nagarro AI Sandbox Sessions style.

**Use when:** You're sending an event invite, newsletter, or announcement and need a header image.

**You'll need to provide:**
- Event or session title (the headline)
- Optional: category tag, date, speaker name

---

### 💼 nagarro-linkedin-post
Writes a LinkedIn post in the Nagarro Product Studio voice — direct, human, no buzzwords. Includes a self-review against the tone of voice guide before returning the final copy.

**Use when:** You need to post about a project, event, hire, or company update on LinkedIn.

**You'll need to provide:**
- Topic and key message
- Purpose (share a win, announce something, thought leadership, etc.)

---

### 📣 nagarro-marketing-campaign
Plans an external marketing campaign — sets the audience, message, hook, proof points, and channel strategy. Returns a structured campaign brief with a content list to execute.

**Use when:** You're planning a product launch, event push, or brand campaign and need a strategy before writing content.

**You'll need to provide:**
- Campaign goal
- Target audience
- Key proof point or story to lead with
- Channels (LinkedIn, email, events, paid, etc.)

---

### ✉️ nagarro-internal-comms
Writes internal letters and company-wide announcements — all-hands, org changes, leadership news, policy updates, and sensitive communications. Always leads with people, not process.

**Use when:** You need to communicate something to the team — big or small.

**You'll need to provide:**
- What the news is
- Who it's going to
- Who is signing the message

---

## Brand foundation

All skills draw from shared docs in `brand/`. You don't need to read them — the skills do it automatically.

| Doc | Used by |
|---|---|
| `brand/tone-of-voice.md` | All copy skills (LinkedIn, internal comms, marketing) |
| `brand/design-system.md` | All visual skills (Figma deck, PowerPoint, email cover) |
| `brand/positioning.md` | All skills — Nagarro's core message and value prop |

---

## Tips

- **Be as specific as you can in your first message.** The more context you give, the fewer follow-up questions the skill needs to ask.
- **You can say "skip" or "I'll decide later"** for any optional brief question.
- **For decks:** always review the slide plan before approving — it's much faster to adjust the plan than to rebuild slides.
- **For LinkedIn posts:** mention any real stats, project names, or quotes you want included — the skill won't invent them.
- **For campaigns:** the skill returns a brief, not the finished content. Use the other skills (LinkedIn, email cover, deck) to execute it.
