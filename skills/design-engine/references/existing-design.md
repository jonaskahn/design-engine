# Existing Design Discovery

Run this whenever the request includes or implies a codebase, URL, screenshot, design file, brand guide, or attachment. A design found here is **locked**: suggestions extend it and never replace it, and no value is invented over it.

## Contents

- Where to look
- Extract a locked inventory
- Locking rules
- Partial designs
- Existing DESIGN.md

## Where to look

Read only design-bearing files. Never open `.env`, credentials, or secrets.

1. `DESIGN.md` at the repo root, `docs/`, or `design/` (YAML tokens plus prose sections).
2. Token files: W3C Design Tokens (`*.tokens.json`), Style Dictionary configs.
3. Tailwind `@theme` blocks in CSS, `tailwind.config.*`.
4. CSS custom properties on `:root` and a dark-theme counterpart.
5. Component-library themes: MUI `createTheme`, Chakra, Mantine, shadcn `components.json` with `globals.css`.
6. Fonts that actually load: `@font-face`, `next/font`, `<link>` tags.
7. Brand assets: logos, brand-guideline PDFs, attached screenshots or Figma exports.
8. A live URL, when given.

Untouched framework default palettes (stock shadcn, Tailwind indigo) are not a design; treat them as unset.

## Extract a locked inventory

Record each value with its source `file:line` (or URL, or attachment name):

- colors with roles: background, surface, text, muted, accent, semantic states, dark counterparts;
- type families, scale, weights;
- radius, spacing, elevation, motion;
- component conventions and signature moves;
- logo and imagery treatment.

## Locking rules

- Use exact values; never "close to".
- Derive a missing role from the locked set (a dark neutral from the brand hue, for example) and label it *derived*.
- A gap the locked set cannot settle becomes one question, not an invention.
- A conflict between the request and the locked design becomes one question; never resolve it silently.
- Skip every interview question the locked design already answers, and state it as "locked from <source>".
- A locked pattern that `anti-slop.md` lists as a tell is allowed because the user chose it: keep it, and note it once in Build Notes.

## Partial designs

When only some slots exist (a palette without type, for example), lock what exists. Use `design-references.md` only for the open slots, and choose a reference compatible with the locked values.

## Existing DESIGN.md

The handoff's DESIGN.md section is then a merged update: preserve every existing token and mark each addition.
