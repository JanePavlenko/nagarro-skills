# Nagarro Figma Slide Components — Assembly Rules

File: `LcZfBeKL7RcjQH4bqhi4Na` (Presentations Skill)
Page: **Local Components** (page id `732:745`)
Section: **Cards & Process** (section id `3620:5259`)

---

## Component Inventory

### Card Section — `3620:1244` (COMPONENT_SET)

A content card with a title, body text, and an optional icon. Used as the base unit for both section grids and process steps.

| Variant | Node ID | Size (native) | Use when |
|---|---|---|---|
| `Icon=true` | `3620:1140` | 547 × 290 px | Primary choice — icon adds visual hierarchy |
| `Icon=false` | `3620:1421` | 547 × 194 px | Dense layouts (8+ cards, narrow columns) |

**Anatomy (native component):**
- Background: `#eff1f4`, border-radius 8px
- Icon: 80 × 80 px (top, Icon=true variant only)
- Title: 34px Equip Extended Medium, `#010716`
- Body: 20px Equip Regular, `#535457`, line-height 1.4

**Grid alignment rule (mandatory):**
- The card row **starts at x = 90** — the same left edge as the slide title. Never center the row.
- The row fills the full content area: **x = 90 to x = 1830** (width = 1740 px).
- Per-card width = `(1740 − (N − 1) × 24) / N` where N is the column count and 24 px is the column gap.

| N (cols) | Card width | Use case |
|---|---|---|
| 2 | 858 | Two-up cards (e.g. mockup signals) |
| 3 | 564 | 3-card grid or 3×N grid |
| 4 | 417 | 4-card single row |
| 5 | 328 | 5-card chain (rare) |
| 6 | 270 | 6-card single row (dense) |

> **Why x=90 and not centered?** Centering creates an inconsistent gutter between the title (anchored at 90) and the card row, breaking visual alignment across slides. The card row always shares the title's left edge.

**Production layout (when used on a slide — overrides native padding):**
| Property | Value | Notes |
|---|---|---|
| Card width | 547 px | Native, no resize |
| Padding horizontal (`PAD_X`) | 40 px | left = right |
| Padding top (`PAD_TOP`) | 36 px | |
| Padding bottom (`PAD_BOTTOM`) | 56 px | Intentionally larger than top — breathing room below body |
| Gap title → body (`GAP_TB`) | 12 px | |
| Title text auto-resize | `HEIGHT` (hug) | Width fixed to `547 − 2·PAD_X = 467 px` |
| Body text auto-resize | `HEIGHT` (hug) | Same fixed width |
| Card height | computed | `PAD_TOP + max(titleH) + GAP_TB + max(bodyH) + PAD_BOTTOM` across the row |

