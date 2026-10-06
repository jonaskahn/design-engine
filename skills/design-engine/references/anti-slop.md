# Anti-Slop

A tell is a default nobody chose. Models regress to the median of their training data, so unprompted output drifts toward the same few looks. The ban is on **unchosen** patterns: a pattern is allowed only when the user, a locked existing design, or the chosen reference design explicitly includes it. Then keep it, and note it once in Build Notes as "chosen deliberately".

## Catalog of tells

**Color**
- purple or indigo to blue gradients; gradient headline text (`bg-clip-text`); glowing blur blobs
- neon cyan or violet on near-black with glowing card borders; dark-only as a reflex
- the second-generation "tasteful" defaults: warm cream or beige with a terracotta or soft-gold accent; near-black with one acid-green or vermilion accent; an emerald fallback accent
- untouched shadcn or Tailwind default palettes; muted gray text below 4.5:1

**Typography**
- one family for everything with no pairing (Inter or the system stack)
- the free-font set used as a reflex: Space Grotesk, Geist, Instrument Serif, Fraunces
- one italic, serif, or accent-colored word inside a sans headline
- tracked all-caps eyebrow over every section; monospace labels and `A · B · C` meta strings as decoration
- a font declared in CSS but never loaded

**Layout**
- centered hero with a pill badge above the headline and two buttons below
- the stock sequence: hero, logo strip, three feature cards, stats, testimonials, three-tier pricing with a "most popular" ring, CTA band, four-column footer
- bento grids by reflex; decorative "01 / 02 / 03" numbering; everything centered
- uniform padding and radius on every element; newspaper-hairline "broadsheet" styling

**Components**
- `rounded-2xl` plus `shadow-lg` on everything; glass and `backdrop-blur` navbars by reflex
- icons inside rounded-square tiles; pill buttons with a permanent trailing arrow
- fake window dots and terminal mockups; stock spotlight, beam, marquee, or meteor effects
- dot-grid or noise-grain backgrounds with no purpose; missing focus states

**Motion**
- the same fade-up on every section; bounce easing; count-up stats
- lift and scale on every card hover; motion that ignores `prefers-reduced-motion`

**Icons, imagery, copy**
- a sparkle icon as shorthand for "AI"; emoji as feature icons; one stock icon set with no size or stroke system
- placeholder avatar grids and invented testimonial names; invented metrics ("10x faster", "99.9%")
- buzzwords (elevate, seamless, unlock, supercharge, "build the future") and a generic "Get started" CTA

**Application UI**
- a row of KPI cards with invented green up-arrow percentages; a sparkline on every card
- decorative donut charts; sidebars of identical icon-and-label rows with no hierarchy

**Chat UI**
- a purple sparkle assistant avatar; gradient "AI" borders; generic suggestion chips

**Email**
- a full-bleed gradient hero image that carries the critical copy

## The slop check

Run it after the direction is defined and before the handoff. Repeat until it passes.

1. List every visual decision in the direction and tag its origin: user, locked, reference, or catalog default.
2. Count catalog-default decisions that match a tell.
   - 0: pass.
   - 1–2: replace each with a choice tied to this audience, content, or brand, and give the reason.
   - 3 or more: the direction is generic. Reopen the composition decision with the user and offer a reference design.
3. **Silhouette test.** Describe the page as a block outline. If the outline could belong to any product in the category, change one structural decision: section order, grid, or hero composition.
4. **Distinctiveness.** Name at least two choices that only make sense for this product or audience.

## Where the result goes

- The Final Prompt gets an **Avoid** list naming the tells that were not chosen, taken from the categories most relevant to this surface (12 items at most). A vague "avoid a generic AI look" does not count; name the patterns.
- The DESIGN.md `Do's and Don'ts` section carries the same list.
- Build Notes records each tell the user, a locked design, or the chosen reference design chose deliberately.
