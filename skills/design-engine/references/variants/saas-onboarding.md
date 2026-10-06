# SaaS Onboarding and Empty States Variant

Host core: application-ui (in-product) or marketing-website (when signup is the surface). Covers only what onboarding and empty states adds.

## Required context

- what a new user must accomplish to reach first value ("activation");
- whether the product supports team invites or role-based permissions;
- whether sample or demo data is available to seed a first-use experience.

## Branch decisions

### Onboarding shape

- Linear checklist with completion tracking
- Stepped wizard, one decision per screen
- Progressive contextual hints inside the real product
- Pre-seeded sample data the user can explore or discard
- No guided onboarding, explore freely

### Progress visibility

- Persistent progress indicator
- Dismissible checklist
- No visible progress tracking

### Skip and resume

- Onboarding can be skipped entirely
- Onboarding can be skipped but resumed later
- Onboarding is required to proceed

### Invite and permission placement

- Invite prompted during onboarding
- Invite available later from settings, not forced early
- No multi-user invite needed

### Activation moment

Define concretely what action marks a user as "activated" — this should drive what the checklist or wizard optimizes for.

## Empty-state catalog

Each empty state must specify what happened, why, and one clear next action:

- First-use empty state (nothing created yet)
- User-cleared empty state (user deleted everything)
- Filtered-empty state (results exist but the current filter hides them)
- Permission-limited empty state (content exists but the user cannot see it)
- Error-driven empty state (data failed to load, distinct from genuinely empty)

Distinguish loading state from empty state explicitly — never show an empty-state message while data is still loading.

## Output emphasis

The prompt must define the onboarding shape, activation moment, and the full empty-state catalog with a specific next action for each.
