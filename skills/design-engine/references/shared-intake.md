# Shared Intake

Use this catalog after the experience branch and core product facts are known. Ask only about unresolved decisions that will materially change the result.

## Core fact support

Ask for goals and audiences in free form when possible. If the user needs choices, offer only the relevant examples.

### Goal examples

- Present a personal brand
- Present work or projects
- Explain a product and build trust
- Capture signups, leads, contact requests, or demo bookings
- Help users understand information or complete tasks
- Improve the quality, clarity, conversion, or mobile behavior of an existing experience

### Audience examples

- Recruiters or hiring managers
- Consumers
- Clients or partners
- Internal teams
- Investors
- Developers or designers

Do not force the user into these examples when their actual goal or audience is more specific.

## Grouping

Group related decisions instead of asking one question at a time:

1. composition, organization, and density;
2. palette, theme strategy, brand dependency, and accent;
3. typography and imagery;
4. controls, motion, and device priority;
5. accessibility target and localization, only when gated (see below).

Do not present every option when a shorter, relevant subset will do. The user may combine compatible choices or answer in free form.

## Composition

### Character

- Restrained and minimal
- Content-led
- Product-led
- Showcase-led
- Custom direction

Translate the selected character into visible decisions about hierarchy, whitespace, imagery, and emphasis. Do not leave abstract adjectives unexplained in the final prompt.

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

Reconcile organization and density when they conflict. For example, a dense card grid and a very spacious presentation require an explicit priority.

## Color system

### Palette direction

- Black-and-white minimal
- Deep gray with cool white
- Deep navy-black with ice blue
- Deep green-black with teal
- Deep burgundy with muted gold
- Warm brown-gray with off-white
- Pure white with cool gray
- Off-white with warm gray
- Pale blue-gray with white
- Cream white with soft gold
- Light neutral with a cool accent
- Light neutral with a warm accent
- Dark with limited bright highlights
- Brand-color-led
- Multicolor with stronger contrast
- High-contrast color blocking
- Custom palette

### Brand dependency

- Independent of an existing brand
- Use the existing brand system
- Brand system is not decided yet

If an existing or custom palette is selected, collect the actual colors, tokens, or asset reference when available. Otherwise preserve a labeled placeholder.

### Accent

- Blue
- Cyan
- Green
- Yellow
- Gold
- Orange
- Red
- Purple
- Pink
- Existing brand color
- No obvious accent
- Custom accent

Do not select an accent that undermines the requested contrast, tone, or brand constraints.

## Theme strategy

Ask this in every intake — it changes every palette decision that follows.

### Theme support

- Light mode only
- Dark mode only
- Both light and dark (recommended)

### Default behavior (if both)

- Follow system `prefers-color-scheme` with a manual override toggle (recommended)
- Default light with a manual toggle
- Default dark with a manual toggle
- Force one mode regardless of system setting

### Dark base surface (if dark is in scope)

- Dark gray, approximately `#121212` (Material default, recommended)
- Pure black `#000000` (OLED battery savings)
- Branded dark, tinted with the brand hue

Reconcile the theme choice with the palette direction. Elevation in dark mode comes from surface lightness, not shadow. A palette chosen for light mode needs explicit dark-mode neutrals rather than a mechanical inversion.

## Typography

- Sans serif throughout
- Serif headlines with sans-serif body
- Editorial or magazine-like
- Minimal and neutral
- Technical and product-like
- Futuristic
- Premium or luxury-oriented
- Friendly and soft
- Expressive and brand-forward
- Steady and professional
- Custom typography direction

Describe hierarchy, weight, scale, and reading character. Name a specific typeface only when the user supplied it, licensing is understood, or the target environment provides it.

## Imagery

- Real people or photography
- Product screenshots or interface visuals
- Abstract background treatments
- Illustration or graphic-led visuals
- 3D visuals
- Video or moving-image-led visuals
- Mixed photography and product visuals
- Minimal imagery with layout-led presentation
- Custom imagery direction

Record whether assets already exist. Use explicit placeholders rather than inventing missing photography, screenshots, or brand artwork.

## Controls

### Primary action style

- Rounded solid button
- Rounded outline button
- Square solid button
- Square outline button
- Fully pill-shaped button
- Text-only action
- Solid primary with outline secondary
- One oversized primary action with secondary actions de-emphasized
- Custom control style

For application interfaces, interpret this as the broader control language rather than styling every action identically.

## Motion

- No animation
- Very subtle feedback only
- Noticeable but restrained
- Strong sense of motion
- Highly dynamic showcase motion
- Custom motion direction

Specify where motion adds orientation, feedback, or storytelling. Avoid decorative animation that competes with the main task. Always provide a reduced-motion equivalent for nonessential movement.

## Device priority

- Desktop first
- Mobile first
- Equally strong on desktop and mobile
- Custom device or platform priority

Device priority changes composition and interaction priorities; it never permits a broken secondary layout.

## Accessibility target (gated)

Do not ask by default. Ask only when the request signals a regulated, public-sector, enterprise, or EU-procurement context, or names a specific standard. Otherwise state the default below as an assumption and move on.

- Best-effort baseline
- WCAG 2.1 AA (the EU legal floor via EN 301 549 v3.2.1)
- WCAG 2.2 AA (default when the topic is asked)
- WCAG AAA
- A named in-house or client standard

What each level changes: AA requires 4.5:1 contrast for body text and 3:1 for large text and non-text UI components; AAA requires 7:1 and 4.5:1 respectively; 2.2 adds focus-appearance, minimum target size, dragging alternatives, consistent help, and redundant entry requirements.

Do not re-ask reduced motion, focus visibility, or keyboard access here — the skill's baseline requirements already mandate them for every direction. Escalate to further detail only for AAA or a named in-house standard.

## Localization and text direction (gated)

Do not ask by default. Ask only when the request mentions multiple languages, markets, or regions; contains non-Latin content; or the codebase already has i18n infrastructure. Otherwise assume single language, left-to-right, and layouts that tolerate longer strings without truncation.

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

When right-to-left is in scope, mirror layout, directional icons, and progress or timeline order — not only text alignment. Use locale-aware formatting for dates, numbers, and currency. Never bake translatable text into images.

## Completion check

Before moving to the output, confirm internally that the selected choices form one coherent system. Reconcile theme strategy with the palette direction, and the accessibility target with the theme's contrast ratios. Ask one targeted question if a conflict would otherwise force the final prompt to guess.
