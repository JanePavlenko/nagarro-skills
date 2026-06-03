# Chapter Cover Slide

## Overview
Section divider slides placed before each major chapter. Always dark background. Three layout variants differing in title placement and visual style.

## Template file
`templates/powerpoint/presentations-skill.pptx`

---

## Variants

### Variant 1 — Chapter Cover / Center (Slide 07)
Title fills the center of the slide as a large block. Chapter number sits bottom-right.

| Shape name | Content |
|---|---|
| `chapter-title` | Section title (1–5 words) |
| `chapter-number` | Auto-incremented chapter number: "01", "02" … |

Positions: title @(94, 399) 1366×533 · number @(1785, 832) 129×100

---

### Variant 2 — Chapter Cover / Number + Title (Slide 08)
Large chapter number sits at the top-left, followed by the title below it. Useful when chapter numbers are a design feature.

| Shape name | Content |
|---|---|
| `chapter-number` | Chapter number (top-left, large) |
| `chapter-title` | Section title below the number |

Positions: number @(88, 397) 1213×100 · title @(88, 528) 1493×133

---

### Variant 3 — Chapter Cover / Bottom Left (Slide 09)
Title anchored to the bottom-left of the slide. Number bottom-right. Most minimal and cinematic of the three.

| Shape name | Content |
|---|---|
| `chapter-title` | Section title |
| `chapter-number` | Chapter number |

Positions: title @(94, 799) 1432×133 · number @(1785, 832) 129×100

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
- Place a chapter cover before every major section in the deck.
- Use Variant 1 for section titles that span 3–5 words and benefit from visual emphasis.
- Use Variant 2 when chapter numbering is a key navigation device.
- Use Variant 3 for the most minimal, cinematic look or when the title is very short.

## Usage Rules
- Always dark background. Do not use on light slides.
- Chapter numbers must auto-increment across the deck: 01, 02, 03 …
- Never leave `chapter-title` as "Chapter title" — always replace with real section name.
