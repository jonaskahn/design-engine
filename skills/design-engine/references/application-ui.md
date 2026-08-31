# Application UI Branch

Use for application screens, dashboards, admin panels, internal tools, and workflow-oriented interfaces. Do not ask marketing-page hero questions unless the requested screen genuinely includes a product introduction. This core hosts three variants: [saas-onboarding.md](variants/saas-onboarding.md), [community-social.md](variants/community-social.md), and [booking.md](variants/booking.md) when booking is a flow inside a larger product. Read at most one variant alongside this core.

## Required context

Collect only what is missing:

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

### Primary workspace

- Charts and metrics
- Tables and lists
- Forms and actions
- Mixed workspace

### Data presentation

- Large summary values with charts
- Table-led presentation
- Balanced charts and tables
- Summary cards with a detailed panel
- Workflow-led presentation where data is secondary

### Chart and table emphasis

- Charts matter more
- Tables matter more
- Charts and tables are balanced
- Workflow matters more than data display

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

### Card usage

- Avoid cards where possible
- Use cards only for summaries
- Use cards for charts and summaries
- Use cards for most modules

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
