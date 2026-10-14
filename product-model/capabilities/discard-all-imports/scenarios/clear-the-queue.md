---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Discard all
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::imports'}
- text: The Product marks every pending Import discarded
  kind: product
  actor: athlete
  entities: [{entity: import, effect: changes, from: Pending, to: Discarded, facts: []}]
  contexts:
    web: {place: 'web::app::imports'}
---

# Clear the queue

## Trigger

The Athlete does not want any of the pending imports.

## Outcome

The queue is empty and none of them is staged again.
