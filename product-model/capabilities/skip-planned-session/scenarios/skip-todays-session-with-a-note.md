---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Skip on a Planned session for today and writes why
  kind: actor
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::today'}
- text: The Product saves the reason and shows the Planned session as Skipped
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: changes, from: Planned, to: Skipped, facts: [Skip note]}]
  contexts:
    web: {place: 'web::app::today'}
---

# Skip today's session with a note

## Trigger

The Athlete will not do a session planned for today.

## Outcome

The session shows as Skipped on Today with the Athlete's reason, and Undo skip is offered.

## Edge cases

- Skipping from Today needs a note; an empty one is not accepted.
- Plan keeps showing a session skipped from Today as planned until its day has passed.
