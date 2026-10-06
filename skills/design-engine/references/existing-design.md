# Existing Design Discovery

Run this whenever the request includes or implies a codebase, URL, screenshot, design file, brand guide, or attachment. A design found here is **locked**: suggestions extend it and never replace it, and no value is invented over it.

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
- A conflict with the locked design follows the precedence order in `SKILL.md`: an explicit instruction is applied and stated once, and a request that only implies a conflict becomes one question.
- Skip every interview question the locked design already answers, and state it as "locked from <source>".

## Partial designs

When only some slots exist (a palette without type, for example), lock what exists and offer references for the open slots only, compatible with the locked values — `SKILL.md` step 4. The handoff's DESIGN.md section is then a merged update: see `design-md-template.md`.
