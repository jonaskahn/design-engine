---
name: design-engine
description: Guide an adaptive product design intake and turn the decisions into a structured design direction, one reusable generation prompt, and practical build notes. Use for personal websites, marketing or conversion pages, product websites, application UIs, dashboards, e-commerce and marketplace listings, blogs and documentation sites, mobile app screens, AI chat and agent interfaces, email templates, and redesigns of any of these when the user needs help choosing a concrete interface direction. Do not use for implementation-only requests that already provide a complete design specification.
---

# Design Engine

Translate product intent into an actionable interface direction. Ask only for decisions that are missing and consequential; do not force the user through a fixed questionnaire.

## Workflow

1. Read the request and retain every decision the user has already made.
2. Identify the core branch and, if relevant, one variant or the redesign overlay. See Branch routing below.
3. Establish any missing core facts: what is being designed, its audience, its main goal, its essential content or tasks, and the primary action users should take.
4. Read [references/shared-intake.md](references/shared-intake.md), the one matching core reference, and at most one variant or overlay reference. Do not read other core references.
5. Ask unresolved questions in compact groups. Prefer 3–6 related decisions per turn. Accept option numbers, labels, or free-form answers.
6. Follow up only when:
   - a custom choice lacks a concrete value;
   - two choices materially conflict;
   - a missing fact would make the result generic or misleading.
7. When the direction is sufficiently defined, read [references/output-contract.md](references/output-contract.md) and produce the handoff.

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

- Redesign of an existing experience: read [references/redesign.md](references/redesign.md) plus the core reference for the surface being redesigned. Inspect the supplied page, screenshot, or code before asking visual questions. If the surface type is unclear, default the core to marketing website or application UI.

If the branch is unclear, ask one direct branch-selection question before loading a branch reference.

### Composition rule

Load exactly one core. A variant never loads without its host core, and at most one variant loads per request.

When a request genuinely spans two cores, choose the core that governs the surface actually being designed, state that choice to the user, and borrow at most the secondary core's *Required context* list — never its decision catalog. For example, a landing page that promotes an AI chat product is `marketing-website.md`, not `ai-chat.md`; the chat branch is for designing the chat surface itself.

Do not mix two cores' decision catalogs in one interview.

## Interview behavior

- Mirror the user's language. Use bilingual wording only when requested or clearly useful.
- Use concrete interface language rather than vague mood labels.
- Explain a choice only when its consequences may be unclear.
- Let users combine compatible options and override the catalog with free-form direction.
- Treat the option catalog as decision support, not a checklist. Skip irrelevant choices.
- When the user asks for recommendations, recommend a coherent combination and explain the tradeoff briefly.
- Do not prematurely write the final prompt while a high-impact decision remains unresolved.

## Baseline requirements

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

## Completion

Return exactly the three sections defined in `references/output-contract.md`:

1. `Selected UI Direction`
2. `Final Prompt`
3. `Build Notes`

If the user names a target tool, adapt the prompt's vocabulary to that tool without changing the selected direction. Otherwise keep the prompt tool-neutral.
