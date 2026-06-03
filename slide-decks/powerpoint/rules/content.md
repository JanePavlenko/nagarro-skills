# Content Slide

## Overview
The general-purpose workhorse slide for body copy. Used whenever a section needs a title, optional subtitle, and a block of prose or bullets. One variant.

## Template file
`templates/powerpoint/presentations-skill.pptx`

---

## Variants

### Content — Title + Subtitle + Body (Slide 13)
Standard light-background content slide. Title at the top, optional mint-colour subtitle line below, then a large body text area.

| Shape name | Content | Position |
|---|---|---|
| `content-title` | Slide title | @(94, 238) 1697×83 |
| `content-subtitle` | Subtitle or section label — optional | @(94, 338) 1697×47 |
| `content-body` | Body copy: prose, bullets, or numbered list | @(94, 441) 1221×516 |

---

## Footer shapes
| Shape name | Content |
|---|---|
| `Digital Design Strategy` | Service line |
| `Project Name` | Project name |
| `Month Year` | Date |
| `2026` | Copyright year |

---

## When to Use
- Use for any narrative section that needs a title and free-form text.
- Default slide when no more specific template fits the content.
- Triggered by: "the challenge", "our approach", "proposal overview", "technical overview", "methodology", "next steps", "scope", "background", "context".
- Use multiple consecutive instances when content is too long for one slide — keep the same title and append "(cont.)" or break into logical sub-topics.

## Usage Rules
- `content-subtitle` is optional — leave it blank if the title is self-sufficient.
- Body supports prose paragraphs, bullet lists, and numbered lists.
- Do not overload: if bullets exceed 6 or prose exceeds ~5 lines, split across two slides.
- Do not use when content is better as a table (→ tables.md), diagram (→ diagrams.md), timeline (→ timeline.md), or data visual (→ infographics.md).
- Never leave placeholder text ("Lorem ipsum", "Your subtitle goes here") in the output.
