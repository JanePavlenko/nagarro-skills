# Timeline Slides

## Overview
Slides for showing project schedules, phased plans, roadmaps, and kickoff timelines. All variants are light by default.

## Light / Dark Mode
All variants support light and dark mode. Mode can be switched per slide via variables.

## Header & Footer
Information not confirmed for every variant — verify in Figma before use. Most variants include the standard Layout instance, which carries header and footer.

---

## Variants

### Timeline - 8 Columns, High-Level Planning / Light
- 8 week columns across the full slide width
- Timeline items are thin horizontal bars (mint green) that span one or more columns
- Each bar carries a short label (e.g. "Workshop", "Sprint 2")
- Use for **high-level project planning** where you need to show a full project schedule at a glance — typically 8 or more weeks

### Timeline - 4 Columns, Block Layout / Light
- 4 week columns
- Timeline items are large rectangular blocks — each block is a **content placeholder** where the label depends on what that phase is (workshop, development phase, sprint, etc.)
- Inside each block: bold phase name at the top + "Project Steps / Points go here" helper text at the bottom, indicating the block is meant to hold bullet points or steps
- The block height is proportional to the phase duration or visual weight needed
- Use when you have **a few key phases** that each need a distinct visual block rather than a thin bar — better for detailed close-up views of a shorter period

### Timeline - Short Period, Stacked Cards / Light
- Includes a kicker line above the slide title (e.g. "Proposed Approach") and a large slide title (e.g. "MVP Kick-Off Timeline")
- Columns represent any short period unit (Day 1/2/3, Sprint 1/2/3, Phase 1/2/3, etc.) — the column label is not fixed
- Multiple mint-green cards stack vertically inside each column; number of cards per column varies
- Each card holds a **bold activity title** and a short description paragraph below it
- Use for **short-period timelines** where multiple activities happen in parallel within each period (e.g. a 5-day kickoff, a sprint plan, a workshop agenda)

---

## When to Use
- Use whenever the deck needs to show a schedule, phased plan, roadmap, or agenda over time
- Triggered by brief content such as: "project timeline", "plan", "roadmap", "phases", "schedule", "kick-off", "sprints", "milestones"
- Typically placed within the delivery approach or commercials section of a proposal
- Choose variant based on the time period and level of detail:
  - **8 Columns, High-Level Planning**: use for full project schedules of 8+ weeks shown at a glance — thin bars, minimal detail
  - **4 Columns, Block Layout**: use for a close-up view of 3–5 key phases where each phase needs its own content block (steps, deliverables)
  - **Short Period, Stacked Cards**: use for granular short-period plans (days, sprints, workshop agendas) where multiple parallel activities need to be listed within each period

## Usage Rules
- Keep the standard `Layout` instance (header and footer) on by default unless the timeline needs the full canvas
- Column labels are always editable — the template does not fix the time unit (weeks, days, sprints, phases)
- For timelines longer than one slide, continue with the same variant on the next slide; append "(cont.)" to the title
