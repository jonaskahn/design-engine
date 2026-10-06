# Redesign Overlay

Use when the user wants to improve an existing page, screen, or template. This is an overlay, not a standalone branch: read this file **plus** the core reference for the surface being redesigned (for example `ecommerce.md` for a storefront, `content-docs.md` for a documentation site, `application-ui.md` for a dashboard). The chosen core's required context, decision catalog, and required states still apply — this file adds only what redesigning changes about the interview.

## Contents

- Inspect before interviewing
- Required context
- Branch decisions (preserve, improvement, depth, layout, navigation, color, typography, cards, imagery)
- Output emphasis

## Inspect before interviewing

If the user supplied a URL, screenshot, design file, or codebase, inspect it before asking design questions: extract the design with `existing-design.md` and lock it. Also record:

- current structure and hierarchy;
- recognizable brand elements;
- content and functionality that already work;
- clarity, conversion, responsiveness, consistency, and accessibility problems;
- technical or content constraints visible in the source.

If no source is available, request one when visual fidelity or preservation matters. Continue with explicitly labeled assumptions if the user cannot provide it.

## Required context

Missing facts to collect:

- why the redesign is happening;
- target audience and primary action;
- what must remain unchanged;
- what may change;
- available assets and brand rules;
- desired redesign depth;
- implementation or platform constraints.

## Branch decisions

### Preserve

Allow multiple selections:

- Brand colors
- Logo or recognizable brand elements
- Existing information architecture or page structure
- Existing copy
- Existing functionality or workflows
- Nothing must be preserved

Call out conflicts between preservation requirements and the requested improvement.

### Primary improvement

- Feel more premium
- Become clearer and easier to scan
- Feel more current
- Convert more effectively
- Work better on mobile
- Improve task efficiency
- Improve accessibility
- Custom outcome

Translate subjective improvements into observable interface changes and acceptance criteria. When "Improve accessibility" is selected, escalate the gated accessibility-target question from `shared-intake.md` rather than leaving it at the silent default.

### Redesign depth

- Light refinement
- Clear redesign
- Strong visual reset
- Near-complete rebuild

### Layout direction

- More minimal
- More visually striking
- More steady and professional
- More product-like
- Preserve the current layout direction
- Custom direction

### Navigation

- Simple top navigation
- Transparent floating navigation
- Solid fixed navigation
- Side navigation
- Preserve the existing navigation

Ask only when navigation is present and allowed to change.

### Color treatment

- Keep most of the existing palette
- Shift darker for greater visual weight
- Shift lighter for greater clarity
- Redefine the color system

### Typography update

- Preserve current typography
- Small refinement
- Noticeable upgrade
- Full typography reset

### Card treatment

- Reduce cards
- Keep selected cards
- Preserve the current card structure
- Make the experience more card-based

### Imagery update

- Preserve most visuals
- Replace visuals with stronger assets
- Add more visual assets
- Shift toward product-led imagery

Use the shared intake for motion and device priority. Use its other categories only where the redesign leaves those choices open.

## Output emphasis

The final prompt must distinguish preserved elements from changes, describe the new hierarchy and visual system, identify responsive and accessibility improvements, and avoid silently removing existing content or functionality.
