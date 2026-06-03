# PowerPoint Deck Building Guide

## Purpose
This is the master reference for building a Nagarro `.pptx` presentation using the clone-and-populate pattern. It defines the template file, slide map, fixed deck structure, section order, and how to populate shape content.

All slide types referenced here are documented in full in the other files in this `pptx-rules/` folder.

---

## Template File

```
templates/powerpoint/presentations-skill.pptx
```

- **91 slides**, **2000 × 1125 px** canvas
- Every slide has a `Layout` PICTURE shape at layer 0 — the Nagarro branded background (logo, footer separator, dark/light mode). Do not remove or replace this shape.
- Content shapes (text) sit on top of the Layout image.

---

## How to Clone and Populate a Slide

```python
from pptx import Presentation
from pptx.util import Emu
import copy

def clone_slide(template_prs, slide_index, output_prs):
    """Deep-copy slide at slide_index from template into output presentation."""
    template_slide = template_prs.slides[slide_index]
    # Add blank slide to output
    blank_layout = output_prs.slide_layouts[6]
    new_slide = output_prs.slides.add_slide(blank_layout)
    # Copy all shape XML
    for shape in template_slide.shapes:
        el = copy.deepcopy(shape.element)
        new_slide.shapes._spTree.insert(2, el)
    return new_slide

def set_shape_text(slide, shape_name, text):
    """Find a shape by name and set its text, preserving formatting."""
    for shape in slide.shapes:
        if shape.name == shape_name and shape.has_text_frame:
            tf = shape.text_frame
            # Preserve paragraph and run formatting; only replace text
            for para in tf.paragraphs:
                for run in para.runs:
                    run.text = ''
            tf.paragraphs[0].runs[0].text = text
            return True
    return False

def set_footer(slide, service_line, project_name, date, year="© 2026"):
    set_shape_text(slide, "Digital Design Strategy", service_line)
    set_shape_text(slide, "Project Name", project_name)
    set_shape_text(slide, "Month Year", date)
    set_shape_text(slide, "2026", year)
```

---

## Slide Index — Template Slide Numbers

> All indices are 0-based (Python). Slide 01 in the file = index 0.

