# Nagarro Skills

Standalone Claude skills for producing Nagarro-branded outputs.

Each skill is self-contained: it collects its own brief, enforces brand consistency via the shared `brand/` docs, and produces the final deliverable without requiring an agent team.

## Skills

| Skill | What it does | Trigger phrase |
|---|---|---|
| `nagarro-figma-deck` | Build a presentation deck in Figma | "build a deck in Figma", "create slides" |
| `nagarro-pptx-deck` | Build a presentation deck as a `.pptx` | "make a PowerPoint", "build slides" |
| `nagarro-email-cover` | Create an email or event banner in Figma | "make a cover", "create a banner" |
| `nagarro-linkedin-post` | Write a LinkedIn post | "write a post", "draft a LinkedIn caption" |
| `nagarro-marketing-campaign` | Plan an external marketing campaign | "plan a campaign", "content strategy" |
| `nagarro-internal-comms` | Write an internal letter or announcement | "internal email", "all-hands announcement" |

## Brand foundation

All skills draw from shared brand docs in `brand/`:

- `brand/tone-of-voice.md` — voice and writing rules for all channels
- `brand/design-system.md` — colours, typography, layout for visual outputs
- `brand/positioning.md` — Nagarro's core message and value proposition

## Setup

Open this repo in Claude Code (cloud or local). Skills load automatically — no install needed.

Type the trigger phrase or skill name and the skill launches, collects a brief, and produces the deliverable.
