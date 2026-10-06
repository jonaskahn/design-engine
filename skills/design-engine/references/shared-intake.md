# Shared Intake

Catalog of decisions to draw from after the branch and core product facts are known. Ask only about unresolved decisions that will materially change the result. A locked existing design answers its own questions (see `existing-design.md`); a chosen reference design supplies the palette, type, shape, and motion choices.

## Contents

- Core fact support
- Grouping
- Composition
- Color system
- Theme strategy
- Typography
- Imagery
- Controls
- Motion
- Device priority
- Accessibility target
- Localization and text direction
- Completion check

## Core fact support

Ask for goals and audiences in free form. Offer examples only when the user needs choices, and do not force them when the real goal or audience is more specific.

## Grouping

Group related decisions instead of asking one at a time.

1. composition, organization, and density;
2. palette, theme strategy, brand dependency, and accent;
3. typography and imagery;
4. controls, motion, and device priority;
5. accessibility target and localization, only when gated.

## Composition

### Character

- Restrained and minimal
- Content-led
- Product-led
- Showcase-led
- Custom direction

Translate the character into visible decisions about hierarchy, whitespace, imagery, and emphasis. Do not leave abstract adjectives unexplained in the final prompt.

### Content organization

- A few high-priority modules
- Vertical section-by-section explanation
- Card-based modules
- Alternating editorial sections
- Timeline or process narrative
- Dense information structure
- Custom organization

### Information density

- Very spacious with little information
- Light but sufficient
- Complete but clean
- Compact and efficiency-first
- Information-dense

Reconcile organization and density when they conflict. A dense card grid and a very spacious presentation need an explicit priority.

### Card usage

- Avoid cards where possible
- Cards for one content type only (projects, proof, or summaries)
- Cards for most modules
- Custom

## Color system

### Palette direction

- Black-and-white minimal
- Deep gray with cool white
- Deep navy-black with ice blue
- Deep green-black with teal
- Deep burgundy with muted gold
- Warm brown-gray with off-white
- Pure white with cool gray
- Pale blue-gray with white
- Light neutral with a cool accent
- Light neutral with a warm accent
- Brand-color-led
- Multicolor with stronger contrast
- High-contrast color blocking
- Custom palette

Palette options are starting points for the user, not defaults to pick on their behalf. Choose from audience, content, and brand; a palette named in `anti-slop.md` is offered only when the user, a locked design, or a chosen reference supplies it.

### Brand dependency

- Independent of an existing brand
- Use the existing brand system
- Brand system is not decided yet

When an existing or custom palette is selected, collect the actual colors, tokens, or asset reference. Otherwise keep a labeled placeholder.

### Accent

Blue, cyan, green, yellow, gold, orange, red, purple, pink, existing brand color, no obvious accent, or a custom accent. Do not select an accent that undermines the requested contrast, tone, or brand constraints.

## Theme strategy

Ask in every intake, because it changes every palette decision that follows.

### Theme support

- Light mode only
- Dark mode only
- Both light and dark (recommended)

### Default behavior (if both)

- Follow system `prefers-color-scheme` with a manual override (recommended)
- Default light with a manual toggle
- Default dark with a manual toggle
- Force one mode regardless of system setting

### Dark base surface (if dark is in scope)

- Neutral dark gray (roughly `#121212`–`#1C1B1F`; avoid pure black for large surfaces)
- Pure black (OLED battery savings; watch halation on light text)
- Tinted dark derived from the brand hue (the Material 3 approach: tone-based surface roles rather than white overlays)

Reconcile the theme with the palette direction. Elevation in dark mode comes from lighter surface tones, not shadow. A palette chosen for light mode needs explicit dark neutrals, not a mechanical inversion.

## Typography

Choose two things.

**Pairing:** single sans family; serif display with sans body; sans with monospace for technical content; custom.

**Voice:** neutral, editorial, technical, warm, expressive. State the visible consequence of the voice: x-height, stroke contrast, tracking, weight range, and scale ratio.

Describe hierarchy, weight, scale, and reading character. Name a typeface only when the user supplied it, a locked design or chosen reference uses it, or licensing is understood and the target environment provides it. Never default to the typefaces listed in `anti-slop.md`.

## Imagery

- Real people or photography
- Product screenshots or interface visuals
- Pattern or texture derived from the brand's own assets
- Illustration or graphic-led visuals
- 3D visuals, only with a stated purpose
- Video or moving-image-led visuals
- Mixed photography and product visuals
- Minimal imagery with layout-led presentation
- Custom imagery direction

Record whether assets already exist. Use explicit placeholders instead of inventing photography, screenshots, or brand artwork.

## Controls

### Primary action style

- Rounded solid button
- Rounded outline button
- Square solid button
- Square outline button
- Text-only action
- Solid primary with outline secondary
- One oversized primary action with secondary actions de-emphasized
- Custom control style

For application interfaces, read this as the broader control language rather than styling every action identically. Corner radius should come from the locked or referenced shape scale.

## Motion

- No animation
- Very subtle feedback only
- Noticeable but restrained
- Strong sense of motion
- Highly dynamic showcase motion
- Custom motion direction

Specify where motion gives orientation, feedback, or storytelling. Decorative animation that competes with the main task is excluded.

## Device priority

- Desktop first
- Mobile first
- Equally strong on desktop and mobile
- Custom device or platform priority

Device priority changes composition and interaction priorities; it never permits a broken secondary layout.

## Accessibility target (gated)

Ask only when the request signals a regulated, public-sector, or enterprise context; an EU consumer-facing product covered by the European Accessibility Act (e-commerce, banking, transport, e-books, communications); EU procurement; or a named standard. Otherwise state WCAG 2.2 AA as the assumption and move on.

- Best-effort baseline
- WCAG 2.2 AA (default when asked)
- WCAG 2.1 AA (only when a contract or regulation cites it explicitly)
- WCAG 2.2 AAA for selected criteria
- A named in-house or client standard

Reduced motion, focus visibility, and keyboard access are already mandated by the skill's baselines, so do not re-ask them. Escalate detail only for AAA or a named in-house standard.

## Localization and text direction (gated)

Ask only when the request mentions multiple languages, markets, or regions; contains non-Latin content; or the codebase already has i18n infrastructure. Otherwise assume a single language, left-to-right, and layouts that tolerate longer strings without truncation.

### Language scope

- Single language only
- Build localizable now, ship one language first
- Multi-language from launch

### Text direction

- Left-to-right only
- Left-to-right and right-to-left (mirrored layout using logical CSS properties, not just text alignment)
- Right-to-left primary

### Expansion tolerance

- Fixed layouts (single language, controlled copy)
- Flexible layouts that tolerate roughly 35% text expansion (short UI strings can expand far more)

When right-to-left is in scope, mirror layout, directional icons, and progress or timeline order, not only text alignment. Never bake translatable text into images.

## Completion check

Before the handoff, confirm the choices form one coherent system. Reconcile theme strategy with palette, the accessibility target with the theme's contrast ratios, and everything with the locked design and chosen reference. Ask one targeted question if a conflict would otherwise force the final prompt to guess.
