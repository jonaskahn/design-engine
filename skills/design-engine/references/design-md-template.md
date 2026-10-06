# DESIGN.md Template

Skeleton for the handoff's DESIGN.md section, following the Google Labs DESIGN.md spec (`version: alpha`, still changing; check https://github.com/google-labs-code/design.md before relying on details).

## Rules

- YAML front matter holds the normative token values; prose explains how to apply them. Both must agree.
- Section order is fixed: Overview, Colors, Typography, Layout, Elevation & Depth, Shapes, Components, Do's and Don'ts. Omit a section only by omitting it entirely, and never repeat a heading (a duplicate heading rejects the file).
- Token groups: `colors` (any CSS color; define at least `primary`), `typography` (`fontFamily`, `fontSize`, `fontWeight`, `lineHeight`, `letterSpacing`, `fontFeature`, `fontVariation`), `rounded`, `spacing`, `components`. Dimensions use `px`, `em`, or `rem`.
- Component properties: `backgroundColor`, `textColor`, `typography`, `rounded`, `padding`, `size`, `height`, `width`. Variants are separate keys such as `button-primary-hover`.
- Reference tokens as `{colors.primary}`. Outside `components`, a reference must point to a single value, not a group.
- Locked values are copied exactly. Values not yet decided are written `TBD` in prose and left out of the YAML; never invent a hex value or typeface to fill a gap.
- Token values must match the Final Prompt's visual system exactly.
- The `Do's and Don'ts` list is the same anti-slop list as the Final Prompt's Avoid item — same items, not a second list.
- When a DESIGN.md already exists, output the merged file: preserve every existing token unless a higher-precedence rule in `SKILL.md` overrides it, and mark each addition with a trailing YAML comment (`# added`). An overridden value gets a comment naming the source (`# overridden by user instruction`). The spec defines no marker of its own; YAML comments are legal in the front matter.
- Dark theme: add `colors` entries with a `-dark` suffix (for example `surface-dark`) when both themes ship, and describe the mapping under Colors.

## Skeleton

```markdown
---
version: alpha
name: <project name>
description: <one sentence>
colors:
  primary: "<hex>"
  secondary: "<hex>"
  neutral: "<hex>"
  surface: "<hex>"
  on-surface: "<hex>"
  accent: "<hex>"
  error: "<hex>"
typography:
  display:
    fontFamily: <family>
    fontSize: <px>
    fontWeight: <number>
    lineHeight: <number>
    letterSpacing: <em>
  body:
    fontFamily: <family>
    fontSize: <px>
    fontWeight: <number>
    lineHeight: <number>
rounded:
  sm: <px>
  md: <px>
spacing:
  sm: <px>
  md: <px>
  lg: <px>
components:
  button-primary:
    backgroundColor: "{colors.accent}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.md}"
    padding: <px>
---

## Overview
<character, audience, what the interface should feel like, in visible terms>

## Colors
<role of each color, light/dark mapping, contrast notes>

## Typography
<families, licensing/fallback, hierarchy, reading character>

## Layout
<grid, spacing scale, density, responsive behavior>

## Elevation & Depth
<how surfaces separate: tone, border, or shadow>

## Shapes
<radius scale and where each applies>

## Components
<buttons, inputs, cards, navigation, states>

## Do's and Don'ts
- Do: <rules that keep the design consistent>
- Don't: <the unchosen anti-slop tells from the Final Prompt's Avoid list, plus brand-specific prohibitions>
```
