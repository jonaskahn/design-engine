# Application UI Branch

Use for application screens, dashboards, admin panels, internal tools, and workflow-oriented interfaces. Do not ask marketing-page hero questions unless the requested screen genuinely includes a product introduction.

## Required context

Missing facts to collect:

- the screen or workflow being designed;
- user role and task frequency;
- primary and secondary actions;
- important data, entities, and relationships;
- required states, permissions, or destructive actions;
- target platform, viewport, and available design system or component library.

If a codebase is available, inspect its existing navigation, components, tokens, and interaction patterns before proposing replacements.

## Branch decisions

### Layout structure

- Left navigation with main content
- Top navigation with main content
- Left navigation with a right-side detail panel
- Content-led layout with minimal global navigation
- Custom workspace structure

### Navigation style

- Simple top navigation
- Dark sidebar
- Light sidebar
- Compact icon-led navigation
- Custom navigation model

Choose navigation from information architecture and task frequency, not visual preference alone. Include labels or accessible names for icon-led navigation.

### Workspace emphasis

- Metrics and charts lead
- Tables and lists lead
- Balanced charts and tables
- Summary cards with a detail panel
- Forms and workflow lead, data secondary

Do not add charts when values, trends, or comparisons are not meaningful. Define table sorting, selection, pagination, and bulk actions only when relevant.

### Search and filters

- Top-row search and filters
- Left-side filter rail
- Drawer-based filters
- Minimal filter presence
- Custom search or filtering model

Keep search and filters separate from record-detail presentation. Specify active-filter visibility, clearing behavior, and empty results when filtering is important.

### Detail presentation

- No separate detail surface
- Fixed detail panel
- Expandable side panel
- Modal detail view
- Drawer detail view
- Dedicated detail page

Choose a modal only for bounded work that does not require deep navigation or extensive comparison.

## Required states

Include only states relevant to the workflow, but do not omit obvious operational needs:

- loading or progressive loading;
- empty and filtered-empty;
- error and recovery;
- validation and success;
- disabled and permission-limited;
- destructive-action confirmation;
- selection, hover, focus, and keyboard behavior.

## Output emphasis

The final prompt must define information architecture, navigation, workspace hierarchy, task flow, data density, search/filter behavior, detail behavior, responsive adaptation, and required states. It must prioritize efficient completion over decorative presentation.