| Template type | Slide(s) in file | Index (0-based) | Shape names doc |
|---|---|---|---|
| Cover / Standard | 01 | 0 | cover.md |
| Cover / Large Title | 02 | 1 | cover.md |
| Index / List 9 items | 03 | 2 | index.md |
| Index / List + page numbers | 04 | 3 | index.md |
| Index / Grid + subtitles | 05 | 4 | index.md |
| Index / Visual numbers | 06 | 5 | index.md |
| Chapter Cover / Center | 07 | 6 | chapter-cover.md |
| Chapter Cover / Number+Title | 08 | 7 | chapter-cover.md |
| Chapter Cover / Bottom Left | 09 | 8 | chapter-cover.md |
| Confidentiality / Bottom Left | 10 | 9 | confidentiality-statement.md |
| Confidentiality / Centered | 11 | 10 | confidentiality-statement.md |
| Confidentiality / Full-Width | 12 | 11 | confidentiality-statement.md |
| Content / Title+Subtitle+Body | 13 | 12 | content.md |
| Executive Summary / Single Intro | 14 | 13 | executive-summary.md |
| Executive Summary / Single Body | 15 | 14 | executive-summary.md |
| Executive Summary / Three Columns | 16 | 15 | executive-summary.md |
| Executive Summary / Title+3 Cols | 17 | 16 | executive-summary.md |
| A Note From Us / Intro | 18 | 17 | a-note-from-us.md |
| A Note From Us / Two Column | 19 | 18 | a-note-from-us.md |
| A Note From Us / Title+Body | 20 | 19 | a-note-from-us.md |
| A Note From Us / Stacked | 21 | 20 | a-note-from-us.md |
| A Note From Us / With Photo | 22 | 21 | a-note-from-us.md |
| Highlights / Quote Centered | 23 | 22 | highlights.md |
| Highlights / Double Quote | 24 | 23 | highlights.md |
| Highlights / Large Single Quote | 25 | 24 | highlights.md |
| Highlights / Quote Left-Aligned | 26 | 25 | highlights.md |
| Highlights / Quote Wide | 27 | 26 | highlights.md |
| Highlights / Quote + Content | 28 | 27 | highlights.md |
| Highlights / Quote + Portrait | 29 | 28 | highlights.md |
| Highlights / Large Full-Width | 30 | 29 | highlights.md |
| About Nagarro / Services Grid | 31 | 30 | about-nagarro.md |
| About Nagarro / Values | 32 | 31 | about-nagarro.md |
| About Nagarro / Impact Statement | 33 | 32 | about-nagarro.md |
| About Nagarro / Headline+Body | 34 | 33 | about-nagarro.md |
| About Nagarro / Headline Only | 35 | 34 | about-nagarro.md |
| About Nagarro / Stats | 36 | 35 | about-nagarro.md |
| About Nagarro / Two Columns | 37 | 36 | about-nagarro.md |
| About Nagarro / Three Columns | 38 | 37 | about-nagarro.md |
| About Nagarro / Three Boxes | 39 | 38 | about-nagarro.md |
| About Nagarro / Stats Bubbles Dark | 40 | 39 | about-nagarro.md |
| Why Nagarro / Process Phases | 41 | 40 | why-nagarro.md |
| Why Nagarro / Phase Deep-Dive | 42 | 41 | why-nagarro.md |
| Why Nagarro / Three Arguments | 43 | 42 | why-nagarro.md |
| Why Nagarro / Two Arguments | 44 | 43 | why-nagarro.md |
| Partners / Logo Grid | 45 | 44 | our-partners.md |
| Partners / Testimonials Grid | 46 | 45 | our-partners.md |
| Partners / Case Study 1 | 47 | 46 | our-partners.md |
| Partners / Case Study 2 | 48 | 47 | our-partners.md |
| Partners / Case Study 3 | 49 | 48 | our-partners.md |
| Partners / Case Study 4 | 50 | 49 | our-partners.md |
| Partners / Case Study 5 | 51 | 50 | our-partners.md |
| Partners / Regional Logos | 52 | 51 | our-partners.md |
| Partners / Partnership Statement | 53 | 52 | our-partners.md |
| Partners / Capability Grid | 54 | 53 | our-partners.md |
| Partners / Logo Grid Alt | 55 | 54 | our-partners.md |
| Partners / Empty Logo Grid | 56 | 55 | our-partners.md |
| Partners / Industry Breakdown | 57 | 56 | our-partners.md |
| Timeline / 8-Week Sprint | 58 | 57 | timelines.md |
| Timeline / 4-Week Simplified | 59 | 58 | timelines.md |
| Timeline / Milestone Table | 60 | 59 | timelines.md |
| Timeline / Kick-Off Day-by-Day | 61 | 60 | timelines.md |
| Tables / Tech Stack | 62 | 61 | tables.md |
| Tables / Pricing | 63 | 62 | tables.md |
| Infographic / Donut Chart | 64 | 63 | infographics.md |
| Infographic / Horizontal Bar Segmented | 65 | 64 | infographics.md |
| Infographic / Bar Chart + Copy | 66 | 65 | infographics.md |
| Infographic / Bubble Circles | 67 | 66 | infographics.md |
| Infographic / Line Graph | 68 | 67 | infographics.md |
| Infographic / Vertical Bars Ranked | 69 | 68 | infographics.md |
| Infographic / Horizontal Bar Chart | 70 | 69 | infographics.md |
| Infographic / Venn 4 Circles | 71 | 70 | infographics.md |
| Infographic / Venn 3 Full-Width | 72 | 71 | infographics.md |
| Diagram / Layer Stack | 73 | 72 | diagrams.md |
| Diagram / Three Image Cards | 74 | 73 | diagrams.md |
| Diagram / Architecture | 75 | 74 | diagrams.md |
| Diagram / Process Roadmap | 76 | 75 | diagrams.md |
| Diagram / Flow Scheme | 77 | 76 | diagrams.md |
| Diagram / Support Flow | 78 | 77 | diagrams.md |
| Diagram / Token Architecture | 79 | 78 | diagrams.md |
| Assumptions / Two Items | 80 | 79 | assumptions.md |
| Assumptions / Three Items | 81 | 80 | assumptions.md |
| Assumptions / Two Items Alt | 82 | 81 | assumptions.md |
| Assumptions / Three Items Alt | 83 | 82 | assumptions.md |
| Team / Individual + Photo | 84 | 83 | team.md |
| Team / Composition Table | 85 | 84 | team.md |
| Team / Grid 7 Members | 86 | 85 | team.md |
| Team / Org Structure | 87 | 86 | team.md |
| Team / Detailed Bio | 88 | 87 | team.md |
| Team / Full-Page Profile | 89 | 88 | team.md |
| Team / Grid 5 Members | 90 | 89 | team.md |
| Outro | 91 | 90 | outro.md |

---

## Fixed Deck Structure

Every deck opens with the same sequence. Non-negotiable unless explicitly told otherwise.

```
1. Cover                    (always first — index 0 or 1)
2. Index                    (always second — skip only for decks under 8 slides)
3. Confidentiality Statement (external decks — index 9, 10, or 11)
4. Executive Summary        (proposals and pitches — index 13–16)
5. A Note From Us           (proposals only — index 17–21)
```

