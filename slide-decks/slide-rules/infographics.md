# Infographics Slides

## Overview
Data visualisation slides — charts, diagrams, and visual data summaries. Used wherever the deck needs to show numbers, proportions, comparisons, trends, or conceptual relationships. All variants are light by default.

## Light / Dark Mode
All variants support light and dark mode. Mode can be switched per slide via variables.

## Header & Footer
Information not confirmed for every variant — verify in Figma before use. Most variants include the standard Layout instance, which carries header and footer.

---

## Variants

### Infographic - Donut Chart / Light
- Large donut chart centred on the slide, headline percentage displayed inside the hollow centre
- Variable number of segments (as few as 2, as many as needed) in mint/teal/navy tones
- Each segment has a legend item positioned around the chart: name + short description
- No slide title — the chart is the full content of the slide
- Use when you want to show **how a whole breaks down into parts** and one segment or the total is the headline number
- *Note: the Figma layer is currently named `Infographic-piechart` — rename to match this convention*

### Infographic - Horizontal Bar, Segmented / Light
- One full-width horizontal bar divided into coloured segments (mint tones + navy)
- Percentage label sits above each segment
- Legend with colour swatch + description for each segment, positioned in the lower-left
- Top half of the slide is intentionally empty — use it for a slide title or supporting copy
- Use to show **how a total splits across categories** as proportional horizontal segments, each with its own percentage
- *Note: the Figma layer is currently named `Infographic-singlelinechart-withpercentages` — this is a misnomer; rename to match this convention*

### Infographic - Vertical Bars + Copy / Light
- Split layout: large headline + body copy on the left (~40% width), stacked vertical bar chart on the right (~60% width)
- Each bar is divided into **two coloured segments** (mint + navy); the two colours can represent any two stacked values (not limited to before/after comparisons)
- Bar labels sit below each bar; legend at the bottom identifies the two colours
- Use when you need to **combine a narrative statement with comparative bar data** on the same slide

### Infographic - Proportional Circles / Light
- Three overlapping circles of different sizes (small navy, medium light-mint, large bright-mint)
- Each circle contains: topic name, percentage, short description
- Short copy paragraph in the top-left corner
- The overlap between circles is **purely visual** — it conveys relative scale between topics, not intersection or shared meaning
- Use to show **three topics of different magnitude** where size itself is the message (e.g. market sizes, adoption rates, impact levels)

### Infographic - Vertical Bars, Ranked / Light
- Split layout: headline + body copy on the left, 3 vertical bars on the right
- Bars are ranked by height (tallest = largest value) and each uses a distinct colour (navy, medium-mint, light-mint)
- **Percentage sits above each bar**; topic name + short description are displayed **inside** the bar itself — no separate legend
- Use when you want to **rank three topics by magnitude** and each topic needs a label and a brief explanation alongside its value

### Infographic - Horizontal Bar Chart + Copy / Light
- Split layout: headline + body copy + legend on the left, multiple horizontal bars on the right
- Each bar represents one item; bar length reflects its value; bars are colour-coded across up to 4 categories using mint/grey/navy tones
- Legend in the lower-left maps colours to category descriptions
- Number of bars is flexible — remove or add rows as needed
- Use for **ranked or categorised comparisons** across many items (e.g. market share by country, performance by team, adoption by region)
- *Note: this slide physically lives in the "Our Partners" Figma page but is not limited to partner content — use it for any multi-item ranked bar chart*
- *Note: the Figma layer is currently named `Our Partners - Infographic, Bar Graph / Light` — consider renaming*

### Infographic - Line Graph + Copy / Light
- Split layout: headline + body copy on the left, line chart on the right
- Single dashed upward-trending line with Y-axis labels (time periods: weeks, months, quarters, etc.) and two data points marked with circles
- Large headline metric (e.g. "+132%") with a short label (e.g. "Growth") displayed prominently at the bottom-right of the chart area
- Use to show **a single trend over time** with one key growth or change metric called out
- *Note: this slide physically lives in the "Our Partners" Figma page but is not limited to partner content — use it for any single-metric trend story*
- *Note: the Figma layer is currently named `Our Partners - Infographic, Line Graph / Light` — consider renaming*

