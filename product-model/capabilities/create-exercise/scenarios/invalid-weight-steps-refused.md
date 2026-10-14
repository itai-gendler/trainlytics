---
kind: validation
routes:
  web: Web app
steps:
- text: The Athlete saves an exercise with weight steps out of range
  kind: actor
  actor: athlete
  entities: [{entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
- text: The Product refuses it
  kind: product
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::settings'}
---

# Invalid weight steps are refused

## Trigger

The Athlete enters plates outside 1 to 50 lb, more than 100 plates, or a kg step above 20 or with more than two decimals.

## Outcome

Nothing is saved; the field says what is allowed.
