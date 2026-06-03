# Deck Brief Guide — How to Get the Best from AI Deck Generation

> **For AI use:** This doc is the script for guiding the deck brief conversation. Do NOT ask the user to read it. Instead, use `AskUserQuestion` to present each step as a numbered menu (max 4 options + Other). Walk through the questions below in order, one screen at a time, and adapt follow-up questions based on the user's answers. Never ask more than 4 questions at once.

This guide defines the questions AI asks when a user wants to build a deck, and what each scenario requires.

---

---

## AI conversation script — follow this order

When a user asks to build a deck, run through these steps using `AskUserQuestion`. Present one screen at a time. Never skip to building until all required inputs are collected and the slide plan is approved.

### Screen 1 — Scenario

```
AskUserQuestion:
  "Which of these best describes what you're looking for?"
  Options:
  1. Broad idea — I want to explore what a deck on a topic could look like
  2. Brief-driven — I have a document or specific context to base it on
  3. Fully specified — I know exactly what I want, slide by slide
  4. Update existing deck — I want to change part of a deck that already exists
  Other: Quick internal / something else — tell me more
```

Adapt all follow-up questions based on the answer.

### Screen 2 — Deck type (skip if scenario = Update existing)

```
AskUserQuestion:
  "What type of deck is this?"
  Options:
  1. Proposal / RFP response
  2. Capability Overview
  3. Project Kick-off
  4. Recruitment / Employer Branding
  Other: Internal update / Other
```

### Screen 3 — Audience

```
AskUserQuestion:
  "Who is the audience?"
  Options:
  1. New prospect — they don't know Nagarro yet
  2. Existing client or partner
  3. Internal team
  4. C-suite / leadership
  Other: Mixed / Other — describe
```

Also ask (as a follow-up text question): **"What do you want them to do or feel after seeing this deck?"**

### Screen 4 — Format and length

```
AskUserQuestion:
  "How long do you have to present?"
  Options:
  1. Up to 10 minutes (~8–12 slides)
  2. Around 20–30 minutes (~15–25 slides)
  3. 45–60 minutes — full proposal walk-through (~30–40 slides)
  4. I have a specific slide count in mind
  Other: No fixed time / I'm not sure
```

Also ask: **"Figma or PowerPoint?"** and **"Any slides that must be included, or anything to leave out?"**

Also ask as plain text questions:
- **"What is the project or client name?"** — used to populate the footer on every slide (the "Project Name" field)
- **"What month and year is this deck for?"** — used to populate the "Month Year" footer field (e.g. "June 2026")

### Screen 5 — Content (adapt to scenario)

For **Broad idea**: ask for the topic and 3–5 key messages or themes to cover.

For **Brief-driven**: ask the user to paste or upload their document (save to `uploads/` locally — never commit). Extract key messages and context from it automatically.

For **Fully specified**: ask for a numbered list of slides with content summaries.

For **Update existing**: ask for the Figma deck page name and which slides to change.

### Before building — always

Present the slide plan as a numbered list (slide type + one-line content summary per slide) and ask:

```
AskUserQuestion:
  "Does this slide plan look right before I build?"
  Options:
  1. Yes — build it
  2. Add more slides to a chapter
  3. Remove or swap a slide
  4. Change the structure
  Other: Something else
```

Only build after explicit approval.

---

## Before anything is built

AI will always do three things before building:

1. **Ask for any missing key inputs** — if something critical is absent, it asks now, not after building
2. **Show you a slide plan** — a numbered list with slide type and content summary per slide
3. **Wait for your approval** — nothing is built until you confirm the plan

Reviewing the slide plan carefully is the single most important step. Getting it right here means far fewer corrections later.

---

## Scenarios

### 1. Exploratory — "Give me a broad idea of what a deck on X could look like"

Use this when you're not sure yet what the deck should contain and want to see a structure before committing.

**What to give AI:**
- Topic
- Who the audience is (even roughly)
- Rough slide count or presentation time

**What happens:** AI produces a slide plan with section suggestions. You approve or adjust the structure, then it builds.

---

### 2. Brief-driven — "Here's a document, build me a deck from this"