### Infographic - Venn Diagram, 3 Circles / Light
- Split layout: large headline + body copy on the left, 3 overlapping light-mint circles arranged in a triangle on the right
- Each circle has a **Topic + Description** label; the intersection area also has a label — the overlap carries meaning
- Use when you need to show **three topics that share a common area** and the intersection is part of the story (e.g. three capabilities that converge, three audiences that overlap)

### Infographic - Venn Diagram, 2 Circles / Light
- Headline + body copy fills the top portion of the slide; two large overlapping circles sit at the bottom (partially cropped at slide edge)
- Three **Topic** labels: one for the left circle, one for the intersection, one for the right circle
- The intersection label makes the overlap meaningful — not just decorative
- Use for **binary overlap stories** where two distinct things share a middle ground (e.g. design × engineering, business × technology, two audience segments with shared needs)

### Infographic - Layer Stack + Copy / Light
- Split layout: large headline + body copy on the left, isometric stacked layers diagram on the right
- Each layer is a diamond/parallelogram shape in mint green; a callout line connects each layer to a label on the right (bold name + short description)
- Number of layers is flexible — the default example shows 6 but the structure can represent **any layered hierarchy**: tech stacks, business model tiers, service layers, design system architecture, organisational levels, etc.
- Use when you need to show a **stack or hierarchy where each level has a distinct role** and all levels together form a complete system
- *Note: the Figma layer is currently named `Infographic-layers` — rename to match this convention*

### Infographic - 3 Icons + Copy / Light
- Slide title + body copy at the top (~40% of slide height)
- Three equally-spaced columns at the bottom, each with: a mint abstract icon, a bold label, and a short description paragraph
- Use for **three-pillar or three-capability summaries** where each pillar needs a visual icon alongside a short explanation
- *Note: the Figma layer is currently named `Infografic-3icons` — typo (`Infografic`) needs fixing when renaming*

### Infographic - Bars / Light
- Bar chart with a `Copy` frame and a legend (4 items)
- *Layout details to be confirmed visually — description inferred from Figma structure*

---

## When to Use
- Use whenever a number, proportion, comparison, trend, or relationship is clearer as a visual than as text or a table
- Triggered by brief content such as: "show the data", "breakdown", "proportions", "growth", "comparison", "how it works", "three pillars", "relationship between"
- Can appear anywhere in the deck where data needs a visual anchor — not tied to a single section
- Choose variant based on the data structure and story:
  - **Donut Chart**: use when a total breaks into parts and one segment or the whole is the headline (e.g. "65% of projects delivered on time")
  - **Horizontal Bar, Segmented**: use when a 100% total splits across categories shown as proportional horizontal segments
  - **Vertical Bars + Copy**: use when you need a narrative statement alongside comparative bar data on the same slide
  - **Proportional Circles**: use when three topics have very different magnitudes and size itself is the message
  - **Vertical Bars, Ranked**: use to rank exactly three topics by magnitude with labels and explanations inside each bar
  - **Horizontal Bar Chart + Copy**: use for ranked or categorised comparisons across many items (5+)
  - **Line Graph + Copy**: use to show a single trend over time with one key growth metric called out
  - **Venn Diagram, 3 Circles**: use when three topics converge and the intersection carries meaning
  - **Venn Diagram, 2 Circles**: use for binary overlap stories where two things share a meaningful middle ground
  - **Layer Stack + Copy**: use when components stack in a hierarchy and each layer has a distinct role
  - **3 Icons + Copy**: use for three-pillar summaries where each pillar needs an icon and short explanation

## Usage Rules
- Prefer the variant whose chart type matches the data — do not retrofit a different chart by editing shapes
- The number of segments, bars, or circles is flexible within each variant (except where noted) — add or remove as needed
- For Venn diagrams, the intersection area must always carry a label — do not use overlapping circles as purely decorative
- If a chart needs a colour that isn't in the existing palette (mint, petrol, navy, purple, yellow accents), flag it rather than inventing a token
