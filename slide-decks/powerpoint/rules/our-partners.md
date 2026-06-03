# Partners & Clients Slides

## Overview
Slides showing Nagarro's client roster, testimonials, case studies, and partner relationships. Used in proposals and capability decks to build credibility.

## Template file
`templates/powerpoint/presentations-skill.pptx`

---

## Variants

### Variant 1 — Partners / Logo Grid (Slides 45, 55)
Left column: title + body text. Right area: logo grid (baked-in image). Default "trusted by" slide.

| Shape name | Content | Position |
|---|---|---|
| `partners-title` | "Trusted by global brands" or custom | @(88, 399) 594×167 |
| `partners-body` | Supporting paragraph | @(88, 599) 594×97 |

*`logo-grid` is a PICTURE shape — replace with updated client logos if needed.*

---

### Variant 2 — Partners / Testimonials Grid (Slide 46)
Full grid of client testimonials, 2 columns, 4 quotes per column. Each quote and attribution is a separate `text-content` shape.

| Shape name | Content |
|---|---|
| `testimonials-title` | "What Our Clients Say About Us" |
| `text-content` (×8+) | Individual quote text (alternating quote / attribution pairs) |

*Content shapes are named `text-content` — target by index position when populating.*

---

### Variant 3 — Partners / Case Study (Slides 47–51)
Full-bleed image background with a single bold headline. Used as visual case study "moment" slides. Background image is a PICTURE shape named `Slide1`, `Slide2`, etc.

| Shape name | Content |
|---|---|
| `showcase-headline` | Bold project description or impact statement |

*Replace background image by swapping the `SlideN` PICTURE shape.*

---

### Variant 4 — Partners / Logo Grid + Body (Slide 52)
Title + short body on the left. Logos (`Logos` image) filling the right. Regional or segment-specific version.

| Shape name | Content | Position |
|---|---|---|
| `partners-title` | "Trusted by:" or segment label | @(88, 359) 594×50 |
| `partners-body` | Supporting description | @(88, 432) 594×333 |

---

### Variant 5 — Partners / Partnership Statement (Slide 53)
Single centered partnership headline. Background image (`Group 36335`) fills the right. Minimal and impactful.

| Shape name | Content |
|---|---|
| `partners-headline` | Partnership tagline (e.g. "A Partnership to Stay.") |

---

### Variant 6 — Partners / Capability + Technology Grid (Slide 54)
Three column headers + dense grid of capability/technology tags. Use for showing breadth of work areas.

| Shape name | Content |
|---|---|
| `partners-title` | Main heading |
| `We work with` | Column 1 header |
| `In multiple areas` | Column 2 header |
| `Across technology` | Column 3 header |
| `Innovation` … `SAP` etc. | Individual capability/tech labels |

---

### Variant 7 — Partners / Empty Logo Grid (Slide 56)
Footer-only slide with logo grid image and no text shapes. Used as a pure logo display.

*No content shapes — logo grid image only.*

---

### Variant 8 — Partners / Industry Breakdown (Slide 57)
Two-column list of 10 industry verticals with logo strips per industry. Title + industry titles.

| Shape name | Content |
|---|---|
| `partners-title` | Heading (e.g. "Working with the leaders in each industry") |
| `industry-title-1` … `industry-title-10` | Industry sector names |

---

## Footer shapes (Variants 1, 2, 4, 5, 6, 7, 8)
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
| 1 (Logo grid) | Standard "we work with" credibility slide |
| 2 (Testimonials) | When client quotes are strong proof points |
| 3 (Case study) | Individual project showcase with impact headline |
| 4 (Regional logos) | Regional or sector-specific client proof |
| 5 (Partnership statement) | Relationship-led closing argument |
| 6 (Capability grid) | Broad breadth-of-service slide |
| 8 (Industry breakdown) | When showing cross-industry reach is key |

## Usage Rules
- Use 1–3 partner slides per deck. Do not stack all variants in one deck.
- `showcase-headline` must be a real project impact statement, not placeholder text.
- Never leave "We help our clients transform…" filler text in the final output.
