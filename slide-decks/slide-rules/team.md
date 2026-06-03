# Team Slides

## Overview
Slides introducing the Nagarro team involved in the project. Includes group team views, org structure, team composition table, and individual member profiles. All variants are light by default.

## Light / Dark Mode
All variants support light and dark mode. Mode can be switched per slide via variables.

## Header & Footer
Information not confirmed — verify in Figma before use.

## Components Used

### Role Badge
A small component used in the Team Structure slide (v3). Has two variants:
- **Team** — group icon, used to represent a team or department
- **User** — single person icon, used to represent an individual role
- Role/position label to the right of the icon in both variants
- No name — roles only, no individuals
- Used to represent a position within the team structure

---

## Variants

### Team - 5 Members / Light
- Displays 5 team members in a row
- Each member: rounded photo + name and surname on one line below + role/position on the line below that
- All centered horizontally
- Minimum: 2 members. Maximum: 5 members (use Team - 10 Members for larger teams)

### Team - 10 Members / Light
- Displays up to 10 team members
- Same layout as the 5-member variant (rounded photo + name + role)
- All centered horizontally
- Minimum: 2 members. Maximum: 10 members

### Team Structure / Light
- Slide title: "Team Structure", aligned to the top left
- Below the title: two horizontal rectangles stacked, one above the other
- Inside each rectangle: Role Badge components aligned to the right, arranged in two rows
- The second rectangle contains the Nagarro logo
- No individual names — roles only
- Use to show the team's organisational structure

### Team Composition / Light
- Slide title: "Team Composition", aligned to the top left
- Below the title: a table with 9 columns
  - Columns: Role, Location, M1, M2, M3, M4, M5, M6, UAT/LIVE
  - M1–M6 likely represent project months/milestones; UAT/LIVE marks go-live phase
  - Number of rows = number of roles + 1 header row
- Use to show staffing plan over time

### Team Member - Bio + Photo / Light
- Slide title: person's name; subtitle: their role/position
- Content area divided into:
  - Left 2/3: "About" section + stats
  - Right 1/3: vertical photo of the person, filling the full vertical space
- Use for individual team member profiles

### Team Member - Bio + Skills + Photo / Light
- Same as above with an additional column for skills, software, and industry experience (bullet points)
- Photo does not take the full vertical space — it respects the grid constraints
- Three content columns total: bio + stats | skills/software/industry | photo

### Team Member - Bio, No Photo / Light
- Focuses on text only — no photo
- Title: person's name; subtitle: their role/position
- Content organised in 2 equally distributed columns
- Title and subtitle sit above the two columns
- Use when no photo is available or when a photo is not appropriate

---

## When to Use
- Use in any deck where the client needs to know who will be working with them — most common in proposals, SOW responses, and project kick-offs
- Triggered by brief content such as: "the team", "meet the team", "our people", "staffing plan", "org structure"
- Choose variant based on what information is available and what the audience needs:
  - **Team - 5 Members**: default for most decks — shows up to 5 people with photo, name, and role
  - **Team - 10 Members**: use for larger delivery teams where showing every person matters
  - **Team Structure**: use when the client needs to understand reporting lines and team organisation, not individual bios
  - **Team Composition**: use in proposals where the staffing plan over time (roles per month) is part of the commercial offer
  - **Team Member - Bio + Photo**: use for key people (account lead, project manager) who warrant individual introduction
  - **Team Member - Bio + Skills + Photo**: use when skills, software, or industry experience are decision-relevant (technical proposals)
  - **Team Member - Bio, No Photo**: use when no photo is available or when a photo-free format is more appropriate

## Usage Rules
- Do not use the "Team — example" frames — they are reference examples only, not templates
- For team member slides, source photos from Local Components → CV Photos
- For Team Structure: use Role Badge components from Local Components
- The Team Composition table columns (M1–M6, UAT/LIVE) represent project timeline phases — fill in accordingly per project
- Choose between 5-member and 10-member variants based on team size; both support as few as 2 members
