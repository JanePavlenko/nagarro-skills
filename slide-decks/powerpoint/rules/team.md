# Team Slides

## Overview
Slides presenting project team members, org structure, and staffing plans. Seven variants ranging from individual profiles to group grids and team composition tables.

## Template file
`templates/powerpoint/presentations-skill.pptx`

---

## Variants

### Variant 1 — Team / Individual Profile + Photo (Slide 84)
Single member profile card with a small photo, name, role, and supporting details.

| Shape name | Content |
|---|---|
| `member-name` | Full name |
| `member-role` | Role / position |

*`CV Photo` is a PICTURE shape — replace with the member's photo.*
*`3` is a PICTURE shape for role category indicator.*

---

### Variant 2 — Team / Composition Table (Slide 85)
Staffing plan table showing roles, locations, and monthly allocation. Shapes are named by column header.

Key shape names:
| Shape name | Content |
|---|---|
| `Role` | "Role" (column header) |
| `Location` | "Location" (column header) |
| `M1` … `M4` | Month column headers |

*~80 individual cell shapes, each named after their column label. Target data cells by (x, y) position.*

---

### Variant 3 — Team / Grid 7 Members (Slide 86)
Seven team member photo cards in a grid layout. Each card is a `Team Member` PICTURE shape — replace with individual member photos.

*No named text content shapes — member names and roles are baked into the card images.*

---

### Variant 4 — Team / Org Structure (Slide 87)
Hierarchy structure showing roles connected by lines. Role shapes named `Role position`.

| Shape name | Content |
|---|---|
| `Role position` (×multiple) | Role or position title for each node |

*Org chart line connectors are PICTURE shapes (`Group 36449`, `Group 36448`).*

---

### Variant 5 — Team / Detailed Bio (Slide 88)
Full individual profile: name, role, work experience paragraph, key skills, software list. Used in appendix or team section for key personnel.

| Shape name | Content |
|---|---|
| `member-name` | Full name |
| `member-role` | Role / position |
| `At vero eos et accus` | "Work experience" section label |
| Long content shape (work exp) | Work experience description |
| `At vero eos et accus` (2nd) | "Key skills" section label |
| Long content shape (skills) | Skills list |

*Additional shapes: software list, photo (`CV Photo` or `content`), industry/stat shapes.*

---

### Variant 6 — Team / Detailed Profile with Photo (Slide 89)
Full-slide individual profile with photo, name, role, and multi-section bio. Alternate footer.

| Shape name | Content |
|---|---|
| `member-name` | Full name |
| `member-role` | Role / position |

*`CV Photo` PICTURE shape + `Main Section` layout image. Alternate footer: `Name` (×3).*

---

### Variant 7 — Team / Grid 5 Members (Slide 90)
Five team member photo cards in a row. Each card is a `Team Member` PICTURE shape.

| Shape name | Content |
|---|---|
| `Digital Design Strategy` | Service line (footer) |
| `Project Name` | Project name (footer) |
| etc. | Standard footer shapes |

---

## Footer shapes (Variants 1–5, 7)
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
| 1 (Individual + photo) | Key lead introduction |
| 2 (Composition table) | Staffing plan with monthly allocation |
| 3 (Grid 7) | Full team overview with photos |
| 4 (Org structure) | Reporting lines / team governance |
| 5 (Detailed bio) | Appendix CVs for key personnel |
| 6 (Full-page profile) | Feature profile for C-level or lead |
| 7 (Grid 5) | Smaller team overview |

## Usage Rules
- Always replace placeholder names ("Name Surname") and roles ("Role / Position").
- Replace `CV Photo` and `Team Member` PICTURE shapes with real member photos.
- For Variant 2, ensure all `M1–M4` columns reflect the actual engagement calendar.
- Never leave filler text in any `member-name` or `member-role` shape.
