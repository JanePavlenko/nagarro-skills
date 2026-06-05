# Creating New Slide Components — Brand-Aligned Composition Recipe

This is the **fallback playbook** for the figma-deck skill. Use it **only when**:
1. The slide's content shape doesn't fit any layout in [`layouts.md`](layouts.md), **and**
2. The content shape doesn't fit any atomic component in [`slide-components.md`](slide-components.md).

The recipe lets you compose something new without inventing brand. Every choice — color, font, size, padding, radius — must come from a token already defined in [`brand/design-system.md`](../../brand/design-system.md). **Nothing is improvised.**

---

## Step 0 — Try harder to use what exists

Before composing anything new, run through these checks:

- Does the content match a layout's slot contract if you rephrase the content? (e.g. a 5-row decision matrix → Table cols=3 with 3 columns + 5 rows; a 2-row sequence → Process Card flow)
- Does the content split across two slides cleanly? (e.g. 8 items → 4+4 in two consecutive Content slides)
- Does an atomic component handle the visual? (Card Section, Process Card, Progress Banner, Statement Bar, Table)

If yes to any of these, **stop** — use the existing pattern. The composition path below is the last resort.

---

## Step 1 — Anchor to the canvas

| Token | Value | Source |
|---|---|---|
| Slide canvas | 1920 × 1080 px (16:9) | design-system §5.1 (canonical is 1932×1080 — for Figma slides we use 1920) |
| Outer margin | **84 px** each side (160 in PowerPoint = 84 in Figma after the 1920 scale) | design-system §5.2 |
| Content area | `(84, 164)` to `(1836, 968)` → **1752 × 804 px** | derived from outer margin |
| Title anchor | `(90, 164)` (matches every title-on-top layout) | layouts.md anchors table |
| Footer band | `y = 968` (4-cell strip, 20 px tall labels) | layouts.md footer.* |
| Grid | 12 columns × 24 px gutters inside the content area | design-system §5.3 |
| Inter-block | 24–40 px related, 64–96 px between major sections | design-system §5.2 |

**Rule:** never start a new element outside the content area, and always snap left edges to a 12-column grid line. Column width = `(1752 − 11 × 24) / 12 ≈ 124 px`. Single column = 124, two = 272, three = 420, four = 568, six = 864.

---

## Step 2 — Use only token colors

From `brand/design-system.md` §1. Every color used in a new component **must** be one of these exact hexes — never "close" values.

| Use | Token | Hex |
|---|---|---|
| Default background | Pure White | `#FFFFFF` |
| Default text | Petrol Blue / Petrol Black | `#010716` |
| Secondary text / supporting | Nightfall Blue | `#13294B` |
| Muted text / captions | Nightfall Blue – Light | `#4E5E78` |
| Dominant accent | Mint Green | `#47D7AC` |
| Dark callout / CTA bar | Petrol Blue | `#010716` |
| Card fill (light) | Limestone Grey – Lightest | `#EFF1F4` |
| Card stroke / divider | Limestone Grey | `#C4C9D2` |
| Differentiation accents (charts, callouts) | Lavender Purple `#2E008B` / Sunset Pink `#F8485E` / Vanilla Yellow `#FBD872` | use sparingly |

**Hard rules:**
- White dominates (55% target).
- Mint Green is *the* accent — first choice for emphasis, CTAs, lead chart series.
- Do not introduce off-palette colors. Do not invert the ratio (no full-bleed Mint slides except approved covers/dividers).
- Dark text on light backgrounds, white text on dark. No mid-tone-on-mid-tone.

---

## Step 3 — Use only the type scale

From `brand/design-system.md` §2.3. Pick the closest tier for the role; never invent a size.

| Role | Font | Weight | Size (1920×1080) | Line height |
|---|---|---|---|---|
| Cover hero | Equip Extended | Bold | 96–130 pt | 1.0 |
| Slide H1 (section / divider) | Equip Extended | Bold | 56–64 pt | 1.05 |
| Slide H2 (most content titles) | Equip Extended | Medium | 40–48 pt | 1.1 |
| Subtitle / callout headline | Equip Extended | Medium | 28–32 pt | 1.15 |
| Lede / first body paragraph | Equip | Regular | 24–28 pt | 1.3 |
| Body | Equip | Regular | 18–20 pt | 1.4 |
| Caption / source | Equip | Regular | 12–14 pt | 1.4 |
| Footer | Equip | Medium | 10–11 pt | 1.3 |

