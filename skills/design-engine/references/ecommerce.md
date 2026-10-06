# E-commerce and Marketplace Branch

Use for product listing pages, product detail pages, cart, checkout, account areas, and marketplace search. Also use for real estate listings, job boards, and general directory listings — they share the same listing-and-facet decisions even when there is no cart.

## Required context

Missing facts to collect:

- the surface being designed: listing, detail, cart, checkout, account, or search results;
- category or catalog scope and typical item count;
- target audience and purchase or inquiry intent;
- primary action, such as add to cart, buy now, book, apply, or contact;
- real product data available: prices, variants, images, stock, shipping, reviews;
- payment, fulfillment, or booking constraints that affect checkout.

Do not invent: prices, stock levels, shipping times, return windows, review counts, ratings, or payment methods.

## Branch decisions

### Listing layout

- Dense grid
- Spacious grid with larger imagery
- List view with side-by-side detail
- Map-paired list (real estate, local listings)
- Mixed grid with featured items

### Facet and filter model

- Left filter rail
- Top filter bar
- Drawer-based filters
- Minimal filtering
- Custom filter model

Specify applied-filter chip visibility, clearing behavior, and result count. Keep filtering separate from item detail.

### Product detail structure

- Large gallery with sticky buy box
- Gallery and description stacked
- Split gallery and specification table
- Minimal detail with linked full spec sheet

### Variant and price presentation

- Simple variant selector (size, color, plan)
- Complex configurator with dependent options
- Single fixed price
- Price range with variant-driven changes
- Promotional or strikethrough pricing

Do not invent promotional pricing unless the user supplies real figures.

### Cart model

- Dedicated cart page
- Side drawer cart
- Mini cart preview only

### Checkout structure (choose one)

- Single-page checkout
- Multi-step checkout
- Accordion-style checkout

### Checkout options (combine as needed)

- Guest checkout allowed
- Express wallet options (Apple Pay, Google Pay, etc.), only if genuinely available

Define the minimum necessary fields. Do not request unnecessary personal data.

## Required states

- Out of stock and back-in-stock
- Variant unavailable in combination
- Low stock urgency (only with real inventory signals)
- Empty cart
- Zero search or filter results
- Payment failure and retry
- Address or form validation
- Order or application success

## Output emphasis

The final prompt must define listing density, facet behavior, detail-page hierarchy, cart and checkout flow, and every required state. Never present fabricated availability, pricing, or reviews as real.
