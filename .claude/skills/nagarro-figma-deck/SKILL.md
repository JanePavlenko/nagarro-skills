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

For each slide in the brief, decide which layout to use **in this order**:

1. **Catalog match.** Read [`slide-decks/figma/layouts.md`](../../../slide-decks/figma/layouts.md). For the slide's content shape (eyebrow + title + N cards / quote / table / flow / stat grid / etc.) pick the layout whose **slot contract** matches. This is the default path — never skip it.
2. **Atomic component fit.** If no full layout matches but the content is one of the documented patterns (3/4/6/8 cards, process steps, statement bar, table, conclusion slide, progress banner), clone `Content - Title + Body / Light` (`3139:797`) and drop in components from [`slide-decks/figma/slide-components.md`](../../../slide-decks/figma/slide-components.md) following [`slide-decks/slide-rules/cards-and-process.md`](../../../slide-decks/slide-rules/cards-and-process.md).
3. **Create-new recipe.** Only if neither 1 nor 2 fits, follow [`slide-decks/figma/create-new.md`](../../../slide-decks/figma/create-new.md) to compose a new component using brand tokens. Never draw without that recipe.

Produce a numbered slide plan. For each slide:
- The layout name + node ID (or "Content + atomic components" / "Create-new") and *why*
- A one-line content summary

> **Do not default to "Content + 3 cards" for everything.** That was the old behavior and led to repetitive, force-fit decks. The catalog has ~90 layouts — most slides should map to one of them.

### Index slide rule
Include an Index slide only when **both** apply:
- Chapter count ≥ 2
- Total slide count ≥ 15

Otherwise skip it. Go Cover → first content slide.

### Diagram slide rule
Never place a Diagram slide unless the brief contains real content for every visible node.
Diagrams with placeholder nodes ("Title", "Bullet Point 1") are rejected.
Drop or substitute with a text-based slide.

### Cards & process slides rule
When the brief, a reference image, or a user description implies **N parallel items** (3/4/6/8) or **a sequence of steps**, do **not** draw boxes by hand. Read [`slide-decks/slide-rules/cards-and-process.md`](../../../slide-decks/slide-rules/cards-and-process.md) and use the Card components from [`slide-decks/figma/slide-components.md`](../../../slide-decks/figma/slide-components.md). The doc maps every count (3/4/6/8) and process length to a component, node ID, and exact x/y/w/h.

Triggers include: "process", "steps", "stages", "phases", "flow", "pillars", "proof points", "journeys", "value props", or any reference slide showing N equal-weight cards in a row or grid.

### No placeholder copy
Every text layer must contain real content. Never ship:
`Lorem ipsum`, `Title`, `Subtitle`, `Bullet Point 1/2/3`, `This is a paragraph`,
`small note`, `Server`, `Your title goes here`, or any other template default.

---

## Step 3 — Confirm the plan

Present the slide plan and wait for explicit approval before touching Figma.

---

## Step 4 — Build in Figma

Use the `mcp__plugin_figma_figma__use_figma` tool to execute a JavaScript build script against the Presentations Skill file.

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

After executing, call `mcp__plugin_figma_figma__get_screenshot` to capture the deck page and confirm:
- Correct slide count
- No placeholder text visible
- Footer populated on every slide

Report the Figma page URL when done.