**Hard rules:**
- `Equip Extended` for every headline; `Equip` for every body. Never cross the streams.
- No italics for emphasis — use Medium or Bold weight instead.
- No underlines (reserved for links).
- All-caps only for ≤ 3-word labels (eyebrow tags, badges).

---

## Step 4 — Re-use the rhythm of an existing layout

Before drawing, **find the closest existing layout** in `layouts.md` and copy its proportions:
- Same H1 anchor coordinate (usually `(90, 164)`)
- Same outer margin (84)
- Same inter-block spacing (24/32/40)
- Same corner radius (8 px on cards, 5 px on banners)
- Same icon proportions (80 × 80 px, sitting in a pill container)

This is the single biggest reason new components feel foreign — they have different rhythm than the rest of the deck. Mirror the rhythm and the new piece reads as a sibling, not a guest.

---

## Step 5 — Compose from atomic components first

When you do need to build, **always reach for an existing atomic component before drawing**:

| Atomic | Use for |
|---|---|
| **Card Section** (`3620:1244`, Icon=true/false) | Any title + body card. Already in `slide-components.md`. |
| **Process Card** (`3620:1243`) | A step in a sequence — has the arrow built in. |
| **Progress Banner** (`3706:1378`, cols=2..6) | Horizontal labeled flow. |
| **Statement Bar** (`3718:1384`, rows=1/2) | Single-sentence dark CTA / takeaway. |
| **Table** (`3734:2374`, cols=1..4) | Any tabular content. |
| **Conclusions slide** (`3705:721`) | Full-bleed statement / manifesto. |

Only fall through to **raw shapes (`createFrame` / `createRectangle`)** when none of the atomic components fit. When you do:
- Card fill: `#EFF1F4`, radius 8 px, padding 40 / 36 / 56 (X / top / bottom) — matches the Card Section production layout
- Dark callout: `#010716`, radius 5–8 px, padding 24 / 16 — matches the Statement Bar / Progress Banner
- Stat tile: number 96–130 pt Equip Extended Bold (`#010716`), label below 18–24 pt Equip Regular (`#13294B`)
- Icon pill: 100 × 100 px circle filled `#E0E3E8` (Limestone Grey – Lighter), icon centered inside at ~80 × 80

---

## Step 6 — Self-check before committing

Run this checklist mentally before adding the new component to the slide:

- [ ] Every color is in §1 of design-system.md.
- [ ] Every font + size is in §2.3 of design-system.md.
- [ ] Left edges snap to a 12-column grid line (84, 208, 332, 456, 580, 704, 828, 952, 1076, 1200, 1324, 1448).
- [ ] Padding values come from the rhythm set: 8, 12, 16, 24, 32, 40, 48, 56, 64.
- [ ] Corner radius is one of: 5 (banner), 8 (card), 100% (icon pill).
- [ ] No element extends past the safe area (84 / 84 / 84 / 84 margins).
- [ ] If the slide already has an existing layout's title, the new component sits **below the subtitle's bottom edge + 40 px** (no overlap).
- [ ] White dominates the slide overall; accent color used in 1–2 spots max.
- [ ] Spell-check: no placeholder text (`Lorem`, `Title`, `Body`, `Server`, `Your title goes here`).

If anything fails, fix before continuing.

---

## Step 7 — Promote useful new components back to the library

When a freshly-composed component ends up working well and might recur, **add it to `slide-components.md`** with the full spec (sizes, anchor, padding, fetch+populate code, rules). This keeps the catalog growing organically and prevents re-composing the same thing later.

---

## What this recipe is NOT

- Not permission to invent colors or fonts.
- Not permission to skip the catalog check.
- Not permission to draw a slide layout from scratch — slides always start from a cloned template (typically `Content - Title + Body / Light`, `3139:797`). The composition rules above apply to **components placed on a template**, not to the slide chrome itself.

If a slide truly needs a whole new layout (not a new in-slide component), **stop and flag it** — that decision belongs to the design director, not the model.
