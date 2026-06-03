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

**Anatomy:**
- Background: `#eff1f4`, border-radius 8px, padding 8px × 27px
- Icon: 80 × 80 px (top)
- Title: 34px Equip Extended Medium, `#010716`
- Body: 20px Equip Regular, `#535457`, line-height 1.4

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

## Quick Reference

| Slide type | Component | Count rule | Variant |
|---|---|---|---|
| Process 3 | Process Card × 2 + Card Section × 1 | native 547px | Icon=true |
| Process 4 | Process Card × 3 + Card Section × 1 | resize to 418/388px | Icon=true |
| Sections 4 | Card Section × 4 | resize to 828px | Icon=true |
| Sections 6 | Card Section × 6 | resize to 544px | Icon=true |
| Sections 8 | Card Section × 8 | resize to 402px | Icon=false |

---

*Last updated: 2026-06-03*
