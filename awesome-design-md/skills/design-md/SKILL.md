---
name: design-md
description: Use when asked to build or restyle a UI to match a specific company's or product's visual design (e.g. "make this look like Stripe" or "give it an Apple-style design") - provides a library of pre-extracted DESIGN.md design system references
---

# design-md

## Overview

This plugin bundles 75 `DESIGN.md` files, each a plain-text design system extracted from a real product or website (`design-md/<company>/DESIGN.md`). A `DESIGN.md` follows the [Stitch DESIGN.md format](https://stitch.withgoogle.com/docs/design-md/specification/): visual theme, color palette with semantic roles, typography hierarchy, component stylings, layout/spacing rules, elevation/shadow system, do's and don'ts, responsive behavior, and an agent prompt guide.

Use this skill whenever a user wants generated or restyled UI to visually match a specific brand or product, instead of guessing at colors and fonts from memory.

## Process

1. **Find the reference.** List `design-md/` (in this plugin's directory) to see available companies, or grep for the name the user mentioned. Available companies include: Stripe, Apple, Figma, Notion, Tesla, Airbnb, Linear, Vercel, Slack, Spotify, Shopify, and dozens more — see `README.md` in this plugin for the full catalog.
2. **If no match exists**, tell the user this company isn't in the bundled library and either pick the closest available reference or ask them to provide their own `DESIGN.md`/site to base it on. Do not invent design tokens from vague memory of a brand.
3. **Read the matched `DESIGN.md` in full** before writing any UI code. Do not skim — the color hex values, spacing scale, and component states in section 2-6 are what makes the output actually match.
4. **Apply it consistently**: use the exact hex values and semantic roles from the palette, the specified font stack and type scale, the stated spacing/grid unit, and the shadow/elevation rules — for every component you generate, not just the first one.
5. **Respect the Do's and Don'ts section** — these call out anti-patterns specific to that design language (e.g. rounded corners that would look wrong, animations that clash with the brand).
6. **Check responsive rules** (breakpoints, touch targets, collapsing strategy) before finalizing layouts for multiple screen sizes.

## Notes

- These are read-only reference documents, not code to execute.
- A copy of the matched `DESIGN.md` can be dropped into the user's project root if they want other tools/agents to pick up the same design language later.
