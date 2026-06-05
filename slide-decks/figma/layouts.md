# Nagarro Figma Slide Layouts — Slot Catalog

File: `LcZfBeKL7RcjQH4bqhi4Na` (Presentations Skill)
Canvas: **1920 × 1080 px**. Brand tokens (colors, type scale, margins, grid) live in [`brand/design-system.md`](../../brand/design-system.md).

This catalog lists every approved slide layout in the file with its **slot contract** — the named fillable layers, their types, positions, and constraints. The build flow is:

1. **Read the slide's content shape** (what slots does it need?).
2. **Pick the layout whose slots match** from this catalog.
3. **Clone the template, fill the slots.** Don't compose from atomic components unless no layout fits.

For each slot, the type signals what content goes in:
- `text(N)` — single-line text, max ~N characters
- `text(multi)` — multi-line, wraps automatically
- `richtext` — multiple paragraphs / line breaks allowed
- `number` — short numeric label (e.g. "01")
- `image` — image fill on a frame
- `list[N]` — fixed-cardinality list of subslots

Every layout shares the same **footer slot group** (omit on covers / chapter / outro variants only if explicitly marked):
- `footer.left` — `Digital Design Strategy` (or document/strategy name)
- `footer.mid-left` — `Project Name`
- `footer.mid-right` — `Month Year`
- `footer.right` — `© 2026` (year auto)

---

## Cover

### `Cover - Standard / Dark` — `872:16552`
**Use for:** Opening slide of a standard deck. Dark Petrol background, hero title + supporting subtitle, footer strip across bottom.

| Slot | Type | Position (x, y, w, h) | Constraint |
|---|---|---|---|
| `cover-title` | text(80) | (84, 436, 1308, 128) | 128pt Equip Extended Bold; 1–2 lines |
| `cover-subtitle` | text(140) | (84, 596, 1308, 48) | 48pt Equip Extended Medium; 1 line preferred |
| `footer.*` | text | (y=996) | All four cells populated |

---

### `Cover - Large Title, Mint / Dark` — `872:27249`
**Use for:** Hero cover when the title alone is the message. Title fills most of the slide; subtitle sits bottom-right.

| Slot | Type | Position | Constraint |
|---|---|---|---|
| `cover-title` | text(60) | (84, 183, 1386, 512) | **256pt** Equip Extended Bold; max 6–8 words |
| `cover-subtitle` | text(60) | (1296, 874, 540, 48) | 48pt; sits in bottom-right corner |
| `footer.*` | text | (y=996) | |

---

## Chapter cover

### `Chapter Cover - Large Title Left, Number Right / Dark` — `880:18634`
**Use for:** Section divider between major chapters. Big chapter title left, small number ("01", "02") bottom-right.

| Slot | Type | Position | Constraint |
|---|---|---|---|
| `chapter-title` | text(60) | (90, 383, 1308, 512) | 256pt Equip Extended Bold |
| `chapter-number` | number(2) | (1714, 799, 122, 96) | 96pt Equip Extended Light; "01"…"12" |
| `footer.*` | text | (y=996) | |

> Two more variants exist: *Vertically Centered, Number Top* and *Title Left, Number Right (compact)*. Add to catalog when needed.

---

## Content (general body slide)

### `Content - Title + Body / Light` — `3139:797`
**Use for:** Default body slide. Title + supporting line + a body paragraph or freeform area. **Use this as the canvas when dropping atomic components** (cards, banners, tables) — set `content-area.x=90, .y=164` and clear `content-body` first.

| Slot | Type | Position | Constraint |
|---|---|---|---|
| `content-title` | text(80) | (90, 228, 1627, 80) | 64pt Equip Extended Regular; pin frame to `(90, 164)` after clone |
| `content-subtitle` | text(140) | (90, 324, 1627, 45) | 24pt Equip Regular |
| `content-body` | richtext | (90, 423, 1160, 495) | 24pt Equip Regular; clear this when using atomic components in its place |
| `footer.*` | text | (y=996) | |

---

## Executive Summary

### `Executive Summary - 3 Col, Title Above / Light` — `945:16529`
**Use for:** Three parallel paragraphs under a section title. Each column ≈ 563 px wide. Ideal for *"Customer ambition / Platform opportunity / Business outcome"* or any 3-aspect framing.

| Slot | Type | Position | Constraint |
|---|---|---|---|
| `exec-title` | text(40) | (84, 345, 1751, 80) | 64pt Equip Extended Regular; full-width header |
| `exec-body-1` | richtext | (84, 457, 563, 279) | 24pt Equip Regular |
| `exec-body-2` | richtext | (679, 457, 563, 279) | 24pt |
| `exec-body-3` | richtext | (1273, 457, 563, 217) | 24pt |
| `footer.*` | text | | |

### `Executive Summary - 3 Col, Title as First Col / Light` — `872:6179`
**Use for:** Same 3-paragraph structure but title takes the first column, leaving 2 paragraph columns. Use when the section name itself is short and you want more body space.

| Slot | Type | Position | Constraint |
|---|---|---|---|
| `exec-title` | text(30) | (84, 354, 568, 160) | 64pt; column 1 |
| `exec-body-1` | richtext | (678, 354, 568, 403) | 24pt; column 2 |
| `exec-body-2` | richtext | (1272, 354, 568, 372) | 24pt; column 3 |
| `footer.*` | text | | |

