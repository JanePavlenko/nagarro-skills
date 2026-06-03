# Infographics Slides

## Overview
Data visualisation slides. Chart and infographic layouts where the visual graphic is a baked-in PICTURE shape and editable text labels sit on top. Seven variants covering donut charts, bar charts, bubble charts, line graphs, and Venn diagrams.

## Template file
`templates/powerpoint/presentations-skill.pptx`

---

## Variants

### Variant 1 — Infographic / Donut Chart (Slide 64)
Three-segment donut chart. Each segment has a label and description. Central percentage value.

| Shape name | Content | Position |
|---|---|---|
| `Percentage` | Central stat value (e.g. "64,2%") | @(782, 505) 424×133 |
| `bar-1-label` | Segment 1 label | @(1399, 544) 79×33 |
| `bar-1-desc` | Segment 1 description | @(1399, 577) 171×22 |
| `bar-2-label` | Segment 2 label | @(432, 572) 79×33 |
| `bar-2-desc` | Segment 2 description | @(432, 605) 171×22 |
| `bar-3-label` | Segment 3 label | @(601, 206) 79×33 |
| `bar-3-desc` | Segment 3 description | @(601, 240) 171×22 |

*Donut graphic is a PICTURE `Container` shapes group — replace if segment sizes change.*

---

### Variant 2 — Infographic / Horizontal Bar Segmented (Slide 65)
Segmented horizontal bar chart with a large percentage stat and three segment labels.

| Shape name | Content |
|---|---|
| `Percentage` | Primary stat value |
| `segment-label-1` | First segment label |
| `segment-label-2` | Second segment label |
| `segment-label-3` | Third segment label |
| `name_642` (×2) | Secondary stat values |

*Bar graphic is a `graph` + `legenda` PICTURE shapes.*

---

### Variant 3 — Infographic / Bar Chart + Copy (Slide 66)
Left: title + body copy. Right: bar chart with multiple `chart-title` labels for bars. Use for comparing 4–5 named metrics.

| Shape name | Content |
|---|---|
| `chart-title` | Slide title (main heading — leftmost instance) |
| `chart-body` | Supporting body text |
| `chart-title` (×4) | Bar labels (positioned over each bar in chart-area) |

*Identify bar-label instances by (x, y) position. `chart-area` is the bar chart PICTURE.*

---

### Variant 4 — Infographic / Bubble / Circle Chart (Slide 67)
Three nested or grouped circles of different sizes. Each circle has a label, stat, and description. Left: body copy.

| Shape name | Content |
|---|---|
| `chart-body` | Supporting body text (left column) |
| `circle-1-label` | Circle 1 label |
| `name_642` (circle 1) | Circle 1 stat |
| `circle-1-desc` | Circle 1 description |
| `circle-2-label` | Circle 2 label |
| `name_642` (circle 2) | Circle 2 stat |
| `circle-2-desc` | Circle 2 description |
| `circle-3-label` | Circle 3 label |
| `name_642` (circle 3) | Circle 3 stat |
| `circle-3-desc` | Circle 3 description |

*Three PICTURE shapes (`Big Topic`, `Medium Topic`, `Small Topic`) are the circle graphics.*

---

### Variant 5 — Infographic / Line Graph (Slide 68)
Left: title + body copy. Right: line graph with week labels, stat value, and stat label.

| Shape name | Content |
|---|---|
| `chart-title` | Slide title |
| `chart-body` | Body text |
| `Week 1` … `Week 8` | X-axis period labels |
| `stat-value` | Key stat over the graph (e.g. "+132%") |
| `stat-label` | Stat label (e.g. "Growth") |

*Line graph track is a `Group 1437253221` PICTURE shape.*

---

### Variant 6 — Infographic / Vertical Bars Ranked (Slide 69)
Three ranked vertical bars of different heights. Left: title + body. Each bar has a label and description below it.

| Shape name | Content |
|---|---|
| `chart-title` | Slide title |
| `chart-body` | Body text |
| `Percentage` | Primary bar stat (tallest bar, left) |
| `name_642` (×2) | Secondary bar stats |
| `bar-1-label` | Bar 1 label |
| `bar-1-desc` | Bar 1 description |
| `bar-2-label` | Bar 2 label |
| `bar-2-desc` | Bar 2 description |
| `bar-3-label` | Bar 3 label |
| `bar-3-desc` | Bar 3 description |

*Bar graphics are the `name_1` / `name_2` / `name_3` shapes (tall rectangles).*

---

### Variant 7 — Infographic / Horizontal Bar Chart (Slide 70)
Left: title + body copy. Right: horizontal bar chart with 4 labeled segments and a legend. Bar graphics are a `bars` + `legenda` PICTURE stack.

| Shape name | Content |
|---|---|
| `chart-title` | Slide title |
| `chart-body` | Body text |
| `bar-label-1` | Bar 1 legend label |
| `bar-label-2` | Bar 2 legend label |
| `bar-label-3` | Bar 3 legend label |
| `bar-label-4` | Bar 4 legend label |

---

### Variant 8 — Infographic / Venn 4 Circles (Slide 71)
Left: title + body copy. Right: 4-element Venn or cluster diagram. Each circle has a label and an optional description.

| Shape name | Content |
|---|---|
| `chart-title` | Slide title |
| `chart-body` | Body text |
| `venn-1-label` | Circle 1 label (top) |
| `venn-2-label` | Circle 2 label |
| `venn-2-desc` | Circle 2 description |
| `venn-3-label` | Circle 3 label |
| `venn-3-desc` | Circle 3 description |
| `venn-4-label` | Circle 4 label |

*Venn graphic is a `graph` PICTURE shape.*

---

### Variant 9 — Infographic / Venn 3 Circles Full-Width (Slide 72)
Full-width 3-circle Venn. Title and body at the top, three labels below the circles.

| Shape name | Content |
|---|---|
| `chart-title` | Slide title |
| `chart-body` | Body text |
| `venn-1-label` | Circle 1 label |
| `venn-2-label` | Circle 2 label (center/overlap) |
| `venn-3-label` | Circle 3 label |

*Venn graphic is a `graph` PICTURE shape.*

---

## Footer shapes (all variants)
| Shape name | Content |
|---|---|
| `Digital Design Strategy` | Service line |
| `Project Name` | Project name |
| `Month Year` | Date |
| `2026` | Copyright year |

---

## Content type → Variant mapping
| Content type | Use variant |
|---|---|
| Single percentage / part-of-whole (3 segments) | 1 — Donut |
| Segmented proportion with 3 labels | 2 — Horizontal bar segmented |
| Ranked comparison with values (4–5 bars) | 3 — Bar chart + copy |
| Three different-sized groups / populations | 4 — Bubble circles |
| Trend over time / growth trajectory | 5 — Line graph |
| Ranked comparison (3 values, visual bars) | 6 — Vertical bars ranked |
| Comparison with legend (4 categories) | 7 — Horizontal bar chart |
| Four overlapping concepts / 4-way intersection | 8 — Venn 4 circles |
| Three overlapping concepts / Venn | 9 — Venn 3 full-width |

## Usage Rules
- Graphic visuals (circles, bars, lines) are baked-in PICTURE shapes. Only the text label shapes are editable.
- To change chart proportions or data points, the PICTURE shape must be replaced with a re-exported image — it cannot be edited in-place.
- Never leave `name_642` or "Description goes here" placeholder values in the output.
- `chart-title` and `chart-body` must always carry real content.
