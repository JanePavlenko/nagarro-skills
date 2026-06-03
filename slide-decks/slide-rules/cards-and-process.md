# Cards & Process Slides — Pattern Rules

When a slide's content is **a set of parallel ideas** (3/4/6/8 items) or **a sequence of steps**, do not draw boxes by hand. Fetch the Card components from the Presentations Skill file and lay them out per `slide-decks/figma/slide-components.md`.

This rule fires for **any** of the following — even if the user only shows a reference image, screenshot, or describes the slide in words:

- "3 cards", "4 cards", "6 cards", "8 cards"
- "process", "steps", "stages", "phases", "flow" (with N items)
- "pillars", "principles", "proof points", "journeys", "value props"
- A reference slide with N equal-weight rectangles in a row or grid

---

## Detection → Component map

| What the user shows / asks for | Use this layout |
|---|---|
| 3 parallel cards in one row (no arrows) | **6-Section Grid pattern, single row** → 3× `Card Section Icon=true` at native 547px, OR `Card Section / Set of Cards` (`3620:1204`) |
| 3 steps with arrows / sequence | **3-Step Process** → 2× Process Card + 1× Card Section Icon=true |
| 4 steps with arrows / sequence | **4-Step Process** → 3× Process Card (418px) + 1× Card Section Icon=true (388px) |
| 4 parallel items | **4-Section Grid (2×2)** → Icon=true, 828×290px |
| 6 parallel items | **6-Section Grid (3×2)** → Icon=true, 544×290px |
| 8 parallel items | **8-Section Grid (4×2)** → Icon=false, 402×194px |
| 5 or 7 items | **Drop to next even count** — add a CTA/divider card or remove one |

All coordinates, gaps, node IDs, and resize formulas live in [`slide-decks/figma/slide-components.md`](../figma/slide-components.md). **Read that file before building.**

---

## Workflow when a reference slide is provided

1. **Count the cards** in the reference (3 / 4 / 6 / 8) and decide: parallel grid or sequential process?
2. **Extract the real content** from the reference: eyebrow tag, slide title, supporting line, per-card title, per-card body, footer/CTA bar.
3. **Look up the matching pattern** in [`slide-components.md`](../figma/slide-components.md). Use the node IDs and exact x/y/w/h from that doc.
4. **Fetch the components** via `figma.getNodeByIdAsync(...)` — never reproduce the card visually with rectangles + text.
5. **Place instances** on a fresh 1920×1080 frame, set text via the standard mixed-font pattern, populate the footer.
6. **Never leave** template placeholder text (`Title`, `Body text`, `Lorem ipsum`, etc.).

---

## Example: the "Proof journeys" reference

A reference slide with:
- Eyebrow tag ("Proof journeys")
- H1 ("Start with the work customers are trying to complete.")
- Supporting line under H1
- **3 cards in a single row**, each with a quoted question + a short body
- Dark CTA bar at the bottom

→ Recognize this as a **3-card parallel grid** (not a process — no arrows, no sequence).
→ Use 3× `Card Section Icon=true` (`3620:1140`) at native 547×290px, OR the prebuilt `Card Section / Set of Cards` (`3620:1204`).
→ Position per the 3-card row math in `slide-components.md` (x = 98, 687, 1276; y = 395).
→ Populate per-card title with the quoted question, body with the supporting sentence.
→ Add the dark CTA bar as a separate element below the cards.

---

## Hard rules

- **Never `figma.createFrame()` a slide from scratch.** Always **clone a base content template frame** (see "Base Content Frames" in [`slide-components.md`](../figma/slide-components.md)) and populate it. The template owns the brand chrome (logo, fonts, footer, background) — recreating it manually loses fidelity every time.
- **Never** draw cards with `figma.createRectangle()` + text. Always use the Card components.
- **Never** invent sizes. The widths/heights/gaps in `slide-components.md` are the source of truth.
- **Native size first** — only resize when the count requires it (4-step process, 4/8-section grids).
- **Process = arrows** (Process Card with the built-in arrow). Grid = no arrows (plain Card Section).
- **Last step of a process** is always a plain Card Section Icon=true — never a Process Card (avoids a trailing arrow pointing into nothing).
