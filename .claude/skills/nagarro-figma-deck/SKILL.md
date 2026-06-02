---
name: nagarro-figma-deck
description: Build a branded Nagarro presentation deck directly in Figma. Use this skill whenever a user asks to create, build, or generate a slide deck, presentation, or any set of slides in Figma for Nagarro — even if they just say "make me a deck about X" or "create slides in Figma". Triggers: figma deck, figma slides, figma presentation, build deck in figma, create presentation figma.
---

You build Nagarro slide decks in Figma using the official Presentations Skill template file.

Every slide comes from a template. You never create frames from scratch.
You collect a full brief before touching Figma.

---

## Brand anchor

Before collecting the brief or building anything, read:
- `brand/design-system.md` — colours, typography, layout rules
- `brand/positioning.md` — Nagarro's core message and value proposition

The Figma template file key is: `LcZfBeKL7RcjQH4bqhi4Na`

---

## Step 1 — Collect the brief

Ask for any missing inputs using `AskUserQuestion`. You need:

1. **Topic / title** — what is the deck about?
2. **Audience** — new prospect, existing client, internal team, or C-suite?
3. **Deck type** — Capability Overview, Proposal, Internal, Recruitment, or other?
4. **Length** — short (6–8 slides), standard (12–15), long (20–30)?
5. **Project / client name** — for the footer "Project Name" field
6. **Month and year** — for the footer "Month Year" field (e.g. "June 2026")
7. **Key messages** — 3–5 talking points or themes to cover

---

## Step 2 — Plan the slide sequence

Produce a numbered slide plan. For each slide:
- The exact template frame name from the Figma file
- A one-line content summary

### Index slide rule
Include an Index slide only when **both** apply:
- Chapter count ≥ 2
- Total slide count ≥ 15

Otherwise skip it. Go Cover → first content slide.

### Diagram slide rule
Never place a Diagram slide unless the brief contains real content for every visible node.
Diagrams with placeholder nodes ("Title", "Bullet Point 1") are rejected.
Drop or substitute with a text-based slide.

### No placeholder copy
Every text layer must contain real content. Never ship:
`Lorem ipsum`, `Title`, `Subtitle`, `Bullet Point 1/2/3`, `This is a paragraph`,
`small note`, `Server`, `Your title goes here`, or any other template default.

---

## Step 3 — Confirm the plan

Present the slide plan and wait for explicit approval before touching Figma.

---

## Step 4 — Build in Figma

Use the `use_figma` MCP tool to execute a JavaScript build script against the Presentations Skill file.

### Key technical rules

- **Page names**: template pages are named `└ Cover`, `└ Index`, `└ About Nagarro & Why Nagarro`, etc. — no "DONE" suffix. Use `.includes()` for matching.
- **Section-aware lookup**: About Nagarro, Why Nagarro, Graphs & Tables pages nest frames inside Sections. Use:

```javascript
function findTemplateFrame(page, frameName) {
  const direct = page.children.find(f => f.type === 'FRAME' && f.name === frameName);
  if (direct) return direct;
  for (const child of page.children) {
    if (child.type === 'SECTION' && child.children) {
      const hit = child.children.find(f => f.type === 'FRAME' && f.name === frameName);
      if (hit) return hit;
    }
  }
  return null;
}
```

- **Guard leaf nodes** in recursion — use `kids()`:

```javascript
function kids(node) {
  return ('children' in node && Array.isArray(node.children)) ? node.children : [];
}
```

- **Page setup**: `await figma.setCurrentPageAsync(page)` — never `figma.currentPage = page`
- **Positioning**: slides are 1920×1080px, step = 2020px (`x = slideIndex * 2020`)
- **Font loading**: load all fonts at the top before any per-slide work; use mixed-font pattern for layers where `fontName === figma.mixed`
- **Never edit template frames** — always clone first, then edit the clone
- **Footer on every slide**: set `Digital Design Strategy`, `Project Name`, `Month Year`

### Known frame names (verified)
| Template | Frame name |
|---|---|
| Cover | `Cover - Standard / Dark` |
| Chapter Cover | `Chapter Cover - Title Left, Number Right / Dark` |
| About Nagarro At a Glance | `About Nagarro - Stats Bubbles, Full-Width Photo / Dark` |
| About Nagarro Caring Values | `About Nagarro - Caring Values, Icons / Dark` |
| About Nagarro Services Grid | `About Nagarro - Services Icon Grid / Light` |
| Our Partners 12 logos | `Our Partners - 12 Logos (3×4) + Copy / Light` |
| Diagram Flow Simple | `Diagram - Flow Scheme, Simple / Light` |
| Outro | `Outro - Tagline + Logo / Dark` |

---

## Step 5 — Verify

After executing, take a screenshot of the deck page and confirm:
- Correct slide count
- No placeholder text visible
- Footer populated on every slide

Report the Figma page URL when done.
