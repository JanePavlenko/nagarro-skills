# Index Slide

## Overview
Table of contents slide. Lists the chapters/sections of the deck. All variants are dark by default. One variant (v7) has been deprecated and should not be used.

## Light / Dark Mode
All variants support light and dark mode. Mode can be switched per slide via variables.

## Header & Footer
- **With header + footer (default):** v4, v5, v10
- **No header, no footer:** v1, v2, v3, v6, v8, v9
- When in doubt, prefer variants that include header and footer.

## Variants

### Index - 9 Items, Title Only, Title Center Left / Dark
- "Index" title is vertically centered on the left
- Lists up to 9 items: chapter number + chapter title only
- No subtitles, no page numbers
- No header or footer

### Index - Title + Page Number, Title Top Left / Dark
- "Index" title aligned to the top left
- Items show chapter title + the page they start at
- No chapter numbers, no subtitles
- No header or footer

### Index - 10 Items, Title + Subtitle, Title Bottom Left / Dark
- "Index" title aligned to the bottom left
- Lists up to 10 items: chapter number + title + subtitle
- No header or footer

### Index - 12 Items, Title + Subtitle, Bottom Right / Dark
- "Index" title aligned to the top left
- Lists up to 12 items: chapter number + subtitle, aligned to the bottom right
- Includes header and footer

### Index - 12 Items, Mint Titles, Bottom Left / Dark
- Similar to the above but items sit right below the title, aligned to the bottom left
- Item title color is `Colors/Mint Green/400`
- Includes header and footer

### Index - 6 Items, Large Numbers / Dark
- "Index" title aligned to the top left
- Lists up to 6 items: no subtitles
- Chapter numbers are large and in `Colors/Mint Green/600`
- No header or footer

### Index - Items + Pages, Top Right / Dark
- Items aligned to the top right
- Each item shows: chapter number, title, subtitle, and page number for the subtitle
- No header or footer

### Index - Items + Pages, Bottom Left / Dark
- Items sit right below the "Index" title, aligned to the bottom left
- Each item shows: chapter number, title, subtitle, and page number for the subtitle
- No header or footer

### Index - Large Chapter Numbers / Dark
- Large chapter numbers in `Colors/Mint Green/600`
- Shows chapter titles alongside the numbers
- Includes header and footer

## When to Use

**Inclusion threshold — include an Index only when BOTH apply:**
- The deck has **2 or more chapters** (Chapter Cover slides)
- The deck has **15 or more total slides**

If the deck has only 1 chapter, or fewer than 15 slides, **skip the Index entirely**. Go straight from Cover to the first Chapter Cover (or first content slide). A short deck with a sparse Index reads as unfinished.

When the Index *is* included, it sits as the second slide, right after the Cover.

## Variant selection

Always pick the **smallest fitting variant** for the actual chapter count and content shape. Do not select a 12-item template for 3 chapters.

| Content shape | Preferred variant |
|---|---|
| Subtitles provided in brief, ≤10 chapters | `Index - 10 Items, Title + Subtitle, Title Bottom Left / Dark` |
| Subtitles provided, 11–12 chapters | `Index - 12 Items, Title + Subtitle, Bottom Right / Dark` |
| Page numbers requested | `Index - Items + Pages, Top Right / Dark` or `Index - Items + Pages, Bottom Left / Dark` |
| Title only, ≤6 chapters | `Index - 6 Items, Large Numbers / Dark` or `Index - Large Chapter Numbers / Dark` |
| Title only, 7–9 chapters | `Index - 9 Items, Title Only, Title Center Left / Dark` |
| Title only, 10–12 chapters | `Index - 12 Items, Mint Titles, Bottom Left / Dark` |

## Chapter source
- Auto-derive the chapter list from the Chapter Cover slides in the plan, in order
- The brief can override titles, order, or supply subtitles / page numbers

## Usage Rules
- Apply the inclusion threshold above before adding an Index to the plan
- After populating real chapters, blank out every unused row (clear both the number and title text layers) — never ship a slide with leftover "02 Title" placeholders. Use the `populateIndex` helper documented in `skills/figma-deck-builder/SKILL.md` Step 4
- v7 has been deleted from the Figma file — do not reference it
- Use variants with header and footer by default unless a specific layout reason exists
- The index slide, when included, is the second slide in the deck, after the cover
