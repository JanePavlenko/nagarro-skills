# Index Slide

## Overview
The table of contents slide. Normally the second slide in every deck. Lists all major sections with their numbers. Four layout variants depending on item count and desired visual style.

## Template file
`templates/powerpoint/presentations-skill.pptx`

---

## Variants

### Variant 1 — Index / List (Slide 03)
Up to 9 items in a single vertical list. Number on the left, title on the right. "Index" label sits left-mid.

| Shape name | Content |
|---|---|
| `index-title` | "Index" (label, do not change) |
| `item-1-number` … `item-9-number` | Section numbers: "01", "02" … |
| `item-1-title` … `item-9-title` | Section titles |

---

### Variant 2 — Index / List + Page Numbers (Slide 04)
Up to 4 items in a large-text list. Each item shows title on the left and page number on the right. Used when sections are few and page refs matter.

| Shape name | Content |
|---|---|
| `index-title` | "Index" |
| `item-1-title` … `item-4-title` | Section titles |
| `item-1-page` … `item-4-page` | Page numbers |

---

### Variant 3 — Index / Grid with Subtitles (Slide 05)
Up to 12 items arranged in a 2-column grid. Each item has a number, title, and short subtitle description. Uses an alternate footer format.

| Shape name | Content |
|---|---|
| `index-title-text` | "Index" |
| `item-1-number` … `item-12-number` | Section numbers |
| `item-1-title` … `item-12-title` | Section titles |
| `item-1-subtitle` … `item-12-subtitle` | Short description of each section |

**Alternate footer shapes (this variant only):**

| Shape name | Content |
|---|---|
| `Name` (×3) | Service line / Presentation name / Page ref |

---

### Variant 4 — Index / Visual Numbers (Slide 06)
Up to 5 items with large decorative numbers and short titles. Used for visual emphasis. Fewer items, bolder look.

| Shape name | Content |
|---|---|
| `index-title` | "Index" |
| `name_01` … `name_05` | Section numbers (large display) |
| `Title` (×5) | Section titles |

---

## Footer shapes (Variants 1, 2, 4)
| Shape name | Content |
|---|---|
| `Digital Design Strategy` | Service line |
| `Project Name` | Project name |
| `Month Year` | Date |
| `2026` | Copyright year |

---

## When to Use
| Variant | Use when |
|---|---|
| Variant 1 (List, 9 items) | Standard proposal or capability deck with 5–9 sections |
| Variant 2 (List + page, 4 items) | Short decks with 3–4 sections and explicit page refs |
| Variant 3 (Grid + subtitles, 12 items) | Complex decks where each section needs a brief description |
| Variant 4 (Visual, 5 items) | Visually led decks; 3–5 clear top-level chapters |

## Usage Rules
- Skip index only for very short decks (under 8 slides) with no chapter structure.
- Never change `index-title` text — it must always read "Index".
- Unused item slots must have their text cleared (not left as placeholder text).
