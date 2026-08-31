# Content, Blog, and Documentation Branch

Use for blogs, editorial sites, knowledge bases, API reference sites, changelogs, and other long-form or reference content. This branch's scope explicitly includes documentation, knowledge base, and changelog surfaces.

## Required context

Collect only what is missing:

- the surface being designed: index, article, category, search results, or changelog;
- content type: editorial, technical documentation, reference, or mixed;
- intended reader and their reading context (casual browsing vs. task-driven lookup);
- primary action, such as reading, subscribing, or finding a specific answer;
- available content volume, categorization, and versioning needs.

Do not invent article content, authorship, publish dates, or version history.

## Branch decisions

### Index layout

- Large featured post with a list below
- Uniform card grid
- Dense text-led list
- Category-first landing with curated sections

### Article layout

- Narrow single-column reading measure
- Wide measure with a persistent sidebar
- Two-pane layout (navigation tree and content)

### Sidebar model

- No sidebar
- Table of contents only
- Full navigation tree
- Both navigation tree and table of contents

### Code and technical content

- No code blocks expected
- Inline code only
- Full syntax-highlighted code blocks with copy action

Only include code-block treatment when the content is genuinely technical.

### Search and navigation

- Inline search bar
- Command-palette-style search
- Dedicated search results page
- No search needed at this scale

### Versioning

- No versioning needed
- Version switcher in navigation
- Per-page "applies to version X" notice

## Required states

- No search results
- Empty category
- Table of contents sync on long pages
- Deprecated or outdated content notice

## Output emphasis

The final prompt must define index and article hierarchy, sidebar and navigation model, search behavior, and any versioning treatment. Preserve reading comfort — line length, contrast, and heading hierarchy — as a first-class concern.
