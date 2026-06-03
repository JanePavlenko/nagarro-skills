# Tables Slides

## Overview
Data table slides for tech stacks, scope matrices, pricing, and multi-column structured data. Two variants.

## Template file
`templates/powerpoint/presentations-skill.pptx`

---

## Variants

### Variant 1 — Table / Tech Stack (Slide 62)
Multi-column table with row categories and sub-categories. Suited for technology stack, scope, or tool matrix.

**Column headers:**
| Shape name | Content |
|---|---|
| `Category` | Left column header |
| `Sub-category` | Second column header |
| `Description ToolTechnologies` | Third column header |
| `Licensing` | Fourth column header |

**Row category labels (first cell per group):**
| Shape name | Example content |
|---|---|
| `Frontend` | "Frontend" |
| `Backend` | "Backend" |
| `Observability` | "Observability" |
| `Authentication Platform` | "Authentication Platform" |
| `Design` | "Design" |

**Data cells** (named after their content — do not rename):
Each sub-row has shapes named after the sub-category label, technology name, and license. Target by (x, y) position when populating programmatically.

*Background table grid is a `table` PICTURE shape — text shapes sit on top.*

---

### Variant 2 — Table / Pricing / Commercial (Slide 63)
Three-column commercial breakdown table: Phase, Breakdown, and Contract Value.

| Shape name | Content |
|---|---|
| `Phase` | "Phase" (column header) |
| `Breakdown` | "Breakdown" (column header) |
| `Contract Value` | "Contract Value" (column header) |
| `Release R1  R2` | Row label: release phase |
| `Total cost 2026` | Row label |
| `Build  Run 2027` | Row label |
| `Total cost 2027` | Row label |
| `Run 2028 AMS` | Row label |
| `Total Sum NET 2026 2027 2028` | Total row label |
| `Development Cost Design  Requirements` | Breakdown detail |
| `Build PI-1  PI-2 Run AMS` | Breakdown detail |
| `Run AMS` | Breakdown detail |
| `name_270160 148768` | Contract value cells |
| `name_418928` | Total value |
| `name_269360 67600` | Year 2 values |
| `name_336960` | Year 2 total |
| `name_135200` | Year 3 value |
| `name_891088` | Grand total |

*Background table grid is a `table` PICTURE shape.*

---

## Footer shapes (both variants)
| Shape name | Content |
|---|---|
| `Digital Design Strategy` | Service line |
| `Project Name` | Project name |
| `Month Year` | Date |
| `2026` | Copyright year |

---

## When to Use
| Variant | Best for |
|---|---|
| 1 (Tech stack) | Architecture overviews, scope matrices, tool comparisons |
| 2 (Pricing) | Commercial proposals, pricing breakdowns, cost summaries |

## Usage Rules
- Table background grids are baked-in images — only update the text shapes on top.
- For Variant 1: identify cells by (x, y) position when multiple shapes share similar names.
- For Variant 2: update all `name_*` value shapes with real figures — never leave placeholder numbers.
- Do not add extra rows beyond what the template provides — use a second slide if more rows are needed.
