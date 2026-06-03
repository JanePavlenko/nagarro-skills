# Deck Building Guide

## Purpose
This document is the master reference for constructing a Nagarro slide deck from a brief. It defines the standard deck structure, the fixed intro block, content section logic, and the rules for sequencing slides from the available templates.

All slide types referenced here are documented in full in the other files in this `slide-rules/` folder.

> **Before building any deck** (Figma or PowerPoint): read `slide-rules/deck-brief-guide.md` and use it to guide the brief collection conversation. Never start building until the slide plan is approved by the user.

---

## Deck Types

Choose the deck type from the brief before planning the slide sequence. The deck type determines which sections are included and in what order.

| Deck type | Triggered by |
|---|---|
| **Proposal** | "proposal", "RFP response", "bid", "tender", "offer", "pitch" |
| **Capability Overview** | "capabilities", "what we do", "overview of Nagarro", "intro deck" |
| **Project Kick-off** | "kick-off", "project start", "onboarding", "SOW kick-off" |
| **Internal** | "internal", "team meeting", "all hands", "staff", "colleagues" |
| **Recruitment / Employer Branding** | "recruitment", "employer branding", "why work at Nagarro", "careers" |

---

## Fixed Intro Block

Every deck — regardless of type — opens with the same sequence of slides. These are non-negotiable unless explicitly told otherwise.

```
1. Cover                       (always first — Cover - Standard / Light or Dark)
2. Index                       (always second — skip only for decks under 8 slides with no sections)
3. Confidentiality Statement   (always third — one slide, any variant)
4. Executive Summary           (one slide — use when the deck has a clear set of key messages)
5. A Note From Us              (one slide — use in proposals and relationship-driven decks)
```

For slides 4 and 5: include both in proposals and pitches. In purely informational or internal decks, both may be omitted — but if only one is used, it is always the Executive Summary, never A Note From Us alone.

Slides 4 and 5 are followed directly by the **Proposal Overview block** in proposal decks (see below).

---

## Proposal Overview Block (proposals only)

In proposal decks, after the intro block, include 1–3 overview slides using the **Content - Title + Body** template before moving into the chapter structure. These set the scene for what follows.

Typical overview slides (use as needed, not all required):
- **Proposal Overview** — the overall scope and intent of the proposal
- **Technical Solution Overview** — high-level summary of the technical approach
- **Proposed Commercial & Economic Model** — pricing model, engagement structure

These are plain `Content - Title + Body / Light` slides. The title names the overview type; the body carries a paragraph + bullet summary.

---

## Standard Section Order

After the intro block (and proposal overview if applicable), sections follow this order. Not every section appears in every deck — use the deck type table and the "When to Use" guidance in each slide-rules file to decide what to include.

```
── INTRO BLOCK ──────────────────────────────────────────
  Cover → Index → Confidentiality Statement
  → Executive Summary → A Note From Us
  [→ Proposal Overview slides, proposals only]

── CHALLENGE & CONTEXT ──────────────────────────────────
  Chapter Cover: "The Challenge" (or equivalent section title)
  Content slides: frame the client's problem, context, or needs
  (use Content - Title + Body; use multiple slides if needed)

── APPROACH & DELIVERY ──────────────────────────────────
  Chapter Cover: "Our Approach"
  Content slides: methodology, design approach, solution overview
  (use Content - Title + Body, Infographics, Diagrams as needed)

  Chapter Cover: "Delivery & Timeline"
  Timeline slides: project schedule, phases, sprint plan
  Table slides: milestones, dependencies, pricing (proposals)

── WHY NAGARRO & PARTNERS ───────────────────────────────
  Chapter Cover: "Why Nagarro" (skip if client knows Nagarro well)
  Why Nagarro slides: v1+v2, v3, or v4 depending on argument structure

  Chapter Cover: "Our Partners"
  Our Partners slides: logo grids, project showcases, testimonials
  Highlights slide: place here, near or after testimonials

── ABOUT NAGARRO & TEAM ─────────────────────────────────
  Chapter Cover: "About Nagarro"
  About Nagarro slides: 2–4 variants depending on audience needs

  Chapter Cover: "Our Team"
  Team slides: group view + individual bios as needed

── CLOSE ────────────────────────────────────────────────
  Assumptions (proposals only — one slide, near end)
  Confidentiality Statement (if not already placed at start)
  Outro (always last — one slide)
```

---

## Section Inclusion by Deck Type