---

## A Note From Us

### `A Note From Us - Title Top, Text Bottom Left / Light` — `880:23086`
**Use for:** Letter-style opening — section name + studio header line, then a large title, then a multi-paragraph note in the lower-left. Common for proposals and pitches.

| Slot | Type | Position | Constraint |
|---|---|---|---|
| `note-name-1` | text(20) | (1439, 77, 123, 20) | 16pt; right-aligned tag (e.g. *Product Studio*) |
| `note-name-2` | text(20) | (1610, 77, 157, 20) | 16pt; presentation name |
| `note-name-3` | number(2) | (1815, 77, 21, 20) | 16pt; page/section number |
| `note-title` | text(40) | (86, 201, 858, 80) | 80pt Equip Extended Medium |
| `note-intro` | richtext | (84, 586, 1160, 405) | 24pt; multi-paragraph note |

> No footer-strip on this variant — the page-name row at top replaces it.

---

## Highlights

### `Highlights - Quote, Centered / Light` — `883:2744`
**Use for:** Big centered pull-quote with attribution. Use sparingly — once per chapter for emphasis.

| Slot | Type | Position | Constraint |
|---|---|---|---|
| `quote` | text(140) | (232, 286, 1308, 384) | 96pt Equip Extended Medium; prepend `"` glyph; 2–3 short lines |
| `attribution` | text(40) | (232, 718, 1308, 47) | 36pt Equip Regular; format `— Name, Role` |
| `footer.*` | text | | |

---

## About Nagarro

### `About Nagarro - Headline + 3 Content Boxes / Light` — `956:5267`
**Use for:** "About Nagarro" framing slide — top headline, then 3 boxes of bite-sized context (Our clients / Our work / Our scale).

| Slot | Type | Position | Constraint |
|---|---|---|---|
| `about-title` | text(140) | (84, 253, 1752, 160) | 64pt Equip Extended Regular |
| `about-box-1-title` | text(30) | (116, 689, 504, 31) | 32pt Equip Extended Medium |
| `about-box-1-body` | text(multi) | (116, 760, 504, 93) | 24pt Equip Regular |
| `about-box-2-title` | text(30) | (708, 689, 504, 31) | 32pt |
| `about-box-2-body` | text(multi) | (708, 760, 504, 93) | 24pt |
| `about-box-3-title` | text(30) | (1300, 689, 504, 31) | 32pt |
| `about-box-3-body` | text(multi) | (1300, 760, 504, 93) | 24pt |
| `footer.*` | text | | |

---

## Outro

### `Outro - Tagline + Logo / Dark` — `1045:25071`
**Use for:** Closing slide. Big tagline left of center, brand lockup right. Default closing for any deck.

| Slot | Type | Position | Constraint |
|---|---|---|---|
| `outro-headline` | text(80) | (230, 460, 568, 160) | 64pt Equip Extended Regular; 1–2 short lines |
| `footer.*` | text | | |

---

## How to use this catalog

```javascript
// 1. Clone the template
const layout = await figma.getNodeByIdAsync("3139:797");   // Content - Title + Body / Light
const slide = layout.clone();
slide.x = idx * 2020; slide.y = 0;
page.appendChild(slide);

// 2. Fill the slots (by layer name)
await setText(findByName(slide, "content-title"),    "…");
await setText(findByName(slide, "content-subtitle"), "…");
await setText(findByName(slide, "content-body"),     ""); // clear if dropping atomic components here

// 3. Footer
populateFooter(slide, ["Digital Design Strategy", "<Project>", "<Month Year>"]);
```

**Rule of thumb:**
- If the content fits a layout's slot contract → **use the layout**.
- If it doesn't fit any layout → fall back to `Content - Title + Body / Light` + atomic components from [`slide-components.md`](slide-components.md).
- Never invent layouts. If the content shape isn't in this catalog, propose extending the catalog rather than composing manually.

---

## Next batches to catalog

Still to do (covered by the file but not yet in this catalog):

- **About Nagarro** — 9 more variants (Services Icon Grid, Caring Values, Stats Bubbles, Headline + Photo, etc.)
- **Why Nagarro** — 6 variants (AI-Assisted SDLC, Headline + 2/3 Col Body, etc.)
- **Our Partners** — 13 variants (12 Logos, 20 Logos, Testimonials, Project Showcases, Co-Branding, etc.)
- **Diagrams** — 5 variants (Flow Scheme Simple/Complex, Process Roadmap, Taxonomy Tree, Architecture Flow)
- **Infographics** — 11 variants (Vertical Bars, Horizontal Bar Segmented, Proportional Circles, Venn 2/3 Circle, Layer Stack, 3 Icons + Copy, etc.)
- **Tables** — 3 variants (Multi-Column Data, Pricing Breakdown, Milestones + Dependencies)
- **Timelines** — 4 variants (8 Columns High-Level, 4 Columns Block Layout, Short Period Stacked Cards)
- **Team** — 9 variants (Bio + Photo, Team Composition, 10 Members, Structure, etc.)
- **Index** — 9 variants (already documented separately in [`slide-rules/index.md`](../slide-rules/index.md))
- **Confidentiality Statement** — 3 variants

Total remaining: ~70 layouts. Cataloging in batches of ~10.
