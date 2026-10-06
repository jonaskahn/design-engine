# Event and Conference Variant

Variant of marketing-website. Adds only what an event page adds.

## Required context

- event name, date, format (in-person, virtual, hybrid);
- real speakers, agenda, sponsors, and ticket pricing available;
- registration deadline or capacity constraints, if real.

Do not invent: speakers, agenda items, sponsors, prices, capacity, or deadlines.

## Branch decisions

### Date and urgency treatment

- Simple date block
- Countdown timer
- Deadline banner (limited seats, early-bird pricing)

### Agenda presentation

- Day-by-day tabs
- Track grid (parallel sessions)
- Vertical timeline
- "Agenda coming soon" placeholder

### Speaker presentation

- Photo grid with name and title
- Featured keynote speakers with a supporting grid
- List only, no photos

### Ticket tiers

- Single ticket type
- Multiple tiers with feature comparison
- Free with required registration

### Registration path

- Inline registration form
- Handoff to an external ticketing platform
- Waitlist only (sold out or capacity-limited)

## Required states

- Past-event mode (recap instead of registration CTA)
- Sold out
- Registration closed

