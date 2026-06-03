# Nagarro Design System — Deck Foundations

This document encodes the parts of the **Nagarro Brand Design System (BDS)** that the **Designer** and **Design Director** agents must follow when producing presentation decks. Source: Figma file `Nagarro-BDS` (key `Mk0YPHbJMOg5qgIYVwgYIr`), pages "↳ ✅ Colors", "↳ ✅ Typography", "↳ ✅ Logo", "↳ ✅ Icons".

Status: **Foundations complete. Approved slide-layout catalog documented in §8 from `templates/powerpoint/nagarro-deck.pptx` (63 example slides, 1 master layout "DEFAULT").**

---

## 1. Colors

### 1.1 Primary brand colors
The two anchors of the brand. Always present in some form on every deliverable.

| Name | Hex | Token |
|---|---|---|
| Mint Green | `#47D7AC` | `color.mint-green` |
| Petrol Blue | `#010716` | `color.petrol-blue` |

> Note: In the BDS, **"Petrol Blue"** refers to the near-black anchor `#010716` (also labelled "Petrol Black" in the detailed usage chart). "Nightfall Blue" `#13294B` is a separate secondary color.

### 1.2 Secondary colors
Used in support of the primaries.

| Name | Hex | Token |
|---|---|---|
| Nightfall Blue | `#13294B` | `color.nightfall-blue` |
| Limestone Grey | `#C4C9D2` | `color.limestone-grey` |
| Lavender Purple | `#2E008B` | `color.lavender-purple` |
| Vanilla Yellow | `#FBD872` | `color.vanilla-yellow` |
| Sunset Pink | `#F8485E` | `color.sunset-pink` |

### 1.3 Neutrals

| Name | Hex | Token |
|---|---|---|
| Pure White | `#FFFFFF` | `color.pure-white` |

### 1.4 Extended palette (all shades)
Tints and shades for marketing variations. Always prefer the canonical color above; use extended shades for backgrounds, dividers, and supporting elements.

**Greens (Mint Green family)**
| Name | Hex |
|---|---|
| Mint Green – Darkest | `#205463` |
| Mint Green – Darker | `#2D807B` |
| Mint Green – Dark | `#3AAB94` |
| **Mint Green** | **`#47D7AC`** |
| Mint Green – Light | `#75E1C1` |
| Mint Green – Lighter | `#A3EBD5` |
| Mint Green – Lightest | `#D1F5EA` |

**Blues (Nightfall + Petrol)**
| Name | Hex |
|---|---|
| Petrol Blue (Black anchor) | `#010716` |
| **Nightfall Blue** | **`#13294B`** |
| Nightfall Blue – Light | `#4E5E78` |
| Nightfall Blue – Lightest | `#8893A5` |

**Greys (Limestone family)**
| Name | Hex |
|---|---|
| **Limestone Grey** | **`#C4C9D2`** |
| Limestone Grey – Light | `#D2D6DD` |
| Limestone Grey – Lighter | `#E0E3E8` |
| Limestone Grey – Lightest | `#EFF1F4` |

**Purples (Lavender family)**
| Name | Hex |
|---|---|
| **Lavender Purple** | **`#2E008B`** |
| Lavender Purple – Light | `#6240A8` |
| Lavender Purple – Lighter | `#9680C5` |
| Lavender Purple – Lightest | `#CBBFE2` |

Note: The Extended Colors page also labels two purple swatches as "Heather" and "Silver". Treat these as synonyms for the lighter end of the Lavender family until confirmed; prefer the `Lavender Purple – Lighter / Lightest` names.

**Yellows (Vanilla Yellow family)**
| Name | Hex |
|---|---|
| Vanilla Yellow – Darker | `#F99068` |
| Vanilla Yellow – Dark | `#FAB46D` |
| **Vanilla Yellow** | **`#FBD872`** |
| Vanilla Yellow – Light | `#FCE195` |
| Vanilla Yellow – Lighter | `#FCEBB8` |
| Vanilla Yellow – Lightest | `#FDF4DC` |

**Pinks (Sunset Pink family)**
| Name | Hex |
|---|---|
| Sunset Pink – Darkest | `#4C3150` |
| Sunset Pink – Darker | `#863854` |
| Sunset Pink – Dark | `#BF4059` |
| **Sunset Pink** | **`#F8485E`** |
| Sunset Pink – Light | `#F97586` |
| Sunset Pink – Lighter | `#FBA3AF` |
| Sunset Pink – Lightest | `#FCD0D7` |

### 1.5 Ideal color usage ratios
From the BDS "Ideal Colour Usage Ratios" charts. Use as the default proportion of each color on a slide deck overall (not necessarily per slide).

