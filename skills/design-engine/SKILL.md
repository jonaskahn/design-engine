---
name: design-engine
description: Runs an adaptive design intake that turns a vague interface idea into one concrete, non-generic design direction, a reusable generation prompt, a DESIGN.md, and build notes. Detects and preserves an existing design (DESIGN.md, design tokens, theme files, brand palette) and otherwise grounds suggestions in named reference design languages such as Apple, IBM Carbon, Stripe, or Linear. Use when the user asks how a UI should look or be structured — personal sites, landing and product pages, dashboards and app screens, storefronts and listings, blogs and docs, mobile app screens, AI chat or agent interfaces, email templates, or a redesign — or wants a design prompt, a DESIGN.md, or a design that avoids the generic AI look. Not for implementation-only requests that already include a complete design spec.
license: GPL-3.0
metadata:
  version: "1.1.0"
---

# Design Engine

Translate product intent into an interface direction that is specific to this product and free of generic AI-default styling. Ask only for decisions that are missing and consequential; do not force the user through a fixed questionnaire.

## Workflow

1. **Retain** every decision already in the request.
2. **Discover the existing design.** Read [references/existing-design.md](references/existing-design.md) and run its discovery whenever a codebase, URL, screenshot, or attachment exists. A found design is *locked*: suggestions extend it and never replace it.
3. **Route** to one core (plus at most one variant or the redesign overlay) using the table below, and establish the missing core facts: what is being designed, its audience, its goal, its essential content or tasks, and the primary action. Each reference lists its *Required context* — collect only what is missing.
4. **Ground the direction.** If no design is locked, read [references/design-references.md](references/design-references.md) and offer 2–3 reference design languages that fit the experience type and audience, each with one line on why it fits. The user may decline and go custom.
5. **Lock-in research.** When a reference is chosen, read `references/brands/<slug>.md`, then refresh it from the official source using the procedure in `design-references.md`.
6. **Interview** with [references/shared-intake.md](references/shared-intake.md) plus the core reference. Prefer 3–6 related decisions per turn. Accept option numbers, labels, or free-form answers.
7. **Slop check.** Before the handoff, run the check in [references/anti-slop.md](references/anti-slop.md) against the direction and the prompt.
8. **Handoff** per [references/output-contract.md](references/output-contract.md).

Precedence when rules collide: the user's explicit instruction, then a locked existing design, then the chosen reference design, then catalog defaults. Anti-slop bans apply at every level except where a higher level explicitly chose the pattern.

Do not ask again for information that can be inferred confidently from the request, an attached artifact, or the existing codebase. State nonessential assumptions instead of extending the interview.

## Branch routing

### Core branches (choose exactly one)

- Personal website: read [references/personal-website.md](references/personal-website.md).
- Marketing, product, or conversion website: read [references/marketing-website.md](references/marketing-website.md).
- Application UI, dashboard, or admin panel: read [references/application-ui.md](references/application-ui.md).
- E-commerce, marketplace, real estate, job board, or directory listings: read [references/ecommerce.md](references/ecommerce.md).
- Blog, editorial, documentation, knowledge base, or changelog: read [references/content-docs.md](references/content-docs.md).
- Native or hybrid mobile app screens: read [references/mobile-app.md](references/mobile-app.md).
- AI chat, assistant, or agent interface: read [references/ai-chat.md](references/ai-chat.md).
- Marketing, newsletter, or transactional email: read [references/email-template.md](references/email-template.md).

### Variants (read at most one, only with its host core)

- Event or conference landing page — hosts on marketing: read [references/variants/event-page.md](references/variants/event-page.md).
- Nonprofit, donation, or fundraising page — hosts on marketing: read [references/variants/nonprofit-donation.md](references/variants/nonprofit-donation.md).
- Booking or reservation flow — hosts on marketing or application UI: read [references/variants/booking.md](references/variants/booking.md).
- SaaS onboarding and empty states — hosts on application UI or marketing: read [references/variants/saas-onboarding.md](references/variants/saas-onboarding.md).
- Community, social, or forum platform — hosts on application UI: read [references/variants/community-social.md](references/variants/community-social.md).

### Overlay

- Redesign of an existing experience: read [references/redesign.md](references/redesign.md) plus the core reference for the surface. Infer the surface from the inspected source; if still unclear, ask one branch-selection question.

If the branch is unclear, ask one direct branch-selection question before loading a branch reference.

### Composition rule

Load exactly one core. A variant never loads without its host core, and at most one variant loads per request.

When a request genuinely spans two cores, choose the core that governs the surface actually being designed, state that choice to the user, and borrow at most the secondary core's *Required context* list — never its decision catalog. Do not mix two cores' decision catalogs in one interview.

## Interview behavior

- Mirror the user's language. Use bilingual wording only when requested or clearly useful.
- Use concrete interface language rather than vague mood labels.
- Explain a choice only when its consequences may be unclear.
- Let users combine compatible options and override the catalog with free-form direction.
- Treat the option catalog as decision support, not a checklist. Skip irrelevant choices.
- When the user asks for recommendations, recommend a coherent combination and explain the tradeoff briefly.
- Do not prematurely write the final prompt while a high-impact decision remains unresolved.

## Baselines

Apply these unless the user explicitly provides a stronger or conflicting requirement:

- responsive behavior appropriate to the chosen device priority;
- semantic structure and readable hierarchy;
- sufficient color contrast and non-color status cues;
- visible focus and keyboard access for interactive controls;
- reduced-motion behavior for nonessential animation;
- realistic interface states where relevant, including empty, loading, error, disabled, and success states;
- theme parity: when both light and dark themes ship, contrast and non-color status cues hold in each.

Do not turn these baselines into extra interview questions unless the product has unusual accessibility or platform needs. The gated accessibility-target and localization topics in `shared-intake.md` are the one exception — surface them when their gating condition is met.

## Privacy and accuracy

- Treat every external design or generation service as a third party.
- Do not place secrets, private URLs, internal metrics, customer lists, unpublished roadmap details, personal contact details, or proprietary data into an external-tool prompt without explicit user approval.
- Generalize confidential context and use labeled placeholders for missing copy, assets, screenshots, metrics, testimonials, or customer names.
- Do not invent product claims, social proof, capabilities, or brand assets.
- Distinguish visual exploration from production-ready implementation.
- Reference designs are inspiration: borrow principles, scales, and patterns — never logos, trademarks, product imagery, or proprietary typefaces the user has not licensed.

## Completion

Read `references/output-contract.md` and return its four sections.
