# Mobile App Branch

Use for native or hybrid mobile app screens. Do not use for responsive web pages viewed on mobile — use the relevant web branch with mobile-first device priority instead.

## Required context

Collect only what is missing:

- the screen or flow being designed;
- target platform: iOS, Android, or both;
- user role and primary task;
- primary and secondary actions on the screen;
- required data, entities, and states;
- existing design system or component library, if any.

## Branch decisions

### Platform and design-system baseline

- Follow iOS Human Interface Guidelines
- Follow Material Design
- Custom design system
- Brand-uniform across both platforms rather than platform-native

### Navigation model

- Bottom tab bar
- Stack navigation with back gesture
- Side drawer
- Modal-heavy flow
- Gesture-led navigation

### Screen structure

- Single scrollable screen
- Segmented or tabbed screen
- List-to-detail flow
- Form-driven flow

### Action placement

- Floating action button
- Bottom action bar
- Top toolbar actions
- Inline actions within content

### Sheets and modals

- Bottom sheet for secondary actions
- Full-screen modal for focused tasks
- Minimal modal use

### Platform fidelity

- Strict platform-native conventions
- Cross-platform consistency with light platform adaptation
- Fully custom brand experience on both platforms

## Required states

- Skeleton or loading
- Empty state
- Offline
- Permission denied
- Pull-to-refresh
- End-of-pagination
- Validation and error
- Destructive-action confirmation

## Output emphasis

The final prompt must define navigation model, screen structure, action placement, and required states. Account for thumb reach, safe areas, minimum touch target size (44pt iOS / 48dp Android), and dynamic type support.
