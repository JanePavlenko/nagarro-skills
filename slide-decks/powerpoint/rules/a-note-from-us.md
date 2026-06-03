# A Note From Us Slide

## Overview
A personal, relationship-driven message to the client — typically from the Product Studio or Nagarro leadership. Used in proposals and pitch decks to establish partnership tone before the technical content begins.

## Template file
`templates/powerpoint/presentations-skill.pptx`

---

## Variants

### Variant 1 — A Note From Us / Intro (Slide 18)
Title top-left with a single large body text area. Cleanest and most readable variant. Alternate footer.

| Shape name | Content | Position |
|---|---|---|
| `note-title` | "A Note From Us" | @(90, 209) 896×83 |
| `note-intro` | Body message | @(88, 610) 1210×422 |

**Alternate footer shapes (this variant only):**
| Shape name | Content |
|---|---|
| `note-name-1` | Studio name (e.g. "Product Studio") |
| `note-name-2` | Presentation name |
| `note-name-3` | Page or section reference |

---

### Variant 2 — A Note From Us / Two Column (Slide 19)
Title/label left column, two body text columns. Use when the note has two distinct parts (e.g. intro + credentials).

| Shape name | Content | Position |
|---|---|---|
| `A NoteFrom Us` | Title label (left) | @(88, 336) 594×167 |
| `note-body-1` | First column body | @(704, 336) 594×323 |
| `note-body-2` | Second column body | @(1321, 336) 594×452 |

---

### Variant 3 — A Note From Us / Title + Single Body (Slide 20)
Title left, body taking up two-thirds width. Balance between label and message.

| Shape name | Content | Position |
|---|---|---|
| `note-title` | "A Note From Us" | @(88, 351) 594×167 |
| `note-body-1` | Body message | @(704, 351) 902×422 |

---

### Variant 4 — A Note From Us / Stacked (Slide 21)
Title and body stacked vertically. Most similar to a Content slide. Use when the note is a single flowing paragraph.

| Shape name | Content | Position |
|---|---|---|
| `note-title` | "A Note From Us" | @(88, 402) 1210×83 |
| `note-body-1` | Body message | @(88, 519) 1210×422 |

---

### Variant 5 — A Note From Us / With Photo (Slide 22)
Title and body text paired with a masked photo on the right (speaker or author portrait). Use when attaching a name and face to the message.

| Shape name | Content |
|---|---|
| `note-title` | "A Note From Us" |
| `note-body-1` | Body message |

*Note: Photo image is a `PICTURE` shape named `Mask group` — replace via python-pptx `add_picture` to the shape's crop/fill.*

---

## Footer shapes (Variants 2–5)
| Shape name | Content |
|---|---|
| `Digital Design Strategy` | Service line |
| `Project Name` | Project name |
| `Month Year` | Date |
| `2026` | Copyright year |

---

## When to Use
- Include in proposals and relationship-driven pitches.
- Place after the Executive Summary.
- Omit in internal decks, informational overviews, or kick-off decks.

## Usage Rules
- `note-title` text should almost always read "A Note From Us" — change only if a specific signatory is needed.
- Keep the note personal and warm in tone — this is not a technical slide.
- Variant 1 (Intro) is the default. Use Variant 5 when a speaker photo strengthens the message.
