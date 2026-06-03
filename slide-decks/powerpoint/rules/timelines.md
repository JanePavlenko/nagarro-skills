# Timeline Slides

## Overview
Project schedule, sprint plan, and milestone slides. Four variants covering sprint timelines, milestone tables, and kick-off day schedules.

## Template file
`templates/powerpoint/presentations-skill.pptx`

---

## Variants

### Variant 1 — Timeline / 8-Week Sprint (Slide 58)
Horizontal 8-week timeline. Each week column has a header. Activities shown as diagonal bands across weeks. Background image carries the visual track layout.

| Shape name | Content | Position |
|---|---|---|
| `Week 1` … `Week 8` | Week column headers | @(100–1697, 255) 59×22 each |
| `Project Kick-Off` (×4) | Activity/sprint labels within weeks | Various positions |

*Timeline layout and bands are part of `timeline layout` and `content` PICTURE shapes.*

---

### Variant 2 — Timeline / 4-Week Simplified (Slide 59)
Four-week timeline with sprint milestones. Fewer columns, more space per sprint. Sprint label shape names are reused.

| Shape name | Content |
|---|---|
| `Week 1` … `Week 4` | Week column headers |
| `Workshop` | First activity (week 1) |
| `Project Steps / Points go here` | Generic step label |
| `Project Kick-Off` | Sprint milestone label |

---

### Variant 3 — Milestone Table (Slide 60)
Table listing project milestones, deliverables, dependencies, and approval outcomes. Each cell is a separate shape named `cell-text`.

| Shape name | Content |
|---|---|
| `table-title` | Table heading (e.g. "Milestone Outputs & Dependencies") |
| `cell-text` (×20+) | Individual table cells — headers and data rows |

**Column headers (first row `cell-text` shapes):**
- "Milestone"
- "What BRAND receives"
- "Key dependencies"
- "Approval outcome"

**Row labels (first column):** M1, IM1, M2, M3

*When populating, identify cells by position (x, y coordinates) since all are named `cell-text`.*

---

### Variant 4 — Kick-Off Timeline / Day-by-Day (Slide 61)
Detailed day-by-day kick-off schedule. 5 day columns, activity cards per day.

| Shape name | Content |
|---|---|
| `timeline-title` | Schedule title (e.g. "MVP Kick-Off Timeline") |
| `kicker` | Short label above title (e.g. "Proposed Approach") |
| `column-label` (×5) | Day labels: "Day 1" … "Day 5" |
| `card-1-title` … `card-8-title` | Activity card titles |
| `card-1-body` … `card-8-body` | Activity card descriptions |

---

## Footer shapes (all variants)
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
| 1 (8-week) | Proposals with a sprint-by-sprint delivery plan |
| 2 (4-week simplified) | Shorter engagements or phase plans |
| 3 (Milestone table) | Deliverable-based milestones with dependencies |
| 4 (Day-by-day kick-off) | Workshop or discovery kick-off schedules |

## Usage Rules
- Week labels must match actual sprint/phase labels in the brief — never leave "Week 1" as a generic placeholder.
- `table-title` must reflect the actual milestone context.
- In Variant 3, clear any `cell-text` shapes that are not needed rather than leaving filler text.
- Background track images are baked in — do not attempt to redraw them.
