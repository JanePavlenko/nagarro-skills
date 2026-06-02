---
name: nagarro-email-cover
description: Create a branded Nagarro email or event banner/cover image in Figma. Use this skill whenever a user asks to make a cover, banner, or header image for an email, newsletter, webinar, session, event, or announcement — even if they just say "make me a cover for X" or "create a banner for this event". Triggers: email cover, event cover, banner, email header, newsletter cover, session cover, webinar banner, event image.
---

You create Nagarro AI Sandbox Sessions–style email and event covers in Figma.
Output: a 1400×400px Figma frame with a deep purple gradient background.
You collect a full brief before building anything.

---

## Brand anchor

Before anything, read:
- `brand/design-system.md` — colour tokens, typography, logo usage
- `brand/tone-of-voice.md` — headline style (bold, human, direct; no buzzwords)

### Cover style (fixed — do not deviate)
| Element | Spec |
|---|---|
| Canvas | 1400×400px |
| Background | Deep purple gradient: `#1A0533` → `#2D0F5C` (left to right) |
| Headline | Equip Extended Black, white, 48–64px depending on length |
| Category tag | Optional teal pill: `#47D7AC` with dark text |
| Speaker photo | Optional — right side, circular crop |
| Decorative element | Optional geometric / abstract visual, right side |
| Logo | Nagarro horizontal white logo, top-left or bottom-left |

---

## Step 1 — Collect the brief

Ask using `AskUserQuestion`. You need:

1. **Event / session title** — the main headline text
2. **Category tag** — optional (e.g. "AI Sandbox Sessions", "Webinar", "Workshop")
3. **Date and time** — optional, shown as a sub-line
4. **Speaker name(s)** — optional
5. **Decorative visual** — optional description or "none"
6. **Figma file** — which file to create the cover in (or create a new page)

---

## Step 2 — Confirm the design direction

Summarise the cover layout and confirm with the user before building.

---

## Step 3 — Build in Figma

Use the `use_figma` MCP tool to run a JavaScript build script.

### Frame setup
```javascript
const frame = figma.createFrame();
frame.name = 'email-cover-EVENT_TITLE';
frame.resize(1400, 400);
```

### Purple gradient background
```javascript
frame.fills = [{
  type: 'GRADIENT_LINEAR',
  gradientTransform: [[1, 0, 0], [0, 1, 0]],
  gradientStops: [
    { position: 0, color: { r: 0.102, g: 0.020, b: 0.200, a: 1 } },
    { position: 1, color: { r: 0.176, g: 0.059, b: 0.361, a: 1 } },
  ]
}];
```

### Typography
- Headline: `Equip Extended`, `Black`, white, 48–64px
- Sub-line: `Equip`, `Regular`, white at 70% opacity, 20px
- Category tag: `Equip`, `Medium`, `#01071600` dark, 14px; pill background `#47D7AC`

### Layer naming
Name every layer descriptively (kebab-case). No `Frame 123`, `Rectangle`, `Group 4`:
- `cover-background`
- `cover-headline`
- `cover-subline`
- `cover-category-tag`
- `cover-logo`
- `cover-decoration`

---

## Step 4 — Verify

Take a screenshot, confirm headline text, colours, and no placeholder copy.
Report the Figma node URL.
