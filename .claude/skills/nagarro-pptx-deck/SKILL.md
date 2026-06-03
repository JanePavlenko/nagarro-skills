---
name: nagarro-pptx-deck
description: Build a branded Nagarro presentation deck as a .pptx file. Use this skill whenever a user asks to create a PowerPoint, slide deck, presentation, or .pptx for Nagarro — even if they just say "make me a deck about X" or "build slides". Triggers: powerpoint, pptx, slides, presentation, deck, .pptx.
---

You build Nagarro-branded .pptx files using the official section templates.
Every slide is copied from a pre-built section file using `copy_slide_from()`.
You never build slides from scratch.
You collect a full brief before writing any code.

---

## Brand anchor

Before collecting the brief or building anything, read:
- `brand/design-system.md` — colours, typography, layout rules
- `brand/positioning.md` — Nagarro's core message and value proposition

Section template files live at:
`slide-decks/powerpoint/sections/` (in this repo — all 16 .pptx files are present)

Per-slide layout rules live at:
`slide-decks/powerpoint/rules/` — read the relevant `.md` file before placing each slide type.

---

## Step 1 — Collect the brief

Ask for missing inputs using `AskUserQuestion`. You need:

1. **Topic / title** — what is the deck about?
2. **Audience** — new prospect, existing client, internal team, or C-suite?
3. **Deck type** — Capability, Proposal, Internal, Recruitment?
4. **Length** — short (6–8 slides), standard (12–15), long (20–30)?
5. **Project / client name** — footer "Project Name" field
6. **Month and year** — footer "Month Year" field (e.g. "June 2026")
7. **Service line** — footer "Digital Design Strategy" replacement (e.g. "Internal", "Capability Pitch")
8. **Key messages** — 3–5 themes to cover

---

## Step 2 — Plan the slide sequence

Produce a numbered slide plan. For each slide, state which section file and slide index to use.

### Available section files
| File | Contents |
|---|---|
| `cover.pptx` | Cover slides (2 variants) |
| `index.pptx` | Index slides (4 variants) |
| `chapter-cover.pptx` | Chapter cover slides (3 variants) |
| `confidentiality-statement.pptx` | 3 variants |
| `content.pptx` | Content slide |
| `executive-summary.pptx` | 4 variants |
| `a-note-from-us.pptx` | 5 variants |
| `highlights.pptx` | 7 variants |
| `infographics.pptx` | 9 variants |
| `diagrams.pptx` | 7 variants |
| `tables.pptx` | 2 variants |
| `timelines.pptx` | 4 variants |
| `about-nagarro.pptx` | 10 variants |
| `why-nagarro.pptx` | 4 variants |
| `our-partners.pptx` | 6 variants |
| `assumptions.pptx` | 2 variants |
| `team.pptx` | 7 variants |
| `outro.pptx` | 1 slide |

### Index slide rule
Include an Index slide only when **both** apply:
- Chapter count ≥ 2
- Total slide count ≥ 15

Otherwise skip it. Go Cover → first content slide directly.

### Diagram slide rule
Never place a Diagram slide without real content for every visible node.
Drop or substitute with a text-based slide.

### No placeholder copy
Never ship: `Lorem ipsum`, `Title`, `Subtitle`, `Bullet Point 1/2/3`,
`This is a paragraph`, `small note`, `Server`, `Your title goes here`.

---

## Step 3 — Confirm the plan

Present the numbered slide plan and wait for explicit approval before writing code.

---

## Step 4 — Build the .pptx

Write and run a Python script using python-pptx.

### Required implementation pattern

```python
import os, copy, itertools, zipfile
from lxml import etree
from pptx import Presentation
from pptx.opc.package import Part
from pptx.opc.packuri import PackURI

SECTIONS = 'slide-decks/powerpoint/sections'
_img_counter = itertools.count(1)

def copy_slide_from(src_path, slide_idx, dst_prs):
    src_prs = Presentation(src_path)
    src_slide = src_prs.slides[slide_idx]
    new_slide = dst_prs.slides.add_slide(dst_prs.slide_layouts[0])
    IMAGE_TYPES = {
        'http://schemas.openxmlformats.org/officeDocument/2006/relationships/image',
        'http://schemas.openxmlformats.org/officeDocument/2006/relationships/media',
    }
    rId_map = {}
    for rId, rel in src_slide.part.rels.items():
        if not rel.is_external and rel.reltype in IMAGE_TYPES:
            try:
                new_rId = new_slide.part.relate_to(rel.target_part, rel.reltype)
                rId_map[rId] = new_rId
            except Exception as e:
                pass
    src_spTree = copy.deepcopy(src_slide.shapes._spTree)
    xml_str = etree.tostring(src_spTree, encoding='unicode')
    for old, new_id in rId_map.items():
        xml_str = xml_str.replace('r:embed="%s"' % old, 'r:embed="%s"' % new_id)
        xml_str = xml_str.replace('r:id="%s"' % old, 'r:id="%s"' % new_id)
    new_spTree = etree.fromstring(xml_str)
    dst_spTree = new_slide.shapes._spTree
    dst_spTree.getparent().replace(dst_spTree, new_spTree)
    return new_slide

def dedup_pptx(path):
    entries = {}
    with zipfile.ZipFile(path, 'r') as z:
        for info in z.infolist():
            entries[info.filename] = z.read(info.filename)
    tmp = path + '.tmp'
    with zipfile.ZipFile(tmp, 'w', zipfile.ZIP_DEFLATED) as z:
        for name, data in entries.items():
            z.writestr(name, data)
    os.replace(tmp, path)

A_NS = 'http://schemas.openxmlformats.org/drawingml/2006/main'

def replace_text(slide, replacements):
    root = slide.part._element
    for el in root.iter():
        if el.tag.endswith('}cNvPr') and 'name' in el.attrib:
            name = el.attrib['name']
            if name in replacements:
                parent = el.getparent()
                while parent is not None and not parent.tag.endswith('}sp'):
                    parent = parent.getparent()
                if parent is not None:
                    t_els = parent.findall('.//{%s}t' % A_NS)
                    if t_els:
                        t_els[0].text = replacements[name]
                        for t in t_els[1:]:
                            t.text = ''
```

### Base presentation — never blank
Start from a blank `Presentation()` with template dimensions:
```python
prs = Presentation()
prs.slide_width  = 18288000  # 2000px at 9144 EMU/px
prs.slide_height = 10287000  # 1125px at 9144 EMU/px
```

### Footer on every slide
```python
FOOTER = {
    "Digital Design Strategy": "SERVICE_LINE",
    "Project Name":            "PROJECT_NAME",
    "Month Year":              "MONTH_YEAR",
}
replace_text(slide, FOOTER)
```

### Output
Save to `output/DECK-NAME-MONTH-YEAR.pptx` and run `dedup_pptx()` after saving.

---

## Step 5 — Verify

After running, confirm:
- Correct slide count
- No placeholder text in any shape
- File opens without corruption

Report the output path when done.
