# Executive Summary Slide

## Overview
A dedicated slide for the key messages or situation summary at the start of a deck. Four layout variants offering progressively richer column arrangements.

## Template file
`templates/powerpoint/presentations-skill.pptx`

---

## Variants

### Variant 1 — Executive Summary / Single Intro (Slide 14)
Title at the top-left. Large single body column below, suitable for one sustained argument.

| Shape name | Content | Position |
|---|---|---|
| `exec-title` | "Executive Summary" or custom heading | @(90, 209) 839×83 |
| `exec-intro` | Full body text (prose or bullets) | @(88, 562) 1210×420 |

---

### Variant 2 — Executive Summary / Single Body (Slide 15)
Title mid-slide with body text below. Useful when the summary is short and punchy.

| Shape name | Content | Position |
|---|---|---|
| `exec-title` | Section heading | @(88, 402) 1210×83 |
| `exec-body-1` | Body text | @(88, 519) 1210×420 |

---

### Variant 3 — Executive Summary / Three Columns (Slide 16)
Title on the left, body split into two columns to the right. Best for 2–3 distinct key messages.

| Shape name | Content | Position |
|---|---|---|
| `exec-title` | Section heading (left column, doubles as label) | @(88, 369) 594×167 |
| `exec-body-1` | Message column 1 | @(706, 369) 594×420 |
| `exec-body-2` | Message column 2 | @(1325, 369) 594×388 |

---

### Variant 4 — Executive Summary / Title + Three Columns (Slide 17)
Full-width title at top. Three equal body columns below. Use for 3 clearly distinct points.

| Shape name | Content | Position |
|---|---|---|
| `exec-title` | Full-width heading | @(88, 359) 1826×83 |
| `exec-body-1` | Column 1 | @(88, 476) 588×291 |
| `exec-body-2` | Column 2 | @(707, 476) 588×291 |
| `exec-body-3` | Column 3 | @(1326, 476) 588×226 |

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
- Use in proposals and pitches, placed after the Confidentiality Statement and before chapter content.
- Variant 1 or 2 for a single narrative summary.
- Variant 3 or 4 when the summary breaks into 2–3 distinct key messages or pillars.
- Omit in internal or purely informational decks unless a clear set of key messages exists.

## Usage Rules
- `exec-title` is usually "Executive Summary" — change only when a more specific heading fits better.
- Never leave placeholder or Lorem ipsum text in body columns.
- Unused columns must be cleared — do not leave "column 3" empty in a 2-column layout; use Variant 3 instead.
