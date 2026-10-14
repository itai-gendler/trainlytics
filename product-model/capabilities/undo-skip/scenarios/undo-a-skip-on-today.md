---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Undo skip on a Skipped planned session
  kind: actor
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::today'}
- text: The Product clears the skip note and the Planned session is planned again
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: changes, from: Skipped, to: Planned, facts: [Skip note]}]
  contexts:
    web: {place: 'web::app::today'}
---

# Undo a skip on Today

## Trigger

The Athlete skipped today's session but now wants to do it.

## Outcome

The skip note is gone and Start, Move to tomorrow and Skip are offered again.
