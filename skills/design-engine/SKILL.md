---
name: design-engine
description: Turns a vague interface idea into one non-generic design direction, a reusable prompt, a DESIGN.md, and build notes — preserving an existing design when the codebase has one, otherwise grounding the choice in named reference design languages. Use when the user asks how a UI should look or be structured (sites, dashboards, storefronts, docs, mobile, AI chat, email, redesign), wants a design prompt or a DESIGN.md, or wants a design that avoids the generic AI look. Not for implementation-only requests that already include a complete design spec.
license: GPL-3.0
metadata:
  version: "1.2.0"
---

# Design Engine

Translate product intent into an interface direction that is specific to this product and free of generic AI-default styling. Ask only for decisions that are missing and consequential; do not force the user through a fixed questionnaire.

## Workflow

1. **Retain** every decision already in the request.
2. **Discover the existing design.** Read [references/existing-design.md](references/existing-design.md) and run its discovery whenever the request includes or implies one of the sources it defines. A found design is *locked*: suggestions extend it and never replace it.
3. **Route** to one core per the Composition rule, and establish the missing core facts. Each reference lists its *Required context* — collect only what is missing.
4. **Ground the direction.** If any design slot (palette, type, shape, components) is open, read [references/design-references.md](references/design-references.md) and offer 2–3 reference design languages for the open slots only, each compatible with what is already locked, with one line on why it fits. The user may decline and go custom.
5. **Lock-in research.** When a reference is chosen, read `references/brands/<slug>.md`, then refresh it from the official source using the procedure in `design-references.md`.
6. **Interview** with [references/shared-intake.md](references/shared-intake.md) plus the core reference. Prefer 3–6 related decisions per turn. Accept option numbers, labels, or free-form answers.
7. **Slop check.** Before the handoff, run the check in [references/anti-slop.md](references/anti-slop.md) against the direction and the prompt.
8. **Handoff** per [references/output-contract.md](references/output-contract.md) — all four sections, in one response.
9. **Build** only when the request asked to build or implement the interface, not merely to design it — see [Completion](#completion).

Order when rules collide: explicit user instruction > locked design > chosen reference > catalog defaults. An explicit instruction that overrides a locked value is applied, and the override is stated once in the response. A request that only implies a conflict becomes one question. An anti-slop ban is lifted only when a higher level explicitly chose the pattern.

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

Guards where two branches look alike: a mobile app means native or hybrid screens — for a responsive web page viewed on mobile, use the web branch with mobile-first device priority. AI chat means the interface itself — for a marketing page that merely promotes an AI product, use the marketing branch. Application UI gets no marketing-hero questions unless the screen genuinely includes a product intro.

### Variants (read at most one, only with its host core)

- Event or conference landing page — hosts on marketing: read [references/variants/event-page.md](references/variants/event-page.md).
- Nonprofit, donation, or fundraising page — hosts on marketing: read [references/variants/nonprofit-donation.md](references/variants/nonprofit-donation.md).
- Booking or reservation flow — hosts on marketing or application UI: read [references/variants/booking.md](references/variants/booking.md).
- SaaS onboarding and empty states — hosts on application UI or marketing: read [references/variants/saas-onboarding.md](references/variants/saas-onboarding.md).
- Community, social, or forum platform — hosts on application UI: read [references/variants/community-social.md](references/variants/community-social.md).

### Overlay

- Redesign of an existing experience: read [references/redesign.md](references/redesign.md) plus the core reference for the surface.

### Composition rule

Load exactly one core. Add at most one of: a variant (only with its host core) or the redesign overlay. When a request genuinely spans two cores, use the core that governs the surface being designed, say so, and borrow only the other core's *Required context* — never its decision catalog.

If the branch, the surface, or the host core is unclear, ask one direct branch-selection question before loading a branch reference.

## Interview behavior

- Mirror the user's language; use concrete interface language rather than vague mood labels. Bilingual wording only when requested or clearly useful.
- Treat the option catalog as decision support, not a checklist: users may combine compatible options, override with free-form direction, and skip what does not matter here.
- When the user asks for recommendations, give one coherent combination with the tradeoff in a line; explain a choice only when its consequences may be unclear.
- Do not write the final prompt while a high-impact decision remains unresolved.

## Baselines

Apply these unless the user explicitly provides a stronger or conflicting requirement:

- responsive behavior appropriate to the chosen device priority;
- semantic structure and readable hierarchy;
- sufficient color contrast and non-color status cues;
- visible focus and keyboard access for interactive controls;
- reduced-motion behavior for nonessential animation;
- realistic interface states where relevant, including empty, loading, error, disabled, and success states;
- theme parity: when both light and dark themes ship, contrast and non-color status cues hold in each.

Baselines are not interview questions, except the gated topics in `shared-intake.md` — surface those when their gating condition is met.

## Privacy and accuracy

- Treat every external design or generation service as a third party: no secrets, private URLs, internal metrics, customer lists, unpublished roadmap details, personal contact details, or proprietary data in an external-tool prompt without explicit user approval.
- Generalize confidential context and use labeled placeholders for missing copy, assets, screenshots, metrics, testimonials, or customer names.
- Do not invent product claims, social proof, capabilities, or brand assets.
- Distinguish visual exploration from production-ready implementation.
- Reference designs are inspiration: borrow principles, scales, and patterns — never logos, trademarks, product imagery, or proprietary typefaces the user has not licensed.

## Completion

Deliver per [references/output-contract.md](references/output-contract.md).

When the original request asked to build or implement the interface, the handoff is a midpoint, not the finish line. Then:

1. Write DESIGN.md to the location it was found (repo root, `docs/`, or `design/`), else the repo root as `DESIGN.md`. If one exists, write the merged update. This is the one case where the file is written rather than only offered.
2. Implement the interface using the Final Prompt and `DESIGN.md` as the spec: reuse the existing stack, components, tokens, and conventions when a codebase exists; when the repo is empty, scaffold the simplest sensible app for the experience type and state that choice.
3. Keep going until the result meets the Final Prompt's acceptance criteria — realistic states included — then report what was built, how to run it, and any Build Notes that affected the implementation.

If the request was design-only (a prompt, a critique, a DESIGN.md on its own), stop after the four sections and let the user drive the next step.
