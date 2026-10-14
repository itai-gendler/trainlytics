---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Discard on an Import and confirms
  kind: actor
  actor: athlete
  entities: [{entity: import, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::imports'}
- text: The Product marks the Import discarded
  kind: product
  actor: athlete
  entities: [{entity: import, effect: changes, from: Pending, to: Discarded, facts: []}]
  contexts:
    web: {place: 'web::app::imports'}
---

# Discard one import

## Trigger

An imported activity should not be logged.

## Outcome

The import leaves the queue and is never staged again.
