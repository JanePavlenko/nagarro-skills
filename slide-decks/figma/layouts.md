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

## Diagrams

### `Diagram - Flow Scheme, Simple / Light` — `1023:3254`
**Use for:** Simple horizontal flow with a small number of labeled nodes and a short caption. Use when the slide is *"A → B → C"* with one supporting sentence (not a full chevron banner).

| Slot | Type | Anchor | Notes |
|---|---|---|---|
| `diagram-note` | text(60) | (90, 694, 280, 40) | Small caption above/below the flow |
| `diagram-node` × N | text(20) | row at y≈748, 73 × 73 each | Short labels — 1–2 words each. Native shows 3 nodes; auto-layout adds more if needed |
| `Layout` | bg | full slide | Don't touch |
| `footer.*` | text | y=996 | |

> The internal graph + arrow vectors are part of the template — don't redraw them. If the content has 5+ nodes, prefer the **Progress Banner** atomic component instead.

### `Diagram - Architecture Flow / Light` — `1050:9267`
**Use for:** Architecture / system flow with stacked layers (e.g. *Experience → Context → Systems → Telemetry*). The `graph` group holds boxes + arrows; the `slide-content` is the heading area above.

| Slot | Type | Anchor | Notes |
|---|---|---|---|
| `slide-content` → title | text | (84, 186, 1751, 80) | 64pt title |
| `graph` group | shapes + labels | (89, 368, 1741, 504) | Editable in place — replace box labels and arrow labels; don't add new shapes |
| `footer.*` | text | y=996 | |

> The graph's internal box labels and arrow labels are individual TEXT nodes — drill into the group to populate them. Don't `createFrame` extra boxes; if you need more boxes than the template provides, this layout isn't the right pick.

---

## Infographics

### `Infographic - 3 Icons + Copy / Light` — `3052:4765`
**Use for:** Section intro that pairs a short headline + supporting paragraph at top with **3 icon + label + body** tiles below. Common for "Multi-X, Multi-Y, Multi-Z" framings.

| Slot | Type | Anchor | Notes |
|---|---|---|---|
| `chart-title` | text(60) | (90, 198, 1595, 80) | 64pt H1 |
| `body` (intro) | richtext | (90, 320, 1598, 124) | 24pt supporting paragraph |
| `chart-group` × 3 | icon visuals | (90 / 676 / 1272, 554) | Icon graphics, don't redraw |
| `label-1/2/3` | text(20) | (90 / 676 / 1272, 734, 560, 40) | 32pt Equip Extended Medium — short headers (1–2 words) |
| `body-1/2/3` | text(multi) | (90 / 676 / 1272, 806, 560, 93) | 24pt Equip Regular — 1–2 sentence descriptions |
| `footer.*` | text | y=996 | |

### `Infographic - Proportional Circles / Light` — `999:18436`
**Use for:** Single hero stat displayed as overlapping circles, with surrounding annotation labels. Use when one big percentage is the message.

| Slot | Type | Anchor | Notes |
|---|---|---|---|
| `Percentage` | text(6) | (753, 485, 402, 128) | 128pt; the hero number (e.g. "75%") |
| `Container` × 3 | text labels | scattered around the circles | Short annotation chips |
| `Layout` | bg | full slide | |
| `footer.*` | text | y=996 | |

---

## Tables

### `Table - Multi-Column Data / Light` — `999:14956`
**Use for:** Dense 4-column data table (e.g. Category / Sub-category / Description / Licensing). Built on the canonical content area at x=84, full-width.

| Slot | Type | Anchor | Notes |
|---|---|---|---|
| Header row | text(20) × 4 | y=197; col x = 94 / 366 / 859 / 1353 | 16pt header labels |
| Data rows | text × 4 cols | rows at y≈300, 485, 612, 665, 718, … | 16pt body; rows already styled — populate text, don't redraw |
| `table` frame | container | (84, 185, 1752, 569) | Native shows multiple rows; many are pre-filled with sample data — overwrite |

> For 3-column tables (decision matrices), use the **Table atomic component** (`3734:2374`, `cols=3`) — that one has a built-in mechanism to hide unused rows. This *Multi-Column Data* layout is a richer slide-level template for denser content.

---

## Timelines

### `Timeline - 4 Columns, Block Layout / Light` — `999:2181`
**Use for:** A 4-phase timeline where each phase is a card with a sprint/phase label, dates, and bullet-pointed work. Use for project plans and quarterly roadmaps.

| Slot | Type | Anchor | Notes |
|---|---|---|---|
| `timeline layout` | container | (84, 236, 1752, 655) | Holds the 4-phase strip |
| Phase title (e.g. "Sprint 1") | text(30) | per-column in `content` frame | 32pt headers; one per phase |
| Phase sub (e.g. "Sprint 2") | text(20) | 14pt | Smaller sub-label per phase |
| `content` | container | (84, 281, 1752, 610) | All editable text lives inside |
| `footer.*` | text | y=996 | |

> Each phase column holds a list of bullet items (visible after deeper inspection). Populate by finding the per-phase text nodes by their column position; don't restructure the column layout.

---

## Our Partners

### `Our Partners - 12 Logos (3×4) + Copy / Light` — `956:32333`
**Use for:** Credentials slide — a short paragraph on the left, a 3×4 logo grid on the right.

| Slot | Type | Anchor | Notes |
|---|---|---|---|
| `Copy` | richtext | (84, 383, 568, 285) | 24pt paragraph; one short sentence + maybe a CTA |
| `logo-grid` | image grid | (676, 169, 1157, 713) | 3 cols × 4 rows of partner logos; swap each logo's image fill |
| `footer.*` | text | y=996 | |

> Use the supplied partner logo components from the Local Components page when filling the grid; don't import outside logos.

---

## Why Nagarro

### `Why Nagarro - Headline Top, 3 Col Body / Light` — `1045:32964`
**Use for:** "Why us" framing — single headline followed by 3 parallel reasoning columns (e.g. *Relationship / Expertise / Experience*).

| Slot | Type | Anchor | Notes |
|---|---|---|---|
| `why-title` | text(80) | (84, 259, 1224, 160) | 64pt headline; wraps to 2 lines |
| `why-body-1` | richtext | (84, 484, 568, 336) | 18pt; ~120 words per column |
| `why-body-2` | richtext | (682, 484, 568, 288) | 18pt |
| `why-body-3` | richtext | (1280, 484, 568, 336) | 18pt |
| `footer.*` | text | y=996 | |

---

## Team

### `Team Member - Bio + Photo / Light` — `747:1813`
**Use for:** Single-person bio slide. Half-bleed photo on the right, name + role + bio paragraph on the left.

| Slot | Type | Anchor | Notes |
|---|---|---|---|
| `member-name` | text(30) | (84, 243, 625, 80) | 80pt Equip Extended Bold |
| `member-role` | text(30) | (84, 335, 200, 32) | 24pt Equip Extended Medium |
| `member-bio-intro` | richtext | (84, 415, 888, 94+) | 36pt opening sentence; supporting bio continues below |
| `CV Photo` | image | (1244, 0, 676, 1080) | Full-height portrait photo on the right; swap the image fill |
| `footer.*` | text | y=996 | |

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