| Color | Hex | Share |
|---|---|---|
| Pure White | `#FFFFFF` | **55%** |
| Nightfall Blue | `#13294B` | 20% |
| Limestone Grey | `#C4C9D2` | 20% |
| Limestone Grey – Light | `#D2D6DD` | 2.5% |
| Mint Green | `#47D7AC` | 7.5% |
| Lavender Purple | `#2E008B` | 2.5% |
| Sunset Pink | `#F8485E` | 2% |
| Vanilla Yellow | `#FBD872` | 0.5% |
| Petrol Blue / Petrol Black | `#010716` | 0.5% |

Hard rule: **white dominates**. Color is used in punctuated, deliberate moments.

### 1.6 Color do's and don'ts
- ✅ Default deck background: **Pure White** `#FFFFFF`.
- ✅ Default text on white: **Petrol Blue / Petrol Black** `#010716` or **Nightfall Blue** `#13294B`.
- ✅ Use **Mint Green** as the dominant accent (CTAs, highlights, charts' lead series).
- ✅ Use **Lavender Purple, Sunset Pink, Vanilla Yellow** sparingly for differentiation in charts and infographics.
- ❌ Do not introduce colors outside this palette.
- ❌ Do not change hex values to "close" colors (no `#48D7AC`, `#011018`, etc.).
- ❌ Do not invert the ratios (e.g. full-bleed Mint Green slides) except for cover or section-divider slides where it's an approved layout.

---

## 2. Typography

### 2.1 Font families
The system uses two custom fonts in the Equip family. Both are referenced from the Typography page as downloadable.

| Family | Use |
|---|---|
| **Equip** | Body text, captions, supporting copy, footers. Regular proportion. |
| **Equip Extended** | Display, headlines, slide titles, section titles, cover titles. Wide proportion. |

> If `Equip` / `Equip Extended` are not available on the target system (e.g. when generating a `.pptx`), the Designer must report this as a `BLOCKER`. No silent substitution. An approved fallback (e.g. Arial / Helvetica) may be defined later but is not authorized yet.

### 2.2 Weights observed in the BDS
The typography page demos at least these weights:

- **Equip Extended:** Bold, Medium, Regular (Bold is the cover/H1 weight).
- **Equip:** Regular, Medium, Bold (Regular is the body default; Medium for emphasis).

### 2.3 Type scale for decks (16:9 / 1932×1080 px canvas)
Derived from the BDS demos and the supplied `nagarro-deck.pptx` template (slide size 20.125 × 11.25 in = 1449 × 810 pt = 1932 × 1080 px @ 96 DPI). Use this as the default scale; adjust proportionally for non-default canvases.

| Style | Font | Weight | Size | Line height | Use |
|---|---|---|---|---|---|
| Display / Cover title | Equip Extended | Bold | 96–130 pt | 1.0 | Cover slide hero title only |
| H1 / Slide title | Equip Extended | Bold | 56–64 pt | 1.05 | Section/divider slides |
| H2 / Slide title | Equip Extended | Medium | 40–48 pt | 1.1 | Most content slide titles |
| H3 / Subtitle | Equip Extended | Medium | 28–32 pt | 1.15 | Section subtitles, callout headlines |
| Lede / Intro body | Equip | Regular | 24–28 pt | 1.3 | First paragraph of a content slide |
| Body | Equip | Regular | 18–20 pt | 1.4 | Default body copy |
| Small / Caption | Equip | Regular | 12–14 pt | 1.4 | Footnotes, source attributions |
| Footer | Equip | Medium | 10–11 pt | 1.3 | Slide footers, page numbers |

> These size ranges are derived from the BDS Typography demo (1440-wide artboard) scaled to the 1932×1080 deck canvas used by `nagarro-deck.pptx`. Treat them as the authoritative scale.

### 2.4 Typography do's and don'ts
- ✅ Use **Equip Extended** for every headline.
- ✅ Use **Equip** for every body paragraph, bullet, caption, footer.
- ✅ Keep titles to one line where possible; wrap to two max.
- ❌ Don't mix Equip Extended into body copy or Equip into headlines.
- ❌ Don't use italics for emphasis — use Medium or Bold instead.
- ❌ Don't underline (reserved for hyperlinks).
- ❌ Don't use ALL CAPS except for very short labels (≤ 3 words).

---

## 3. Logo

### 3.1 Lockups (as supplied)
Two approved lockup orientations are supplied as SVG in `brand/logo/`. Use the orientation that fits the space; horizontal is preferred unless the layout is tall/narrow.

1. **Horizontal** — symbol on the left, "nagarro" wordmark to the right.
2. **Vertical** — symbol on top, "nagarro" wordmark below.

> A standalone **Symbol-only** mark and a **Symbol + wordmark + tagline** ("Thinking Breakthroughs") lockup are referenced in BDS principles but **not yet supplied as files** — see §9 Open items. Until they arrive, do not synthesize them.

### 3.2 Approved color modes (as supplied)
Each lockup is supplied in two color modes. In both modes the **symbol is always Mint** (`#47D7AC`); only the wordmark color changes.

| Mode | File suffix | Symbol | Wordmark | Use on |
|---|---|---|---|---|
| Light | `… Light.svg` | `#47D7AC` Mint | `#06041F` (near-black) | White / light backgrounds (default) |
| Dark | `… Dark.svg` | `#47D7AC` Mint | `#FFFFFF` White | Dark backgrounds (Nightfall, Petrol) |

> **Color note.** The wordmark dark in the supplied SVGs is `#06041F`, which is a different near-black than the Petrol Blue type token `#010716` (§1.1). Treat `#06041F` as the **logo-specific wordmark color** — do not recolor the supplied SVGs. Continue using `#010716` for body text and UI.
>
> A pure **Mono dark** (symbol + wordmark both `#06041F`) and pure **Mono light** (both white) are not in the supplied set — see §9 Open items.

### 3.3 Source files
Stored in `brand/logo/` (committed to the repo):

- `Nagarro Horizontal Light.svg`
- `Nagarro Horizontal Dark.svg`
- `Nagarro Vertical Light.svg`
- `Nagarro Vertical Dark.svg`

All four are 1024 × 768 SVGs with the logo centered. The Designer agent embeds these files directly in the `.pptx` — never redraws or recolors them.

### 3.4 Logo do's and don'ts
- ✅ Use one of the **four** supplied SVGs exactly as shipped. Pick by orientation × background.
- ✅ Maintain a clear-space margin around the logo equal to at least the height of the symbol.
- ✅ On white/light backgrounds use the `Light` variant; on Nightfall/Petrol/Mint backgrounds use the `Dark` variant.
- ❌ Don't recolor the symbol or wordmark. The Mint symbol stays Mint in both modes — it is intentional.
- ❌ Don't stretch, skew, rotate, or recompose the lockup. Use SVG; don't rasterize to a smaller-than-needed PNG.
- ❌ Don't add effects (shadows, glows, outlines).
- ❌ Don't crop, partially obscure, or place over busy imagery.
- ❌ Don't substitute the Petrol Blue type token `#010716` for the logo wordmark; use the file as supplied (`#06041F`).

### 3.5 Footer placement on slides
- Default: bottom-left or bottom-right corner of every content slide.
- Default size: ~36–56 pt symbol height for the 1932×1080 canvas, with at least 48 px of clear space from the edge.
- Variant: use `Light` on white/Limestone slides; use `Dark` on Nightfall/Petrol/Mint slides.

---

## 4. Iconography

### 4.1 Style
The Nagarro icon set has a single, distinctive style:

- **Hand-drawn / sketchy line art.** Loose, organic strokes — *not* geometric or grid-perfect.
- **Single-color stroke** in **Petrol Blue / Nightfall Blue** (`#010716` or `#13294B` depending on container).
- **No fills** — purely line work.
- **Container:** each icon sits inside a soft **circular pill** background, typically **Limestone Grey – Lighter** (`#E0E3E8`) or **Lightest** (`#EFF1F4`).
- **Frame size in BDS:** 100 × 100 px per icon (with the circle filling that frame).
- **Stroke weight:** medium-heavy (~3–4 px at 100 px frame size) with rounded caps/joins.

### 4.2 Available icons (60 files supplied)
All icons are stored as PNG in `brand/assets/icons/`. Use these exact filenames (without `.png`) when referencing an icon in a brief.

People & motion — `User`, `People`, `Person Upside Down`, `Dance`, `Sprint`, `Problem`, `Heart`, `Iterate`, `Loop`, `Tornado`, `Spring`

Abstract / patterns — `Stack`, `Waves`, `ZigZag`, `Path`, `Hop`, `Map Pin`, `Goal`

Workspace — `Presentation`, `Presentation (long)`, `Sketch`, `Shapes`, `Storyboard`, `Matrix`, `Affinity Map`

Environment — `Cloud`, `Cloud Lightning`, `Compass`, `Hurdle`, `Stadium`, `Factory`, `Building`, `Leaf`

States & symbols — `Checkmark`, `Checkmark-1` (alt variant), `Eye`, `Search`, `Lock (Locked)`, `Lock (Unlocked)`, `Sparkle`

Brand / tech — `Apple`, `Apple broadcast`, `Video`, `TV (ON)`, `TV (OFF)`, `Phone (ON)`, `Phone (OFF)`, `Phone (OFF)-1` (alt variant), `Dice`, `Data base`, `Api`, `Gauge`, `Shield`

Movement / location — `Road`, `Car`

Finance — `Dolar`, `Euro +`, `Euro -`

Charts — `Chart Upward`, `Chart Downward`

> Notes on the supplied set:
> - `Checkmark-1.svg` and `Phone (OFF)-1.svg` are alternate variants of `Checkmark.svg` and `Phone (OFF).svg`. Prefer the unsuffixed file unless a brief specifies otherwise.
> - An `Impact` highlight icon is referenced in the BDS but was **not** included in the supplied set — see §9 Open items.

### 4.2.1 Actual file colors (verified)
Every supplied SVG uses exactly two colors, matching §4.1:
- **Pill background:** `#E0E3E8` (Limestone Grey – Lighter)
- **Stroke / line art:** `#13294B` (Nightfall Blue)

The Designer agent must use these files as supplied — do not recolor.

### 4.2.2 Source files
Files in `brand/assets/icons/`. Preserve each file's native aspect ratio when placing in a slide.

### 4.3 Iconography do's and don'ts
- ✅ Use only icons from the BDS Icons page. Do not import from other libraries (Material, Carbon, Font Awesome, etc.).
- ✅ Keep the hand-drawn, sketchy style — even at small sizes.
- ✅ Pair with the pill container at the same proportion (~80% icon, ~10% padding each side).
- ✅ Use Petrol Blue / Nightfall Blue strokes by default. On dark backgrounds, invert to white strokes on a darker pill.
- ❌ Don't recolor the stroke to brand accent colors (Mint, Pink, etc.) — they stay dark.
- ❌ Don't redraw or simplify icons. Don't replace with a more geometric equivalent.
- ❌ Don't mix icon styles within a deck.

---

## 5. Slide canvas & spacing

### 5.1 Canvas
- **Default canvas:** 1932 × 1080 px (16:9), which is **20.125 × 11.25 in** = **1449 × 810 pt** in PowerPoint.
- Set in PowerPoint via slide size = Width 20.125 in, Height 11.25 in (not the default 13.333 × 7.5).
- This is the canvas of the supplied `templates/powerpoint/nagarro-deck.pptx`. All decks must inherit it.

### 5.2 Safe area & padding (measured against `nagarro-deck.pptx`)
- **Outer margin:** **160 px** (≈ 1.67 in / 120 pt) from each edge on standard content slides. Footer strip uses the bottom 64 px of that margin.
- **Cover hero block:** title and subtitle sit inside the same 160 px outer margin; the cover allows a taller title block that extends across the safe area.
- **Inter-block spacing:** 24–40 px between related blocks; 64–96 px between major sections of a slide.

### 5.3 Grid
- Use a **12-column grid** with 24 px gutters within the safe area (1612 px content width ÷ 12 = ~134 px columns + gutters). The template's content shapes align to this grid; the Designer must too.

---

## 6. Imagery & illustration

> **Status:** v1 rules drafted from Nagarro's public brand expression. Refine when a formal BDS Photography page is supplied.

### 6.1 Subject & narrative
- ✅ **Human-centered.** People doing real work — collaborating at a screen, sketching on a wall, building something. Not isolated tech screenshots.
- ✅ **In context.** Real workplaces, real moments, environmental crops that show "where" as well as "who".
- ✅ **Visibly diverse teams** across geography, age, gender, and ethnicity. Nagarro's positioning ("Many nations. One Nagarro.") requires this in every people shot.
- ❌ No staged "stock-photo" smiling at the camera; no posed handshakes; no generic suit-and-laptop tropes.
- ❌ No city-skyline cutaways, no abstract code-rain, no Earth-from-space metaphors.

### 6.2 Lighting & color treatment
- ✅ Natural light or soft warm key light. Slight underexposure preferred over flat over-lit shots.
- ✅ Keep natural color. No global filter, no duotone, no tinting toward brand colors.
- ❌ Don't apply Mint or Pink color casts to photos. Brand color shows up around the photo (frame, callouts), not inside it.

### 6.3 Composition
- ✅ Leave **at least 30% negative space** on hero images that will carry overlay text.
- ✅ Crops: medium-tight portrait or wide environmental. Avoid extreme close-ups of single faces.
- ✅ Subject placed on a third, not centered, when overlay text is planned.
- ✅ When text overlays an image, apply a **Petrol Black `#010716` linear gradient** from the text side (`0%` opaque) to `60%` opacity at the image's far edge.

### 6.4 Aspect ratios & resolution (for the 1932 × 1080 deck canvas)
- **Hero / full-bleed:** 16:9, minimum **1932 px wide** native (avoid upscaling).
- **Half-slide / column image:** 4:3 or 3:2, minimum **960 px wide**.
- **Inset / portrait:** 4:5, minimum **640 px wide**.
- **Avatar / circle crop:** 1:1, minimum **320 px wide**.
- General rule: source at **2×** the final placement size; export to JPEG (`quality 85`) for photos, PNG for graphics with transparency.

### 6.5 Pairing with brand elements
- ✅ Photo + Mint accent (a thin Mint rule, a Mint icon-pill, a Mint CTA) — preferred combination.
- ✅ Photo + Nightfall Blue text overlay on white margin — preferred for hero quotes over imagery.
- ❌ Don't place brand icons (`brand/assets/icons/*`) directly on top of photos; icons live on white / Limestone backgrounds.
- ❌ Don't use a photo as the background of a slide that already has a chart, table, or diagram. One visual idea per slide.

### 6.6 Illustration
- Beyond the BDS icon set (§4), Nagarro does not use a separate illustration style today. If a slide needs an illustrated metaphor, **compose it from the existing icon library** (icons on a circle, connected with thin Nightfall Blue lines) rather than introducing a new illustration style.

### 6.7 Charts & data visualization
Derived from the diagram, stat-tile, and roadmap slides in `nagarro-deck.pptx` (S37 roadmap, S38 SLA table, S43–S46 phase tables, S60 stat tiles). All charts use the same palette and typography as the rest of the deck.

**Series color order** (use in this sequence for the 1st, 2nd, 3rd … data series — never skip ahead):
1. Mint Green `#47D7AC`
2. Nightfall Blue `#13294B`
3. Lavender Purple `#2E008B`
4. Sunset Pink `#F8485E`
5. Vanilla Yellow `#FBD872`
6. Limestone Grey `#C4C9D2`

**Canvas & gridlines**
- Plot background: Pure White `#FFFFFF`.
- Gridlines: Limestone Grey – Lightest `#EFF1F4`, 1 px, horizontal only (no vertical gridlines on bar/line charts).
- Axes: 1 px Nightfall Blue `#13294B`; tick marks omitted.

**Typography in charts**
- Chart title: Equip Extended Medium, 24–32 pt, `#010716`.
- Axis labels: Equip Regular, 12–14 pt, `#13294B`.
- Data labels (on bars/lines/slices): Equip Medium, 14–18 pt, `#010716`.
- Legend: Equip Regular, 12–14 pt, `#13294B`, placed top-left or top-right (never below the chart).

**Chart-type rules**
- **Bar / column:** 2 px rounded top corners; no border; no shadow; gap between bars = 40% of bar width.
- **Line:** 3–4 px stroke; rounded caps and joins; data points as filled 8 px circles only if the line has ≤ 12 points.
- **Area:** 3 px stroke + 20%-opacity fill of the same color.
- **Pie / donut:** donut only (no pie); inner radius = 60% of outer; segments in series order above; never more than 5 segments — anything beyond merges into "Other" in Limestone.
- **Stat tile (like S60):** big number in Equip Extended Bold 96–130 pt (`#010716`), label below in Equip Regular 18–24 pt (`#13294B`). Stat tiles stack horizontally up to 5-across (see archetype A34).

**Hard don'ts**
- ❌ No 3D charts, no shadow effects, no bevels, no gradients on bars/lines/slices.
- ❌ No off-palette colors (e.g. PowerPoint's default blue/orange theme).
- ❌ No data tables embedded inside a chart; if a table is needed, use archetype A27 (SLA / table) instead.

---

## 7. PowerPoint mapping

Each foundation element maps to PowerPoint as follows when the Designer agent builds a `.pptx`:

| Foundation | PowerPoint mechanism |
|---|---|
| Colors | Theme color scheme: set Background 1 = `#FFFFFF`, Text 1 = `#010716`, Accent 1 = `#47D7AC` (Mint), Accent 2 = `#13294B` (Nightfall), Accent 3 = `#2E008B` (Lavender), Accent 4 = `#F8485E` (Pink), Accent 5 = `#FBD872` (Yellow), Accent 6 = `#C4C9D2` (Limestone). |
| Typography | Theme fonts: Headings = `Equip Extended`, Body = `Equip`. Type scale enforced via slide-master placeholders matching the table in §2.3. |
| Logo | Embedded as picture in the slide master footer (one per color mode); never re-typed. |
| Icons | Embedded as PNG/SVG image instances pulled from the BDS Icons page; never replaced by built-in PowerPoint icons. |
| Canvas | Slide size = 20.125 in × 11.25 in (1932 × 1080 px @ 96 DPI). Set explicitly when starting from scratch; inherited automatically when opening `templates/powerpoint/nagarro-deck.pptx`. |
| Slide master | Single layout named `DEFAULT` is used by every slide in the template. New slides must be created as **clones of an existing example slide** in the template, then their content swapped — not as new slide-layout objects. |

The Designer agent must NOT create new slide-master layouts. It only **duplicates an existing example slide from `nagarro-deck.pptx`** that matches one of the archetypes in §8, and replaces text/image content. See §8 for the catalog of archetypes and their reference slide numbers.

---

## 8. Slide layouts (archetype catalog)

The template (`templates/powerpoint/nagarro-deck.pptx`) uses **one slide-master layout** (`DEFAULT`) but ships with **63 fully designed example slides**. These example slides — not the layout — are the source of truth. The Designer **clones an example slide and swaps content**; it never invents new layouts.

### 8.0 Standard footer strip (present on most content slides)
Most content slides carry a 4-element footer (named exactly so the Designer can target them):

- `Digital Design Strategy` — left of footer, document/strategy name
- `Project Name` — center-left
- `Month Year` — center-right
- `2026` (rendered as "© 2026") — right edge

When a slide is a **chapter divider**, it also contains a `Chapter number` shape (e.g. "01", "02").
When a slide is **full-bleed** (cover, hero quote, image-led, big-stat), the footer strip is **omitted** — the slide uses the full canvas. (Slides without the footer strip: S1, S7, S9, S19, S33, S35, S37, S38, S39, S48, S50, S51, S54.)

### 8.1 Archetype catalog
Each archetype lists: **name** — purpose — **reference slide(s)** in the template — required shapes.

#### Cover & section
| # | Name | Purpose | Ref slide(s) | Required shapes |
|---|---|---|---|---|
| A1 | **Cover** | Deck opener | **S1** | `Background`, `Title`, `Subititle`, `Project Name`, `Month Year`, `2026` |
| A2 | **Chapter / Section Divider** | Marks a new section | **S6, S12, S15, S27, S32, S40, S47, S53, S56, S58** | Standard footer + section `Title` + `Chapter number` (e.g. "01") |
| A3 | **Closing / Thank-You** | Last slide of the deck | **S63** | Background + closing line ("We help some of the world's best brands…") + decorative frame |

#### Front matter
| # | Name | Purpose | Ref slide(s) | Required shapes |
|---|---|---|---|---|
| A4 | **Index / Table of Contents** | Numbered list of all chapters | **S2** | `Index Items Group` + repeating `{Number, Title, Description}` rows (up to 10) + `Title` ("Index") |
| A5 | **Confidentiality Statement** | Legal / NDA boilerplate | **S3** | Standard footer + `Confidentiality Statement` title + `copy` paragraph |
| A6 | **Executive Summary** | Single-page strategic summary | **S4** | Standard footer + `Executive Summary` title + `copy` paragraph |

#### Statement & intro
| # | Name | Purpose | Ref slide(s) | Required shapes |
|---|---|---|---|---|
| A7 | **Section Intro** | Title + subtitle + body | **S5, S13, S18, S24, S25, S26** | Standard footer + section title + optional subtitle + `copy` |
| A8 | **Big Statement / Hero Quote** | Full-bleed pull quote | **S7, S51** | Background (no footer) + large quote/statement text (and optional caption) |

#### Multi-column copy
| # | Name | Purpose | Ref slide(s) | Required shapes |
|---|---|---|---|---|
| A9 | **3-column copy block** | Three peer points/pillars | **S14, S16, S23, S41** | Standard footer + title + 3 × `copy` blocks (optionally each with its own `Title`) |
| A10 | **4-column "Why X" grid** | Four reasons / value props | **S8** | Standard footer + title + 4 × `copy` blocks |
| A11 | **Multi-block principles grid (6–12)** | Dense grid of named principles | **S30** | Standard footer + title + N × `{Title, copy}` pairs |
| A12 | **Numbered list with descriptions** | Ordered list, 6–8 rows | **S31** | Standard footer + `Index Items Group` + repeating `{List Number, Title, copy}` rows |
| A13 | **Mission / about statement** | 2-paragraph narrative | **S59, S61** | Standard footer + title + 2–3 paragraph blocks |

#### Layered / tiered structures
| # | Name | Purpose | Ref slide(s) | Required shapes |
|---|---|---|---|---|
| A14 | **Layered stack (5 levels)** | Hierarchical system architecture | **S11, S17, S29** | Title + subtitle + 5 × `{Level Title, copy}` rows (top to bottom) |
| A15 | **3-tier categorization (Fixed / Configurable / Temporary)** | Categorize by stability | **S19** | `graph` (background) + 3 named tiers, each with sub-bullets + summary title and copy (no footer) |

#### Diagrams & charts
| # | Name | Purpose | Ref slide(s) | Required shapes |
|---|---|---|---|---|
| A16 | **Spectrum / triangle diagram** | Two extremes with middle position | **S9** | `graph` shape + 3 callouts ("too rigid" / "governed flexibility" / "too fragmented") + title + body |
| A17 | **2×2 strategic matrix** | Quadrant analysis | **S10, S22** | `graph` + 4 quadrants, each with `{Title, copy}` + axis labels + title + body |
| A18 | **Process / pipeline flow** | Linear N-step process | **S20, S21** | Group container + N labeled nodes connected linearly + title + body |
| A19 | **System architecture map** | Multi-layer system diagram | **S28, S42** | Multiple grouped frames + many named nodes (Design Layer, Token Transformation, etc.) + title |

#### 3-phase deep-dive (Discover / Specify / Build)
| # | Name | Purpose | Ref slide(s) | Required shapes |
|---|---|---|---|---|
| A20 | **3-phase overview** | Side-by-side comparison of all 3 phases | **S43** | Title + 3 phase columns, each `{Phase Name, copy, How AI Accelerates, Tools, Transformation stat}` |
| A21 | **Single-phase deep dive** | One phase in detail | **S44 (Discover), S45 (Specify), S46 (Build)** | Phase name + body + `Traditional Challenges` + `How AI Accelerates` + `Top tools` + `Impact and Benefits` + `Transformation` stat |

#### Timelines & roadmaps
| # | Name | Purpose | Ref slide(s) | Required shapes |
|---|---|---|---|---|
| A22 | **Gantt-style weekly timeline (4 weeks)** | Workshops/discovery weeks | **S33** | Background (no footer) + `W 00…W 04` headers + grid of `Project Kick-Off`-style task bars + phase label |
| A23 | **Horizontal week timeline (8 weeks)** | Mid-range delivery view | **S34** | Standard footer + `timeline layout` + `content` + `Week 1…Week 8` headers + task rows |
| A24 | **Horizontal day timeline (5 days)** | Kick-off / sprint week | **S35** | Background (no footer) + `Timeframe` + `Timeline` track + `Day 1…Day 5` headers + task labels |
| A25 | **Milestone outputs grid** | Many deliverables in matrix | **S36** | Standard footer + title + grid of ~21 × `copy` cells |
| A26 | **Quarterly PI roadmap (Build vs Run)** | Multi-quarter capability roadmap | **S37** | Multiple `Frame` groups (no footer) + quarter labels (e.g. JAN–MAR) + PI sections + RUN/Build labels |

#### Tables & SLAs
| # | Name | Purpose | Ref slide(s) | Required shapes |
|---|---|---|---|---|
| A27 | **SLA / Priority table** | Priority × Response × Resolution | **S38** | `Line` separators + 4 priority rows × (`Description`, `Response time`, `Resolution time`) (no footer) |
| A28 | **AMS / service matrix** | Service-type matrix with In/Out scope | **S39** | `Frame` container + columns for Support / Enhancements / Hours / In-scope / Out-of-scope (no footer) |

#### Brand, partners, testimonials
| # | Name | Purpose | Ref slide(s) | Required shapes |
|---|---|---|---|---|
| A29 | **Logo wall** | Up to ~10 client/partner logos | **S48, S49** | Title + subtitle + grid of placeholders/`Title` shapes for each logo |
| A30 | **Capability cloud** | Many capability/category labels visually grouped | **S50** | Group container (no footer) + headline + ~15–20 short capability labels |
| A31 | **Testimonials wall** | Multiple quotes side-by-side | **S52** | Standard footer + title + 2 × `right-content` columns of `copy` blocks |

#### Case studies
| # | Name | Purpose | Ref slide(s) | Required shapes |
|---|---|---|---|---|
| A32 | **Case study summary card** | Short, scannable summary with tags | **S54** | `Main Container` + `Summary`, `Section Heading`, 3 × `Tag Name`, `Our Solution Header`, body sections (no footer) |
| A33 | **Case study deep-dive** | Long-form: Context / Solution / Outcome | **S55, S57** | Standard footer + 2 columns (left = expertise items, right = Business Context / Our Solution / Business Outcome blocks) |

#### About Nagarro
| # | Name | Purpose | Ref slide(s) | Required shapes |
|---|---|---|---|---|
| A34 | **Company stats** | Big-number stats (Years/Customers/Countries/People/NPS) | **S60** | Standard footer + headline + 5 × `{big number, label}` (e.g. 18 Years, 1000 Customers, 38 Countries, 17500 People, 62 NPS) |
| A35 | **Global presence** | Map / manifesto headline | **S62** | Standard footer + `Frame` (map graphic) + headline ("No single HQ Many nations…") |

### 8.2 Layout-selection rules (Designer must follow)

1. Always start from the **closest archetype** in §8.1. Duplicate that example slide in the template, then replace text and image content.
2. **Never invent a new layout.** If content does not fit any archetype, list it under `OPEN QUESTIONS` in the Draft artifact and use the closest match.
3. The **standard footer strip** (§8.0) must remain on every content slide. Only full-bleed archetypes (A1, A8, A15, A22, A24, A26, A27, A28, A30, A32) may omit it.
4. **Cover (A1)** is always slide 1.
5. **Chapter dividers (A2)** must precede every major section. Number them sequentially (`01`, `02`, …) in the `Chapter number` shape.
6. **Index (A4)** comes right after the Cover when the deck has ≥ 3 chapters.
7. **Confidentiality (A5)** is mandatory on **external** (client / RFP) decks; optional on internal decks.
8. **Closing (A3)** is always the last slide.

### 8.3 Recommended deck skeleton (external / client deck)
1. Cover (A1)
2. Index (A4)
3. Confidentiality (A5)
4. Executive Summary (A6)
5. Chapter Divider (A2) — "01"
6. … content slides drawn from A7–A35 …
7. Chapter Divider (A2) — "02"
8. … content slides …
9. About Nagarro section: chapter divider + A13 + A34 + A35
10. Closing (A3)

---

## 9. Open items

- [ ] **Imagery v1 → BDS confirmation.** §6 contains v1 rules drafted from public Nagarro brand expression. Replace with the official BDS Photography page when supplied.
- [ ] **Charts v1 → BDS confirmation.** §6.7 derives series colors and chart-type rules from the template's diagrams and palette ratios. Confirm with brand if an explicit data-viz spec exists.
- [ ] Confirm meaning of "Heather" and "Silver" purple labels — synonyms or separate colors?
- [ ] Additional deck templates beyond `nagarro-deck.pptx` (e.g. a dedicated RFP template, internal template) if/when provided. Today there is **one** approved template.
- [ ] **Logo: Symbol-only lockup** (interlocking double-ellipse mark, no wordmark) — not yet supplied as SVG.
- [ ] **Logo: Symbol + wordmark + "Thinking Breakthroughs" tagline lockup** — not yet supplied as SVG.
- [ ] **Logo: pure Mono dark** (symbol + wordmark both `#06041F`) and **pure Mono light** (both white) — not yet supplied; today both supplied variants keep the symbol Mint.
- [ ] **Logo wordmark color reconciliation:** supplied SVGs use `#06041F`, while the BDS Petrol Blue type token is `#010716`. Confirm with brand which value is canonical for the logo, and whether the type token should be aligned.
- [ ] **Icon: `Impact`** — referenced in the BDS but not included in the 60 supplied SVGs. Request the source file or confirm it's intentionally retired.

---

## 10. Source references

- Figma file: `Mk0YPHbJMOg5qgIYVwgYIr` (Nagarro-BDS)
- Pages used:
  - `↳ ✅ Colors` (node `63:242`)
  - `↳ ✅ Typography` (node `147:214`)
  - `↳ ✅ Logo` (node `163:225`)
  - `↳ ✅ Icons` (node `1202:733`)
- PowerPoint template: `templates/powerpoint/nagarro-deck.pptx` (63 example slides, 1 master layout `DEFAULT`, canvas 20.125 × 11.25 in).
- Fonts: `brand/fonts/Equip/` (16 styles) and `brand/fonts/Equip-Extended/` (16 styles). All 32 also installed in `~/Library/Fonts/` so PowerPoint resolves `Equip` / `Equip Extended` natively.
- Logo SVGs: `brand/logo/Nagarro {Horizontal|Vertical} {Light|Dark}.svg` (4 files).
- Icons: `brand/assets/icons/*.png` — background PNGs also at `brand/assets/nagarro-bg-dark.png` and `brand/assets/nagarro-bg-light.png`.
- Local cached screenshots: `brand/.figma-cache/*.png` (gitignored).
