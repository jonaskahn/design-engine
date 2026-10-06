# Output Contract

Use after the direction is sufficiently defined. Return exactly four top-level sections.

## 1. Selected UI Direction

Summarize the decisions in compact bullets under whichever labels are relevant:

- Product context: experience, audience, goal, and primary action
- Experience structure: sections, navigation, workspace, content flow, or task flow
- Visual system: character, palette, theme strategy, type, imagery, controls, and density
- Behavior: interaction, motion, device priority, responsive adaptation, and text direction or localization when in scope
- Constraints: preserved elements, assets, placeholders, privacy treatment, accessibility target when set, and assumptions

Tag each decision's origin inline — `[user]`, `[locked: source]`, `[reference: name]`, or `[default]` — so the reader can see what was chosen versus inferred. When a reference design is used, add one line naming it; its verification status belongs in Build Notes.

Convert selections into a coherent direction in plain language rather than restating option labels or numbers, and resolve compatible combinations.

## 2. Final Prompt

One self-contained prompt another design or implementation agent can use without reading the interview. Put it in a fenced text block for easy copying.

Include, in a natural order:

1. **Task and context** — what to design, for whom, why, and the primary action or workflow.
2. **Required content or functionality** — real sections, content, data, tasks, and states; retain labeled placeholders where facts or assets are missing.
3. **Structure and hierarchy** — composition, narrative order, information architecture, navigation, and emphasis.
4. **Visual system** — palette, theme strategy (both light and dark token sets when both ship), typography, imagery, spacing, controls, cards, and other treatments. Give exact values when locked or referenced.
5. **Responsive and accessible behavior** — the Baselines from SKILL.md, plus device priority and adaptations, the accessibility conformance target when set, text direction and expansion tolerance when localization is in scope.
6. **Interaction and motion** — feedback, transitions, filtering, details, forms, or task-specific behavior.
7. **Constraints and preservation** — brand rules, existing content or functionality, technical constraints, privacy-safe placeholders, and prohibited invention.
8. **Acceptance criteria** — observable qualities that indicate the result satisfies the selected direction.
9. **Avoid** — the named anti-slop list for this surface, per `anti-slop.md` → "Where the result goes".

When a reference design is used, say "in the spirit of <name>'s design language".

Write directly: one direction, visible consequences instead of adjectives, no interview commentary.

### Target-tool adaptation

- If no tool is named, keep the prompt implementation-neutral.
- For a visual exploration tool, emphasize composition, states, content hierarchy, and visual language; do not imply production code.
- For a coding agent with a codebase, require reuse of the existing stack, components, tokens, and conventions unless the user authorized replacement.
- Do not add framework-specific instructions unless the framework is known.

## 3. DESIGN.md

Always present: one fenced `markdown` block following `design-md-template.md` and the Google Labs DESIGN.md spec.

The block is emitted even when the file is also written to disk, and section 4 follows it in the same response. This section never ends the turn, and neither does a tool call that writes the file.

Tell the user to save it at the repo root as `DESIGN.md`. When the run continues into implementation per `SKILL.md` Completion, write the file there yourself — the write satisfies the save, never the block, and never the response.

## 4. Build Notes

Only practical consequences useful outside the final prompt:

- assets or copy the user still needs to supply;
- risky responsive or interaction areas;
- implementation dependencies implied by the choices;
- privacy-sensitive placeholders that must remain placeholders;
- validation priorities;
- reference verification status (verified against <URL> on <date>, or "stored tokens, unverified");
- font licensing notes;
- anti-slop patterns the user or a locked design chose deliberately.

Do not repeat the selected direction or restate the full prompt. If no extra note is useful, write `No additional build notes.`

## Final quality check

Before responding, verify:

- all four sections are present, with Build Notes last — DESIGN.md was not the last thing said;
- the four sections agree with each other;
- DESIGN.md tokens match the Final Prompt values exactly;
- the slop check passed and item 9 names specific patterns;
- only one final direction is delivered.
