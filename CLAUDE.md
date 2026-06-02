# Nagarro Skills — Claude Rules

This repo contains **standalone skills** for producing Nagarro-branded outputs.
Each skill is self-contained: it collects its own brief, enforces brand consistency,
and produces the final deliverable without relying on an agent team.

---

## 1. Brand foundation — always read first

Every skill must read the relevant brand docs before producing anything:

| Doc | Used by |
|---|---|
| `brand/tone-of-voice.md` | All copy skills (LinkedIn, internal comms, marketing) |
| `brand/design-system.md` | All visual skills (Figma deck, PowerPoint deck, email cover) |
| `brand/positioning.md` | All skills — Nagarro's core message and value prop |

**Never invent colours, fonts, tone, or layouts.** Always check brand docs first.

---

## 2. No Lorem ipsum — anywhere, ever

Placeholder copy is never shipped in any deliverable. This applies to every skill:
- No `Lorem ipsum`, `dolor sit amet`, `consectetur`
- No `Title`, `Subtitle`, `Body text`, `Bullet Point 1/2/3`
- No `This is a paragraph`, `small note`, `Server`, `Your title goes here`

When real content is missing: **ask the user**, **drop the section**, or **use a simpler template**.
Never invent content. Never leave template defaults in place.

---

## 3. Brief collection — always guide the user

Each skill must collect a complete brief before producing anything.
Ask for missing inputs using `AskUserQuestion`. Never start building until you have:
- What the output is for (topic / purpose)
- Who the audience is
- Any specific content, data, or constraints

---

## 4. Skills in this repo

| Skill | Trigger |
|---|---|
| `nagarro-figma-deck` | Build a presentation deck in Figma |
| `nagarro-pptx-deck` | Build a presentation deck as a .pptx file |
| `nagarro-email-cover` | Create an email or event banner/cover |
| `nagarro-linkedin-post` | Write a LinkedIn post for Nagarro |
| `nagarro-marketing-campaign` | Plan an external marketing campaign |
| `nagarro-internal-comms` | Write an internal letter or announcement |

---

## 5. Git rules

- Always `git pull --rebase` before pushing
- Never commit personal draft output files
- Commit skill files and brand docs — not generated deliverables