| Section | Proposal | Capability | Kick-off | Internal | Recruitment |
|---|:---:|:---:|:---:|:---:|:---:|
| Intro block | ✅ | ✅ | ✅ | ✅ | ✅ |
| Proposal Overview slides | ✅ | ❌ | ❌ | ❌ | ❌ |
| Challenge & Context | ✅ | ✅ | ✅ | ⚪ | ❌ |
| Approach & Delivery | ✅ | ✅ | ✅ | ⚪ | ❌ |
| Why Nagarro | ✅* | ✅* | ❌ | ❌ | ❌ |
| Our Partners | ✅ | ✅ | ⚪ | ❌ | ⚪ |
| About Nagarro | ✅* | ✅ | ❌ | ❌ | ✅ |
| Team | ✅ | ⚪ | ✅ | ⚪ | ✅ |
| Assumptions | ✅ | ❌ | ⚪ | ❌ | ❌ |

✅ Always include · ⚪ Include if content is available · ❌ Do not include  
\* Only if the audience does not already know Nagarro well

---

## Content Type → Slide Template Mapping

Use this table when the brief mentions a specific type of content and you need to pick the right template.

| Content type | Slide template |
|---|---|
| Quote, testimonial, striking stat | Highlights |
| Client logos, partner network | Our Partners — Logo Grid variants |
| Specific past project | Our Partners — Project Showcase |
| Client + Nagarro joint presentation | Our Partners — Co-Branding |
| Team members with photos | Team — 5 or 10 Members |
| Reporting structure / org chart | Team — Team Structure |
| Staffing plan over time | Team — Team Composition |
| Individual bio | Team Member variants |
| Project schedule, roadmap | Timeline variants |
| Milestone table, deliverables | Table — Milestones + Dependencies |
| Tech stack, scope matrix | Table — Multi-Column Data |
| Pricing, cost breakdown | Table — Pricing Breakdown |
| Proportions, part-of-whole | Infographic — Donut or Horizontal Bar Segmented |
| Trend over time | Infographic — Line Graph |
| Ranked comparison | Infographic — Vertical Bars Ranked or Horizontal Bar Chart |
| Three equal pillars with icons | Infographic — 3 Icons + Copy |
| Two-thing overlap | Infographic — Venn Diagram 2 Circles |
| Three-thing overlap | Infographic — Venn Diagram 3 Circles |
| Layered hierarchy / tech stack diagram | Infographic — Layer Stack |
| Simple process flow / integration | Diagram — Flow Scheme Simple |
| Complex workflow / multi-party process | Diagram — Flow Scheme Complex |
| Multi-phase process with listed activities | Diagram — Process Roadmap |
| Classification hierarchy | Diagram — Taxonomy Tree |
| Pipeline architecture | Diagram — Architecture Flow |
| Any other body copy, context, narrative | Content — Title + Body |

---

## Light / Dark Mode

- The standard deck uses **light mode** for content slides and **dark mode** for structural slides (Cover, Chapter Cover, Index, Outro)
- All slides support mode switching via variables — no separate dark frames are needed
- Highlights slides can be light or dark depending on position and surrounding slides — match the tone of the surrounding section

---

## Chapter Structure Rules

**Content slides must outnumber chapter covers.** This is the primary rule. If you have 4 chapter covers, you need more than 4 content slides — significantly more. A deck where chapters and content are roughly equal is half structural, half substance. That's the wrong balance.

**Each chapter must contain at least 2 content slides.** A chapter cover with a single slide behind it is almost never justified. The rare exception is a standalone closing or transition section (e.g. a single Outro or Highlights slide after the last chapter) — but even then, consider whether a chapter cover is really needed.

**When slide count is limited, cut chapters before cutting content.** Chapter covers are structural overhead. If a brief gives you a tight slide limit, reduce the number of chapters first. A deck with 3 well-filled chapters is better than 6 thin ones.

**When given a slide count, ask whether chapter covers count toward it.** If a brief says "10 slides" and the structure needs 4 chapter covers, that leaves only 6 slides for content — which may be too tight. Clarify with the user before planning.

**Practical test before finalising the slide plan:** count content slides per chapter. If any chapter has only 1 content slide, merge it into an adjacent chapter or drop its cover slide.

---

## Slide Count Guidelines

| Deck type | Typical range |
|---|---|
| Proposal | 20–40 slides |
| Capability Overview | 12–20 slides |
| Project Kick-off | 10–18 slides |
| Internal | 8–15 slides |
| Recruitment / Employer Branding | 12–20 slides |

These are guides, not hard limits. Let content drive length — do not pad or cut to hit a number.
