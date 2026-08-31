# Community and Social Platform Variant

Hosted by [application-ui.md](../application-ui.md). Read the application core for layout, navigation, and workspace questions; use this file only for what a feed-and-community surface adds.

## Required context

- the community's purpose and topic scope;
- whether content is user-generated, curated, or both;
- moderation model: self-moderated, staffed moderation, or automated.

Never invent user names, avatars, post content, or engagement counts. Do not design mechanics that misrepresent actual activity levels.

## Branch decisions

### Feed model

- Chronological feed
- Ranked or algorithmic feed
- Following-vs-discover split
- Category-first forum index (no unified feed)

### Composer surface

- Always-visible inline composer
- Modal or dedicated composer screen
- Floating action button opens composer

### Thread presentation

- Flat comments, no nesting
- Nested replies with a depth cap
- Q&A style with an accepted-answer marker

### Reaction and voting model

- Simple like or heart
- Multiple reaction types
- Upvote/downvote scoring
- No reactions, comments only

### Notification surface

- In-app notification center
- Badge counts only, no dedicated center
- Real-time inline updates (new posts banner)

### Moderation affordances

- Report content
- Hide or mute
- Lock or pin (moderator-only)
- Dedicated moderation queue

## Required states

- Empty feed for a brand-new user
- No results for a search or filter
- Content removed by moderation
- User blocked or muted
- Rate-limited posting
- Content pending moderation approval
- Real-time arrival of new content while viewing

## Output emphasis

The prompt must define feed model, thread presentation, moderation affordances, and every required state without fabricating sample content or engagement numbers.
