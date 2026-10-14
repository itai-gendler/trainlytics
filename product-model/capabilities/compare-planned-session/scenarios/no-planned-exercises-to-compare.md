---
kind: edge
routes:
  web: Web app
steps:
- text: The Athlete chooses Compare planned vs. actual on a Done strength session
  kind: actor
  actor: athlete
  entities: [{entity: strength-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::plan'}
- text: The Planned session no longer names a template
  kind: condition
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: [Template]}]
  contexts:
    web: {place: 'web::app::plan'}
- text: The Product says no planned exercise data is available
  kind: product
  actor: athlete
  entities: [{entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::plan'}
---

# No planned exercises to compare

## Trigger

The template of a done strength session was deleted.

## Outcome

The comparison says there is no planned exercise data.
