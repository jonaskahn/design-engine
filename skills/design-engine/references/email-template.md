# Email Template Branch

Use for marketing campaign emails, newsletters, and transactional emails. Email rendering is fundamentally different from a web page — treat this branch's constraints as hard requirements, not style preferences.

## Shared-intake carve-out

From `shared-intake.md`, use only: character, palette, theme strategy, typography, imagery, and information density. Skip motion, device priority, and the primary-action control-style catalog — email clients do not support animation, viewport-based layout, or arbitrary CSS control shapes.

## Constraints (state these up front, do not treat as optional)

- Layout must be table-based with inline CSS; no external stylesheets.
- No JavaScript.
- No flexbox or grid inside Outlook for Windows — it renders with the Word engine.
- Background images are unreliable across clients; do not depend on them for critical content.
- Gmail clips messages over roughly 102KB — keep markup lean.
- Every image requires meaningful alt text, since images are blocked by default in many clients.

## Required context

Collect only what is missing:

- email type: marketing campaign, newsletter, or transactional;
- sender and audience context;
- primary action, such as click-through, purchase, or account confirmation;
- required content modules and real copy or a labeled placeholder;
- brand assets available as email-safe image files.

Do not invent sender claims, offers, or transactional details.

## Branch decisions

### Layout width and structure

- Single-column fixed width (600px, recommended for broadest compatibility)
- Hybrid fluid layout with a max width

### Modules

- Preheader text
- Header with logo
- Hero image or headline
- Body content blocks
- Primary call-to-action button
- Product or content grid
- Legal footer with unsubscribe link

### Call-to-action treatment

- Bulletproof table-based button (recommended for reliability across clients)
- Plain styled link

### Image strategy

- Image-led with a text fallback for images-blocked view
- Minimal imagery, text-led for reliability

### Dark mode handling

- Design that tolerates client-forced color inversion (transparent PNG logo, avoid pure-black text on transparent background)
- Explicit dark-mode color scheme via supported meta tags
- No dark-mode handling, accept default rendering

### Typography

- Web-safe font stack only, with a defined fallback order

## Required states

- Images blocked (fallback text and alt attributes)
- Dark-mode forced inversion
- Narrow mobile viewport
- Plain-text version
- Preheader truncation

## Output emphasis

The final prompt must define layout structure, module order, CTA implementation as bulletproof HTML, image fallback behavior, and dark-mode tolerance. State explicitly that output is HTML email markup, not a web page.
