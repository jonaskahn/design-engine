# Output Contract

Use this contract after the direction is sufficiently defined. Return exactly three top-level sections in the user's language.

## Selected UI Direction

Summarize decisions in compact bullets under whichever labels are relevant:

- Product context: experience, audience, goal, and primary action
- Experience structure: sections, navigation, workspace, content flow, or task flow
- Visual system: character, palette, theme strategy, type, imagery, controls, and density
- Behavior: interaction, motion, device priority, responsive adaptation, and text direction or localization when in scope
- Constraints: preserved elements, assets, placeholders, privacy treatment, accessibility conformance target when set, and assumptions

Do not list questionnaire numbers. Convert selections into a coherent direction and resolve compatible combinations in plain language.

## Final Prompt

Write one self-contained prompt that another design or implementation agent can use without reading the interview. Put it in a fenced text block for easy copying.

Include, in a natural order:

1. **Task and context** — what to design, for whom, why, and the primary action or workflow.
2. **Required content or functionality** — real sections, content, data, tasks, and states; retain labeled placeholders where facts or assets are missing.
3. **Structure and hierarchy** — composition, narrative order, information architecture, navigation, and emphasis.
4. **Visual system** — palette, theme strategy (with both light and dark token sets when both themes are in scope), typography, imagery, spacing, controls, cards, and other selected treatments.
5. **Responsive and accessible behavior** — device priority, adaptations, semantic structure, contrast, focus, keyboard behavior, reduced motion, the accessibility conformance target when set, text direction and expansion tolerance when localization is in scope, and theme parity (contrast and non-color status cues hold in every shipped theme).
6. **Interaction and motion** — meaningful feedback, transitions, filtering, details, forms, or task-specific behavior.
7. **Constraints and preservation** — brand rules, existing content or functionality, technical constraints, privacy-safe placeholders, and prohibited invention.
8. **Acceptance criteria** — observable qualities that indicate the result satisfies the selected direction.

Use direct instructions. Avoid commentary about the interview, multiple competing directions, vague adjectives without visible consequences, and claims that the result is production-ready when it is only a visual exploration.

### Target-tool adaptation

- If no tool is named, keep the prompt implementation-neutral.
- For a visual exploration tool, emphasize composition, states, content hierarchy, and visual language; do not imply production code.
- For a coding agent with a codebase, require reuse of the existing stack, components, tokens, and conventions unless the user authorized replacement.
- Do not add framework-specific instructions unless the framework is known.

## Build Notes

Add only practical consequences that are useful outside the final prompt, such as:

- assets or copy the user still needs to supply;
- risky responsive or interaction areas;
- implementation dependencies implied by the choices;
- privacy-sensitive placeholders that must remain placeholders;
- validation priorities.

Do not repeat the selected direction or restate the full prompt. If no extra note is useful, write `No additional build notes.` in the user's language.

## Final quality check

Before responding, verify that:

- the prompt contains no invented facts or confidential details that should be generalized;
- the three sections agree with each other;
- all high-impact choices are represented;
- responsive and accessibility requirements are concrete;
- contrast and non-color status cues hold in every theme the direction ships;
- right-to-left mirroring is specified when text direction is in scope;
- the accessibility conformance target, if any was set, is stated once and never contradicted;
- branch-specific requirements are present;
- placeholders and assumptions are explicit;
- only one final direction is delivered.