Followed by content sections (see Standard Section Order below), ending always with:

```
N-1. Assumptions (proposals only — index 79–82)
N.   Outro       (always last — index 90)
```

---

## Standard Section Order

```
── INTRO ──────────────────────────────────────────
  Cover → Index → Confidentiality
  → Executive Summary → A Note From Us

── CHALLENGE & CONTEXT ────────────────────────────
  Chapter Cover
  Content slides (index 12)

── APPROACH & DELIVERY ────────────────────────────
  Chapter Cover
  Content slides, Diagrams, Timelines, Tables

── WHY NAGARRO & PARTNERS ─────────────────────────
  Chapter Cover
  Why Nagarro slides (index 40–43)
  Partners slides (index 44–56)
  Highlights (index 22–29)

── ABOUT NAGARRO & TEAM ───────────────────────────
  Chapter Cover
  About Nagarro slides (index 30–39)
  Team slides (index 83–89)

── CLOSE ──────────────────────────────────────────
  Assumptions (proposals only — index 79–82)
  Outro (index 90)
```

---

## Section Inclusion by Deck Type

| Section | Proposal | Capability | Kick-off | Internal | Recruitment |
|---|:---:|:---:|:---:|:---:|:---:|
| Intro block | ✅ | ✅ | ✅ | ✅ | ✅ |
| Challenge & Context | ✅ | ✅ | ✅ | ⚪ | ❌ |
| Approach & Delivery | ✅ | ✅ | ✅ | ⚪ | ❌ |
| Why Nagarro | ✅* | ✅* | ❌ | ❌ | ❌ |
| Partners | ✅ | ✅ | ⚪ | ❌ | ⚪ |
| About Nagarro | ✅* | ✅ | ❌ | ❌ | ✅ |
| Team | ✅ | ⚪ | ✅ | ⚪ | ✅ |
| Assumptions | ✅ | ❌ | ⚪ | ❌ | ❌ |

✅ Always include · ⚪ Include if content is available · ❌ Do not include
\* Only if audience does not already know Nagarro well

---

## Footer Fields — Standard Values

These four shapes appear on almost every slide. Always populate them:

| Shape name | What to put |
|---|---|
| `Digital Design Strategy` | Service line (e.g. "Digital Design Strategy", "Product Studio") |
| `Project Name` | Client name or project name |
| `Month Year` | Presentation date (e.g. "May 2026") |
| `2026` | Copyright year as "© 2026" — update year as needed |

Some slides (05, 18, 30, 38) use an alternate footer with `Name` shapes (×3). See the relevant slide-type MD file.

---

## Chapter Structure Rules

**Content slides must outnumber chapter covers.** This is the primary rule. If you have 4 chapter covers, you need more than 4 content slides — significantly more. A deck where chapters and content are roughly equal is half structural, half substance. That's the wrong balance.

**Each chapter must contain at least 2 content slides.** A chapter cover with a single slide behind it is almost never justified. The rare exception is a standalone closing or transition section (e.g. a single Outro or Highlights slide after the last chapter) — but even then, consider whether a chapter cover is really needed.

**When slide count is limited, cut chapters before cutting content.** Chapter covers are structural overhead. If a brief gives you a tight slide limit, reduce the number of chapters first. A deck with 3 well-filled chapters is better than 6 thin ones.

**When given a slide count, ask whether chapter covers count toward it.** If a brief says "10 slides" and the structure needs 4 chapter covers, that leaves only 6 slides for content — which may be too tight. Clarify with the user before planning.

**Practical test before finalising the slide plan:** count content slides per chapter. If any chapter has only 1 content slide, merge it into an adjacent chapter or drop its cover slide.

---

## Hard Rules

1. **Clone from the template — never build from coordinates.** Always copy slide XML from `presentations-skill.pptx`; never draw shapes from scratch.
2. **Never remove the `Layout` PICTURE shape.** It carries the branded background.
3. **Populate every text shape.** Clear or replace all placeholder text ("Lorem ipsum", "Project Name", "Name Surname", etc.) before delivery.
4. **Never create new layouts.** If no template fits, flag it — do not invent shapes.
5. **Preserve run-level formatting.** When setting text, update only `run.text` — do not create new paragraphs or runs.
6. **Footer is mandatory.** Every slide in the output deck must have all four footer fields populated.
7. **Chapter numbers must auto-increment.** Track chapter count and write "01", "02", "03" … sequentially.
8. **Dark slides only for:** Cover, Index, Chapter Cover, Outro, About Nagarro (Stats Bubbles Dark). All other slides use the light layout.
