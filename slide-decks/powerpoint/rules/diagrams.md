# Diagrams Slides

## Overview
Architecture, flow, process, and layer diagram slides. The diagram graphic is always a baked-in PICTURE shape; editable text labels overlay it. Seven variants.

## Template file
`templates/powerpoint/presentations-skill.pptx`

---

## Variants

### Variant 1 — Diagram / Layer Stack (Slide 73)
Left: title + body. Right: vertical layer stack with 6 named layers and descriptions. Use for design system architecture, maturity models, or technical stacks.

| Shape name | Content |
|---|---|
| `chart-title` | Slide title |
| `body` | Body text |
| `Experience` | Layer 1 name (top) |
| `label` (for Experience) | Layer 1 description |
| `Governance` | Layer 2 name |
| `label` (for Governance) | Layer 2 description |
| `Patterns` | Layer 3 name |
| `label` (for Patterns) | Layer 3 description |
| `Components` | Layer 4 name |
| `label` (for Components) | Layer 4 description |
| `Motion` | Layer 5 name |
| `label` (for Motion) | Layer 5 description |
| `Tokens` | Layer 6 name (bottom) |
| `label` (for Tokens) | Layer 6 description |

*Layer name shapes are named after the layer they label. `label` shapes appear directly below each layer name — target by (y) position.*

---

### Variant 2 — Diagram / Three Image Cards (Slide 74)
Title spanning the top. Three image cards below, each with a label and body. Decorative images are `Group 1597880646/7/8` PICTURE shapes.

| Shape name | Content |
|---|---|
| `chart-title` | Slide title |
| `body` | Intro body text (top) |
| `label` (×3) | Card labels |
| `body` (×3) | Card body text |

*Identify `label` and `body` shape pairs by (x, y) position.*

---

### Variant 3 — Diagram / Architecture / Complex Flow (Slide 75)
Dense multi-layer architecture diagram. Nodes and labels are named by content. PICTURE frames carry the visual connector lines.

Key shape naming pattern: shapes are named by their node title (e.g. "Server", "Title", "Bullet Point 1"). Target by position. Not suited for programmatic auto-population — use for clone-only with manual edits.

---

### Variant 4 — Diagram / Process Roadmap (Slide 76)
Horizontal process roadmap with phases (Discovery, Delivery) and swimlane activities per phase step. Shapes are named by their content labels.

Key shapes:
| Shape name | Content |
|---|---|
| `Product Discovery` | Discovery phase label |
| `Product Delivery` | Delivery phase label |
| `Business Discovery` … `Post-release KPI metrics` | Phase step labels |
| `Discovery Workshops` … `Release measurelearn iterate` | Swimlane activity labels |
| Various named content shapes | Activity descriptions |

*Process graphic is a `Group 1597880684` PICTURE shape.*

---

### Variant 5 — Diagram / Flow Scheme (Slide 77)
Left: title + body copy. Right: node diagram with topic labels connected by flow lines.

| Shape name | Content |
|---|---|
| `diagram-title` | Slide title |
| `diagram-body` | Body text |
| `Topic` (×8) | Node labels — target by (x, y) position |

*Flow lines and node backgrounds are a `Group 1597880684` PICTURE shape.*

---

### Variant 6 — Diagram / Support Flow (Slide 78)
Complex support/governance flow diagram with many named process nodes. Shapes named after their content labels. Best used as a clone-and-edit slide — not auto-populated.

Key identifiable shapes: `diagram-title`, `FIFA team`, `MonitoringTools`, `Nagarro L3SupportTeam`, `ProblemManagement`, `ChangeManagement`, `Reporting Governance`, etc.

---

### Variant 7 — Diagram / Token Architecture (Slide 79)
Technical platform / design token architecture flow from Design Layer → DS Repository → Platform Libraries → Application Layer.

| Shape name | Content |
|---|---|
| `diagram-title` | Slide title |
| `Design Layer` | Layer label 1 |
| `Token Trabsformation` | Layer label 2 |
| `DS Repository` | Layer label 3 |
| `Platform Specific Libraries` | Layer label 4 |
| `Application Layer` | Layer label 5 |
| `Existing Backend Platform` | Layer label 6 |
| Named technology shapes | e.g. "Figma DS Variables", "WebComponents", "MobileComponents" |

*Architecture flow graphic is a `graph` PICTURE shape.*

---

## Footer shapes (Variants 1–7)
| Shape name | Content |
|---|---|
| `Digital Design Strategy` | Service line |
| `Project Name` | Project name |
| `Month Year` | Date |
| `2026` | Copyright year |

---

## Content type → Variant mapping
| Content type | Use variant |
|---|---|
| Design system architecture / maturity stack | 1 — Layer stack |
| Three capability or product areas with visuals | 2 — Three image cards |
| Multi-layer platform / technical architecture | 3 — Architecture |
| Product process with discovery + delivery phases | 4 — Process roadmap |
| Simple flow diagram with 6–9 nodes | 5 — Flow scheme |
| Support / approval / governance flow | 6 — Support flow |
| Token / design system technical architecture | 7 — Token architecture |

## Usage Rules
- Diagram graphics are baked-in PICTURE shapes. Only text labels are editable.
- To significantly change the diagram structure, replace the PICTURE shape with a re-exported image.
- `diagram-title` and `diagram-body` must always carry real content — never leave Lorem ipsum.
- For Variants 3, 4, 6: use as clone-and-edit only; do not attempt full programmatic population.
