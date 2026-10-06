# Booking and Reservation Variant

Host core: marketing-website or application-ui (standalone page vs flow inside a product). Covers only what booking adds.

## Required context

- what is being booked (appointment, table, room, service) and typical duration;
- real availability source or constraints, if known;
- required customer information at booking time;
- cancellation, rescheduling, or deposit policy, if real.

Do not invent: availability, time slots, or pricing.

## Branch decisions

### Availability presentation

- Month calendar with available days highlighted
- Week strip
- Next-available list (no calendar)
- Date-then-time-slot two-step selection

### Selection order

- Service or resource first, then time
- Time first, then service or resource
- Combined single-step selection

### Minimum field set

- Name and contact only
- Name, contact, and party size or resource detail
- Full intake form with notes or special requests

### Account requirement

- Guest booking allowed
- Account required
- Guest booking with optional account creation

### Confirmation

- On-screen confirmation only
- Confirmation plus email/SMS notice
- Calendar-file (.ics) offer

## Required states

- No availability for the selected date
- Fully booked date
- Slot taken mid-booking (race condition)
- Time-zone mismatch between user and venue
- Past booking cutoff
- Booking confirmed
- Cancel or reschedule flow

## Output emphasis

The prompt must define availability presentation, selection order, and every required state, especially the slot-taken race condition.