Use this when you have a client document, an RFP, an email thread, a brief, or any written context you want the deck to be based on.

**What to do:** upload or paste the document. AI reads it and extracts the key messages, client context, and relevant content. It then proposes a slide plan for your approval before building.

> **Note:** uploaded documents are used locally for your session only. They are never saved to the shared repository.

**What to also tell AI:**
- Deck type (usually Proposal for RFPs)
- Any slides the client specifically requested
- Anything to leave out

---

### 3. Fully specified — "I know exactly what I want"

Use this when you have a clear idea of every slide.

**What to give AI:** a list of slide titles and what each one should say or show. AI maps each to the right template and builds directly.

---

### 4. Update existing deck — "Change part of this deck"

Use this when a deck already exists and you need to update specific slides or sections.

**What to give AI:**
- The Figma deck page name (e.g. `Design Capability — May 2026`)
- Which slides or chapters to change
- What to change them to

> **Token tip:** batch all your changes into one message. "Update slides 3, 7, and 12" in one go is much more efficient than three separate requests.

---

### 5. Quick internal — "I have 10 minutes to present our progress"

Use this when it's a short internal update with no client-facing formality needed.

**What to give AI:**
- Topic
- Time available
- 3–5 key points you want to cover

**What happens:** AI builds a short deck, skips Nagarro intro sections (Why Nagarro, About Nagarro), and keeps content direct.

---

## Slide count formula

Not sure how many slides you need? Use this as a starting point:

| Presentation time | Suggested slide count |
|---|---|
| 5 minutes | 4–6 slides |
| 15 minutes | 10–15 slides |
| 30 minutes | 20–25 slides |
| 45–60 minutes | 30–40 slides |

These are guides, not hard limits. Let content drive length — don't pad or cut to hit a number.

---

## Full input checklist

The more of these you give AI, the better the first draft will be.

**Context**
- [ ] Topic / project name
- [ ] Client or company name (if applicable)
- [ ] Deck type: Proposal, Capability Overview, Project Kick-off, Internal, or Recruitment
- [ ] Who is the audience? (e.g. client C-suite, internal team, new prospect, existing partner)
- [ ] Do they already know Nagarro? (yes/no — this affects which sections get included)
- [ ] What do you want them to do or feel after seeing this deck?

**Content**
- [ ] Key message — one sentence if possible
- [ ] Main topics to cover
- [ ] Mandatory slides or content that must be included
- [ ] Anything to leave out
- [ ] References — past decks, documents, website pages AI can draw from

**Format**
- [ ] Slide count or presentation time
- [ ] Output format: Figma or PowerPoint
- [ ] Language (default: English)
- [ ] Tone: formal and persuasive / informative and clear / inspirational

---

## How to give good correction instructions

Vague corrections lead to more rounds. Be as specific as you can:

| Instead of | Say |
|---|---|
| "Make slide 4 better" | "Slide 4 needs a timeline with 3 phases: Q1 design, Q2 build, Q3 launch" |
| "The deck feels thin" | "Add 2 content slides to chapter 3 covering our technical approach" |
| "Change the layout of slide 7" | "Slide 7 — try a different layout" (AI will show you up to 2 options to pick from) |
| "I don't like these slides" | "Slides 4 and 9 — can you show me alternative layouts?" |

**Batch your corrections.** If you have multiple changes, send them all in one message rather than one at a time.

---

## Choosing layouts

If you ask to change a slide's layout, AI will show you up to 2 screenshots of the available template options before building anything. You choose, AI builds.

If no alternative template exists for that slide type, AI will tell you clearly and offer to build a custom layout from the Nagarro design system. It will only create this if you confirm.

---

## What AI needs to know about your audience

This is the question most people skip — and it has the biggest impact on the result.

- **New prospect who doesn't know Nagarro** → include Why Nagarro and About Nagarro sections
- **Existing client** → skip those sections, focus on the solution
- **Internal team** → skip all Nagarro intro sections, keep it direct
- **C-suite** → lead with the key message, keep slide copy short
- **Technical audience** → more depth on the approach, less on the company story
