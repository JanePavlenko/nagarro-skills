# Content Slide

## Overview
The general-purpose workhorse slide for body copy sections. Used whenever a section needs a title, optional subtitle, and a block of text with paragraphs and/or bullet points. One variant, light by default.

## Light / Dark Mode
Supports light and dark mode. Mode can be switched per slide via variables.

## Header & Footer
Has both header and footer.

---

## Variants

### Content - Title + Body / Light
- Nagarro logo top left (header)
- Large slide title (`content-title`)
- Mint-coloured subtitle line below the title (`content-subtitle`) — optional, can be left blank
- Full-width body area (`content-body`): supports a prose paragraph followed by a bullet or numbered list
- Footer: Digital Design Strategy | Project Name | Month Year | © year
- Light background by default

---

## Layer Names
| Layer | Name |
|---|---|
| Outer content wrapper | `content-area` |
| Title + subtitle container | `title-block` |
| Title text | `content-title` |
| Subtitle text | `content-subtitle` |
| Body copy container | `body-block` |
| Body text (prose + bullets) | `content-body` |

---

## When to Use
- Use for any content section that needs a title and free-form body copy — this is the default slide when no more specific template fits
- Triggered by brief content such as: "the challenge", "our approach", "proposal overview", "technical overview", "commercial model", "background", "context", "methodology", "next steps", "scope"
- Use multiple instances of this slide within a chapter when the content is too long for one slide — keep the same title and append "(cont.)" or break into logical sub-topics with different titles
- Do not use when the content is better represented as a table (→ Tables), a diagram (→ Vector Tree), a timeline (→ Timelines), or data/statistics (→ Infographics)

## Usage Rules
- The subtitle line is optional — leave it blank if the title is self-sufficient
- Body copy supports both prose paragraphs and bullet/numbered lists — use whichever matches the content
- Do not overload a single slide — if bullets exceed 6 items or the prose runs longer than ~5 lines, split across two slides
- This slide is intentionally minimal — it relies on content quality, not layout complexity
