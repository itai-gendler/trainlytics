---
kind: validation
routes:
  web: Web app
steps:
- text: The Athlete enters an invalid date on an Import
  kind: actor
  actor: athlete
  entities: [{entity: import, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::imports'}
- text: The Product refuses the change
  kind: product
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::imports'}
---

# An invalid date is refused

## Trigger

The Athlete enters a date that is not a calendar date.

## Outcome

The import is unchanged.