> Every card in a row gets the **same height** (the tallest card's computed height). Title and body inside each card stay at the same y so the row reads as a clean grid even when titles wrap to different line counts.

---

### Process Card — `3620:1243` (COMPONENT)

A Card Section with a directional arrow appended to the right. Represents one step in a process, pointing to the next.

| Property | Value |
|---|---|
| Node ID | `3620:1243` |
| Native size | 577 × 290 px |
| Card portion | 547 px wide |
| Arrow + gap | 30 px (12 gap + 18 arrow) |
| Gap after to next card | 12 px |

> Use this for every step **except the last** in a process sequence. The last step is always a plain `Card Section (Icon=true)`.

**Resize gotcha:** Process Card instances default to **HUG sizing horizontally** — calling `inst.resizeWithoutConstraints(418, h)` does nothing until you also set `inst.layoutSizingHorizontal = "FIXED"`. After resize, the inner Card Section's `Container` frame may still be sized for the native 547, so body text can clip on the right.

**The real text-reflow fix:** explicitly resizing the body text via `t.resize(innerW, ...)` often doesn't take effect on instance children (the inner auto-layout overrides it). Instead set **`body.layoutSizingHorizontal = "FILL"`** — the text then inherits its parent Container's width and reflows correctly. Re-write `t.characters = c + " "; t.characters = c;` afterward to force a layout pass.

**Before / After pairs (e.g. "current effort pattern" vs "target experience pattern"):** Stack two 4-step rows on one slide. Each row = 3 × Process Card + 1 × Card Section. Add a small label caption above each row (Equip Extended Medium 22pt, muted gray for "current", Petrol Black for "target"). Drop the Statement Bar — the pattern contrast is the takeaway.

---

### Conclusions / Statement Slide — `3705:722` (COMPONENT_SET)

A full-bleed dark slide used for short, declarative statements: a single big headline + one supporting paragraph. No cards, no diagrams. Use when the message is the slide — e.g. transition / manifesto / closing point.

| Variant | Node ID | Size | Use when |
|---|---|---|---|
| `Property 1=Default` | `3705:721` | 1920 × 1080 px | The only variant — dark teal gradient with scribble texture |

**Anatomy:**
- Background: dark teal gradient + scribble + tint (managed by inner `Layout` instance)
- Nagarro logo top-left at (84, 64)
- `quote-block` frame at **(90, 287)**, 1736 × 334 px, containing:
  - `quote` (TEXT, name) — the big white headline, 1736 × 192 px, large Equip Extended at 80pt+
  - `attribution` (TEXT, name) — supporting paragraph, sits at y=240 inside quote-block, 1736 × 94 px, lighter Equip Regular
- Footer instance at (84, 968) — populate the 3 cells (Digital Design Strategy / Project Name / Month Year)

**When to use this layout:**
- Manifesto / thesis / closing-statement slides — a single bold idea
- Section transitions where you want pause and emphasis
- "Method" or "Approach" framing slides between content blocks

> Examples: "Focused discovery. Evidence-led experience alignment." / "Connect can become the front door." / "We use available evidence … to build a practical recommendation."

**How to use (fetch + populate):**
```javascript
// 1. Fetch the variant directly (or .createInstance() on the component set)
const stmt = await figma.getNodeByIdAsync("3705:721");
const slide = stmt.clone();              // never edit the source
slide.x = slideIndex * 2020; slide.y = 0;
page.appendChild(slide);

// 2. Populate text by layer name
const quote       = findByName(slide, "quote");
const attribution = findByName(slide, "attribution");
await setText(quote, "Your big headline. Two short sentences.");
await setText(attribution, "One supporting paragraph that gives context and turns the headline into a takeaway.");

// 3. Footer (3 cells inside the Footer instance)
populateFooter(slide, ["Digital Design Strategy", "Project Name", "June 2026"]);
```

**Rules:**
- **Always fetch this component** for statement / conclusion / manifesto slides — do not recreate the dark gradient by hand.
- Quote text: keep it to **1–2 short sentences** (≤ ~12 words each). The font is 80pt+; long text wraps badly.
- Attribution text: **1 sentence**, ≤ 25 words. It's the "so what" of the headline.
- Do not add cards, diagrams, or additional content blocks to this layout. If you need supporting structure, use the `Content - Title + Body / Light` template instead.

---

### Statement Bar — `3718:1384` (COMPONENT_SET)

A full-width dark callout bar that closes a slide with one emphatic sentence — "Workshop decision: …", "Recommended first slice: …", "Output: …", "Result: …". Use it whenever a content slide ends with a single takeaway line that needs visual weight.

| Variant | Node ID | Size | Use when |
|---|---|---|---|
| `rows=1` | `3706:1375` | 1752 × 80 px | One short sentence (≤ ~110 chars) |
| `rows=2` | `3718:1385` | 1752 × 126 px | Sentence wraps to two lines |

**Anatomy:**
- Background: `#01070E` (Petrol Black, brand variable), border-radius **8 px**
- Padding: 24 top / 24 bottom / 10 left / 10 right (text auto-centers horizontally with ~183px effective margin)
- Text: `Equip Regular`, 24 pt, white, centered

**Anchor in a content slide:**
- Slide width 1920 → bar centered with 84 px slide-edge margin → x = **84**
- Vertical position: snap **above** the slide footer (which sits at y = 968). For a 1-row bar place at y ≈ 870, for 2-row place at y ≈ 824. If cards sit above it, set bar y = card.bottom + 32.

**How to use:**
```javascript
// Pick the variant by text length
const set = await figma.getNodeByIdAsync("3718:1384");      // COMPONENT_SET
const rows1 = set.defaultVariant ?? await figma.getNodeByIdAsync("3706:1375");
const inst = rows1.createInstance();
slide.appendChild(inst);
inst.x = 84; inst.y = 870;

// Set the sentence — find the single TEXT child
const t = inst.findOne(n => n.type === "TEXT");
await setText(t, "Workshop decision: pick one production slice, one user cohort, the systems involved, the first release boundary and the KPI baseline.");

// If it wraps, swap to rows=2
if (t.height > 40) {
  inst.setProperties({ rows: "2" });   // or recreate from variant 3718:1385
  inst.y = 824;
}
```

**Rules:**
- **Always fetch this component** — never recreate the dark bar with `createFrame` + manual fills. We did this on the Proof journeys slides and it's now retired.
- Sentence content: starts with a label-style lead-in ("Workshop decision:", "Recommended first slice:", "Output:", "Result:") followed by the takeaway. Keep it under ~30 words.
- Pick `rows=1` first; if the text wraps in the variant, switch to `rows=2`.
- One statement bar per slide max — it's a closing punctuation mark.
- Pair well with: card-row slides, before/after diagrams, framework slides. Don't pair with the Statement Slide (`3705:721`) — that layout already is the statement.

---

### Progress Banner — `3706:1378` (COMPONENT_SET)

A full-width dark banner showing a horizontal flow of **2–6 labels separated by chevrons**. Use it for stage-flow lines, process / phase / journey sequences, and architecture-layer pipelines that read as `A → B → C → …`. Sits at the top or middle of a content slide.

| Variant | Node ID | Size | Use when |
|---|---|---|---|
| `cols=2` | `3706:1373` | 1752 × 110 px | Two stages (e.g. *Before → After*) |
| `cols=3` | `3706:1377` | 1752 × 141 px | Three phases (e.g. *Discover → Define → Decide*) |
| `cols=4` | `3706:1376` | 1752 × 172 px | Four-layer architecture (e.g. *AEM → Context → API → Telemetry*) |
| `cols=5` | `3706:1374` | 1752 × 203 px | Five-step process |
| `cols=6` | `3706:1372` | 1752 × 265 px | Six-stage chain (e.g. *Identity → Role → Entitlement → Brand → Order → Action*) |

**Anatomy:**
- Background: `#01070E` (Petrol Black), border-radius **5 px**
- Layout: HORIZONTAL auto-layout, padding **24 top/bottom, 16 left/right**, itemSpacing **8 px**
- Children alternate: `col1`, `chevron-right` (24×24), `col2`, `chevron-right`, `col3`, …, `colN`
- Each `colN` is a TEXT layer, **Equip Regular 24pt white**, left-aligned, auto line-height
- Column heights grow with content — that's why the variant heights differ (cols=2 → 110, cols=6 → 265)

**Anchor in a content slide:**
- x = **84** (full slide-margin width = 1752)
- y depends on slide composition: pair with a title block above and optionally cards/diagram below. A common placement is y ≈ 410 when used as the main visual element of the slide.

**How to use:**
```javascript
const labels = ["Identity", "Role", "Entitlement", "Brand", "Project/order", "Next action"];
const variantId = {2:"3706:1373",3:"3706:1377",4:"3706:1376",5:"3706:1374",6:"3706:1372"}[labels.length];
const comp = await figma.getNodeByIdAsync(variantId);
const inst = comp.createInstance();
slide.appendChild(inst);
inst.x = 84; inst.y = 410;

// Populate each col-N text by name
for (let i = 0; i < labels.length; i++) {
  const t = inst.findOne(n => n.type === "TEXT" && n.name === `col${i+1}`);
  if (t) await setText(t, labels[i]);
}
```

**Rules:**
- **Always fetch this component** when a slide has a chevron-separated horizontal flow — do not draw the chevrons or the banner manually.
- Pick the variant by **stage count**. 7+ stages → break into two banners or rethink the slide; don't squeeze into cols=6.
- Each column label should be a **short noun phrase** (1–4 words). For longer per-stage descriptions, put them in cards *below* the banner — the banner is the spine, not the body.
- One progress-banner per slide. If you need a sub-process flow, use cards or numbered chips instead.
- Pairs well with: the Statement Bar (`3718:1384`) below, or a Card Section row above/below for per-stage detail.

---

### Table — `3734:2374` (COMPONENT_SET)

A structured data table with a header row and data rows separated by horizontal dividers. Variants cover **1–4 columns**; all variants ship with **8 data rows** (rows 5–8 hidden by default, 4 visible). Use for decision frameworks, feature matrices, comparison grids, or any structured multi-column data (e.g. ASSA ABLOY slides 11 and 20).

**Sub-component: TableItems — `3734:2120` (COMPONENT_SET)**

The reusable cell unit. Two variants, driven by the `type` property:

| Variant | Node ID | Typography | Use when |
|---|---|---|---|
| `type=table-title` | `3734:2119` | Equip Extended Regular, 24 px, `#010716`, line-height 32 px, letter-spacing −1 px | Header row cells — column labels |
| `type=table-item` | `3734:2118` | Equip Regular, 18 px, `#010716`, letter-spacing −0.36 px | Data row cells — body copy |

Cell padding: 8 px left. Width: 420 px (fixed). Height: hug content.

**Variants:**

| Variant | Node ID | Columns | Total row width | Use when |
|---|---|---|---|---|
| `cols=4` | `3734:2170` | 4 × 420 px | **1752 px** | Full-width table — fills the 1920 px slide with 84 px margins |
| `cols=3` | `3734:2375` | 3 × 420 px | **1308 px** | Three-column comparison or framework |
| `cols=2` | `3736:2415` | 2 × 420 px | **864 px** | Simple two-column side-by-side |
| `cols=1` | `3736:2455` | 1 × 420 px | **420 px** | Single-column list with dividers |

Column gap: **24 px** (0 px for `cols=1`). All variants: border-radius **8 px**, layout gap between rows **24 px**. Colours use design variables — switch automatically between light and dark mode.

**Row structure (same across all variants):**
- `top-table-row` — header row (`type=table-title` cells)
- `table-line` — horizontal rule divider
- `table-row` × 4 (visible) + `table-row` × 4 (hidden) — data rows (`type=table-item` cells)

**Anchor in a content slide:**
- `cols=4`: x = **84**, spans full content width
- `cols=3/2/1`: centre horizontally — `x = (1920 − totalRowWidth) / 2`
- y: place below title, typically y ≈ **280** when `content-title` is above

**How to use:**
```javascript
// 1. Pick variant by column count
const variantId = { 4: "3734:2170", 3: "3734:2375", 2: "3736:2415", 1: "3736:2455" }[colCount];
const comp = await figma.getNodeByIdAsync(variantId);
const table = comp.clone();
slide.appendChild(table);
table.x = colCount === 4 ? 84 : Math.round((1920 - colCount * 420 - (colCount - 1) * 24) / 2);
table.y = 280;

// 2. Populate header cells
const headerRow = table.findOne(n => n.name === "top-table-row");
const headerCells = headerRow.children.filter(n => n.name === "table-items" || n.type === "INSTANCE");
const headerLabels = ["Decision", "Examples", "Workshop question", "Owner"]; // adjust to colCount
for (let i = 0; i < Math.min(headerCells.length, headerLabels.length); i++) {
  const t = headerCells[i].findOne(n => n.type === "TEXT");
  if (t) await setText(t, headerLabels[i]);
}

// 3. Populate visible data rows (first 4)
const allRows = table.children.filter(n => n.name === "table-row");
const visibleRows = allRows.filter(n => n.visible).slice(0, 4);
const rowData = [
  ["Own in Connect/AEM",     "Top tasks, resource discovery", "What must feel native?",          "Product"],
  ["Deep-link with context", "Brand sites, webshops",         "What external tools need context?","Arch"],
  ["Federated identity",     "SSO, CSR impersonation",        "Who manages access rules?",        "Platform"],
  ["…",                      "…",                             "…",                                "…"],
];
for (let r = 0; r < visibleRows.length; r++) {
  const cells = visibleRows[r].children.filter(n => n.name === "table-items" || n.type === "INSTANCE");
  for (let c = 0; c < cells.length; c++) {
    const t = cells[c].findOne(n => n.type === "TEXT");
    if (t) await setText(t, rowData[r]?.[c] ?? "");
  }
}

// 4. To reveal extra rows (up to 8 total): unhide the hidden table-row + table-line pairs
const hiddenRows = allRows.filter(n => !n.visible);
// unhide as many as needed, then populate the same way as step 3
```

**Rules:**
- **Always fetch this component set** — never build a table manually with rectangles and text layers.
- **Pick the variant by column count.** Don't hide columns inside a wider variant.
- **Light and dark mode**: colours use design variables — no manual overrides needed.
- **Row count**: 4 visible rows by default (out of 8 total). To show more rows, unhide hidden `table-row` + `table-line` pairs in order. Maximum 8 data rows — if you need more, split across two slides.
- Keep header labels short (1–3 words). Body copy per cell: 1–2 lines max.
- Pairs well with `content-title` above and optionally a `Statement Bar` below for a closing takeaway.
- **Trigger this component** when slide content is a: decision framework, comparison grid, feature matrix, or any structured list that appeared as a table in the original source (PPT, doc, or brief).

---

### Table — `3734:2374` (COMPONENT_SET)

A multi-row, multi-column table for decision matrices, comparison grids, and tabular data. Use it whenever the source content reads as `Header row + N data rows × M columns` — never simulate a table with cards.

| Variant | Node ID | Size (native) | Use when |
|---|---|---|---|
| `cols=1` | `3736:2455` | 420 × 344 px | Single-column list with a heading |
| `cols=2` | `3736:2415` | 864 × 416 px | Two-column comparison |
| `cols=3` | `3734:2375` | 1308 × 416 px | Decision matrix (most common) |
| `cols=4` | `3734:2170` | 1752 × 416 px | Four-attribute breakdown |

**Cell component:** `table-items` (`3734:2120`)
- `type=table-title` (`3734:2119`) — header cell, 420×32, Equip Extended Regular 24pt
- `type=table-item`  (`3734:2118`) — data cell, 420×24, Equip Regular 20pt

**Anatomy:**
- Layout: VERTICAL auto-layout, itemSpacing **24 px** (compress to **12 px** if many rows)
- Children alternate: `top-table-row` (header, 32 px tall) → `table-line` (separator) → `table-row` (data, 48 px tall) → `table-line` → …
- Each row is a HORIZONTAL frame containing N `table-items` instances (one per column)
- **8 data rows are pre-baked** in the component; only the first 4 are visible by default. Show / hide rows by setting `.visible` to control row count.

**Anchor in a content slide:**
- x = **84** if using full content width (resize instance to 1752); otherwise center the native width
- y = **440** (clears subtitle); itemSpacing 12 keeps a 5-row table under the footer

**How to use:**
```javascript
const tableCols = { 1: "3736:2455", 2: "3736:2415", 3: "3734:2375", 4: "3734:2170" };
const cols = headers.length;                  // headers + dataRows[][]
const tbl = (await figma.getNodeByIdAsync(tableCols[cols])).createInstance();
slide.appendChild(tbl);
tbl.resize(1752, tbl.height);                 // optional: stretch to full content width
tbl.x = 84; tbl.y = 440;
tbl.itemSpacing = 12;                         // optional: tighter rows when 5+ data rows

const rows = tbl.children.filter(c => c.type === "FRAME" && (c.name === "top-table-row" || c.name === "table-row"));
const lines = tbl.children.filter(c => c.type === "VECTOR" && c.name === "table-line");

// Header
rows[0].visible = true;
const headerCells = rows[0].children.filter(c => c.type === "INSTANCE");
for (let i = 0; i < cols; i++) await setText(headerCells[i].findOne(n => n.type === "TEXT"), headers[i]);

// Data rows — make visible AND populate; hide the rest
const dataRows = rows.slice(1);
for (let r = 0; r < dataRows.length; r++) {
  if (r < dataRows[r] && r < data.length) {
    dataRows[r].visible = true;
    const cells = dataRows[r].children.filter(c => c.type === "INSTANCE");
    for (let i = 0; i < cols; i++) await setText(cells[i].findOne(n => n.type === "TEXT"), data[r][i]);
  } else {
    dataRows[r].visible = false;
  }
}
// Hide separator lines past the last visible data row
for (let i = 0; i < lines.length; i++) lines[i].visible = i < data.length;
```

**Rules:**
- **Always fetch this component** for any tabular content (decision matrices, comparison grids, attribute breakdowns). Do **not** simulate a table with 5+ cards.
- **Make rows visible explicitly** — only the first 4 data rows are visible in the native variant; setting `.visible = true` on the rest is required.
- For 5+ data rows, set `itemSpacing = 12` to keep the table under the footer (y=968).
- If the table content is the takeaway, **drop the Statement Bar** from that slide — tables don't need a closing punctuation line.
- Pair well with: a content slide template; not with statement slides or the Conclusions component.

---

### Card Section / Set of Cards — `3620:1204` (COMPONENT)

Three `Card Section (Icon=true)` instances in a horizontal row. The pre-built 3-card layout.

| Property | Value |
|---|---|
| Node ID | `3620:1204` |
| Native size | 1689 × 290 px |
| Gap between cards | 24 px |

---

## Slide Canvas

- **Frame size:** 1920 × 1080 px
- **Safe horizontal margin:** 120 px each side → content area = **1680 px wide**
- **Content top:** y = 160 px (below slide header)
- **Content bottom:** y = 960 px (above footer)

---

## Base Content Frames (clone, never recreate)

Cards and process steps are **dropped into a cloned template frame**, never onto a bare `figma.createFrame()`. The template owns the background, scribble, Nagarro logo, title/subtitle text styles, and footer — recreating those manually loses brand fidelity.

| Use case | Template frame | Node ID | Notes |
|---|---|---|---|
| Cards or process slide with title + supporting line | `Content - Title + Body / Light` | `3139:797` | Has `content-title` (64pt), `content-subtitle` (24pt), `body-block` (clear and replace with cards), `Footer` instance |

**Key inner layers (by name):**
- `content-title` — H1, Equip Extended, 64pt
- `content-subtitle` — supporting line, Equip Regular, 24pt
- `body-block` / `content-body` — placeholder body text; **clear it** before placing cards
- `Footer` — instance with 3 cells: "Digital Design Strategy" / project name / month year

**Anchor position (Content - Title + Body / Light):**
- `content-area` frame is anchored at **(x = 90, y = 164)** in slide coordinates.
- After cloning the template, explicitly set `contentArea.x = 90; contentArea.y = 164;` — the default template position can drift; pin it.
- This puts the H1 at y = 164, supporting line at y ≈ 260, leaving the rest of the slide for cards/diagrams.

---

## Title Anchor Per Layout

For every template, the title (or hero text) sits at a fixed slide-absolute position. After cloning a template, snap its title node / content-area to these coordinates so the deck reads consistently across slides. All values in 1920×1080 canvas coords.

| Template | Anchor node | x | y | w | h | Notes |
|---|---|---|---|---|---|---|
| Cover - Standard / Dark | `cover-title` | 84 | 436 | 1308 | 128 | 128pt; vertical-center band |
| Cover - Large Title, Mint / Dark | `cover-title` | 84 | 183 | 1386 | 512 | 256pt hero |
| Chapter Cover - Large Title Left, Number Right / Dark | `chapter-title` | 90 | 383 | 1308 | 512 | 256pt |
| Chapter Cover - Vertically Centered, Number Top / Dark | `chapter-title` | 84 | 507 | 1431 | 128 | 128pt; vertical-center |
| **Content - Title + Body / Light** | `content-area` | **90** | **164** | 1627 | 690 | H1 64pt inside |
| Executive Summary - 2 Col Wide, Title Top + Text Bottom / Light | `exec-title` | 86 | 201 | 797 | 80 | 80pt |
| Executive Summary - 2 Col Wide, Bottom Left / Light | `exec-title` | 84 | 386 | 1160 | 80 | 64pt; lower band |
| Executive Summary - 3 Col, Title as First Col / Light | `title` (frame) | 84 | 354 | 568 | 160 | Title sits as first column |
| Executive Summary - 3 Col, Title Above / Light | `exec-title` | 84 | 345 | 1751 | 80 | 64pt full width |
| A Note From Us - Title Top, Text Bottom Left / Light | `Header` frame | 0 | 0 | 1920 | 154 | Title inside header band |
| A Note From Us - Copy Bottom Left / Light | `note-title` | 84 | 386 | 1160 | 80 | 64pt; lower band |
| Highlights - Quote, Centered / Light | `quote` | 232 | 286 | 1308 | 384 | 96pt; centered |
| Highlights - Quote, Bottom Left / Light | `Header` frame | 0 | 0 | 1920 | 154 | Title inside header band |
| About Nagarro - Stats Bubbles, Full-Width Photo / Dark | `about-title` | 256 | 500 | 1408 | 80 | 80pt; mid-slide |
| About Nagarro - Headline + 3 Content Boxes / Light | `about-title` | 84 | 253 | 1752 | 160 | 64pt full width |
| Why Nagarro - Headline Top, 3 Col Body / Light | `why-title` | 84 | 259 | 1224 | 160 | 64pt |
| Why Nagarro - Headline + 2 Col Body / Light | `why-title` | 84 | 288 | 568 | 320 | 64pt; first column |
| Outro - Tagline + Logo / Dark | `outro-headline` | 230 | 460 | 568 | 160 | 64pt; vertical-center |

**How to apply:**
1. Clone the template frame.
2. Find the anchor node by name (`findByName(slide, "<anchor>")`).
3. Set its `x` and `y` to the values above.
4. Populate text content and footer as usual.

> If a template's anchor isn't listed here, run the position-scan snippet (find the largest TEXT node above y=540, or any frame named `content-area` / `title-block` / `Header`) and add the row.

**Workflow:**
1. `const base = await figma.getNodeByIdAsync("3139:797"); const slide = base.clone();`
2. Populate `content-title`, `content-subtitle`, and the 3 footer cells.
3. Clear the body placeholder text.
4. Place Card Section / Process Card instances at the coordinates in this doc.

---

## Process Slides

### Rule: Process Step Layout

For a process with **N steps**, place **(N − 1) Process Card** instances followed by **1 Card Section (Icon=true)**. The arrow on each Process Card points to the next step.

Inter-card rhythm: `[ProcessCard 577px] + [12px gap] + [ProcessCard 577px] + ...`

---

### 3-Step Process

**Card width:** 547 px (native, no resize needed)
**Total width:** 3 × 547 + 2 × 42 = **1725 px**
**Horizontal margins:** (1920 − 1725) / 2 ≈ **98 px**
**Vertical center:** y = (1080 − 290) / 2 = **395 px**

| Element | Type | x | y | w | h |
|---|---|---|---|---|---|
| Step 1 | Process Card | 98 | 395 | 577 | 290 |
| Step 2 | Process Card | 687 | 395 | 577 | 290 |
| Step 3 | Card Section Icon=true | 1276 | 395 | 547 | 290 |

> x offsets: 98 → 98+577+12=687 → 687+577+12=1276

---

### 4-Step Process

Scale all cards down so 4 steps fit the 1680 px content area.

**Formula:** 3 Process Cards (width `p`) + 1 Card Section (width `p − 30`) = 1680 px
→ `3×(p+12) + (p−30) = 1680` → **p = 418 px**, card portion = 388 px

**Total width:** 3 × (418+12) + 388 = **1678 px** ≈ 1680 px
**Horizontal margins:** (1920 − 1678) / 2 ≈ **121 px**
**Vertical center:** y = **395 px**

| Element | Type | x | y | w | h |
|---|---|---|---|---|---|
| Step 1 | Process Card (resized) | 121 | 395 | 418 | 290 |
| Step 2 | Process Card (resized) | 551 | 395 | 418 | 290 |
| Step 3 | Process Card (resized) | 981 | 395 | 418 | 290 |
| Step 4 | Card Section Icon=true (resized) | 1411 | 395 | 388 | 290 |

> x offsets: 121 → 121+418+12=551 → 551+418+12=981 → 981+418+12=1411

---

## Section Grid Slides

### Rule: Section Grid Layout

Section cards are arranged in a **2-row grid**. Column count = N/2.
Always use even numbers (4, 6, 8). Odd counts: drop to the next layout and add a divider or CTA card.

| Count | Columns | Rows | Card variant |
|---|---|---|---|
| 4 | 2 | 2 | Icon=true (828 × 290 px) |
| 6 | 3 | 2 | Icon=true (544 × 290 px) |
| 8 | 4 | 2 | Icon=false (402 × 194 px) |

**Row gap:** 20 px between rows
**Column gap:** 24 px between columns

---

### 4-Section Grid (2 × 2)

**Card width:** (1680 − 24) / 2 = **828 px**, height = 290 px
**Grid size:** 1680 × 600 px (2 × 290 + 20)
**x_start:** 120 px, **y_start:** (1080 − 600) / 2 = **240 px**

| Card | x | y | w | h |
|---|---|---|---|---|
| Card 1 | 120 | 240 | 828 | 290 |
| Card 2 | 972 | 240 | 828 | 290 |
| Card 3 | 120 | 550 | 828 | 290 |
| Card 4 | 972 | 550 | 828 | 290 |

---

### 6-Section Grid (3 × 2)

**Card width:** (1680 − 48) / 3 = **544 px** (≈ native 547), height = 290 px
**Grid size:** 1680 × 600 px
**x_start:** 120 px, **y_start:** **240 px**

| Card | x | y | w | h |
|---|---|---|---|---|
| Card 1 | 120 | 240 | 544 | 290 |
| Card 2 | 688 | 240 | 544 | 290 |
| Card 3 | 1256 | 240 | 544 | 290 |
| Card 4 | 120 | 550 | 544 | 290 |
| Card 5 | 688 | 550 | 544 | 290 |
| Card 6 | 1256 | 550 | 544 | 290 |

---

### 8-Section Grid (4 × 2)

**Card variant:** `Icon=false` (shorter, 194 px height)
**Card width:** (1680 − 72) / 4 = **402 px**, height = 194 px
**Grid size:** 1680 × 408 px (2 × 194 + 20)
**x_start:** 120 px, **y_start:** (1080 − 408) / 2 = **336 px**

| Card | x | y | w | h |
|---|---|---|---|---|
| Card 1 | 120 | 336 | 402 | 194 |
| Card 2 | 546 | 336 | 402 | 194 |
| Card 3 | 972 | 336 | 402 | 194 |
| Card 4 | 1398 | 336 | 402 | 194 |
| Card 5 | 120 | 550 | 402 | 194 |
| Card 6 | 546 | 550 | 402 | 194 |
| Card 7 | 972 | 550 | 402 | 194 |
| Card 8 | 1398 | 550 | 402 | 194 |

---

## Building Combinations in Figma (Plugin API)

```javascript
// Get components
const cardTrue  = await figma.getNodeByIdAsync('3620:1140'); // Icon=true
const cardFalse = await figma.getNodeByIdAsync('3620:1421'); // Icon=false
const procCard  = await figma.getNodeByIdAsync('3620:1243'); // Process Card

// Create and place an instance
function place(comp, frame, x, y, w, h) {
  const inst = comp.createInstance();
  frame.appendChild(inst);
  inst.x = x;
  inst.y = y;
  inst.resizeWithoutConstraints(w, h);
  return inst;
}

// Example: 3-step process
const frame = figma.createFrame();
frame.resize(1920, 1080);
place(procCard,  frame, 98,   395, 577, 290); // Step 1 (with arrow)
place(procCard,  frame, 687,  395, 577, 290); // Step 2 (with arrow)
place(cardTrue,  frame, 1276, 395, 547, 290); // Step 3 (no arrow)
```

---

## Card Row Builder — Hug Text + Match Tallest

The reusable pattern for **any 3/4/6 card row**: clone a base content template, place card instances, detach them so inner layers can be repositioned, force title + body to hug their content, then resize every card to the row's tallest height.

```javascript
// Grid alignment — card row starts at x=90 (matches title left edge), fills 1740 wide
const X_LEFT      = 90;
const CONTENT_W   = 1740;
const GAP_COL     = 24;
// Per-card width derived from column count: CARD_W = (CONTENT_W − (N−1) × GAP_COL) / N
// Constants (the production layout above)
const CARD_W      = 547;
const PAD_X       = 40;
const PAD_TOP     = 36;
const PAD_BOTTOM  = 56;
const GAP_TB      = 12;   // title → body
const GAP_COL     = 24;   // between cards in a row
const innerW      = CARD_W - 2 * PAD_X;

// 1) Preload fonts once
for (const [fam, st] of [
  ["Equip Extended","Medium"],
  ["Equip","Regular"],
]) await figma.loadFontAsync({ family: fam, style: st });

// 2) For each card instance: detach, set content, hug both texts
async function prepareCard(inst, titleText, bodyText) {
  const frame = inst.detachInstance();          // unlock inner layers
  const texts = [];
  (function walk(n){ if (n.type === "TEXT") texts.push(n); if ("children" in n && Array.isArray(n.children)) n.children.forEach(walk); })(frame);
  texts.sort((a,b) => (b.fontSize===figma.mixed?0:b.fontSize) - (a.fontSize===figma.mixed?0:a.fontSize));
  const [title, body] = texts;

  await setText(title, titleText);
  await setText(body,  bodyText);

  for (const t of [title, body]) {
    t.textAutoResize = "NONE";
    t.resize(innerW, t.height);
    t.textAutoResize = "HEIGHT";
    // Re-set characters to force a layout pass so .height is accurate
    const c = t.characters; t.characters = c + " "; t.characters = c;
  }
  return { frame, title, body };
}

// 3) After all cards prepared, resize each to the row's tallest height
const items = /* array of prepareCard results, in row order */;
const titleH = Math.max(...items.map(i => i.title.height));
const bodyH  = Math.max(...items.map(i => i.body.height));
const cardH  = PAD_TOP + titleH + GAP_TB + bodyH + PAD_BOTTOM;

const totalW = items.length * CARD_W + (items.length - 1) * GAP_COL;
const xStart = Math.round((1920 - totalW) / 2);

items.forEach(({ frame, title, body }, i) => {
  frame.resize(CARD_W, cardH);
  frame.x = xStart + i * (CARD_W + GAP_COL);
  // y is set by the slide layout
  title.x = PAD_X; title.y = PAD_TOP;
  body.x  = PAD_X; body.y  = PAD_TOP + titleH + GAP_TB;
});

async function setText(t, value) {
  if (t.fontName === figma.mixed) {
    for (let i = 0; i < t.characters.length; i++) await figma.loadFontAsync(t.getRangeFontName(i, i+1));
  } else { await figma.loadFontAsync(t.fontName); }
  t.characters = value;
}
```

**Why detach?** Figma blocks repositioning the inner layers of a live component instance (`This property cannot be overridden in an instance`). Detaching converts the instance into a regular frame whose children can be moved. Visual styling is preserved; only the component link is broken. This is acceptable because the source-of-truth styling lives in *this* doc — re-runs reproduce identical output from the same constants.

**Why re-set `.characters`?** Setting `textAutoResize = "HEIGHT"` doesn't always force an immediate reflow; reading `.height` can return the previous fixed height. Writing characters again (`c + " "` then `c`) triggers Figma's text engine to recompute, after which `.height` is accurate.

---

## Quick Reference

| Slide type | Component | Count rule | Variant |
|---|---|---|---|
| Process 3 | Process Card × 2 + Card Section × 1 | native 547px | Icon=true |
| Process 4 | Process Card × 3 + Card Section × 1 | resize to 418/388px | Icon=true |
| Sections 4 | Card Section × 4 | resize to 828px | Icon=true |
| Sections 6 | Card Section × 6 | resize to 544px | Icon=true |
| Sections 8 | Card Section × 8 | resize to 402px | Icon=false |

---

*Last updated: 2026-06-03 — added Table component (`3734:2170`)*
