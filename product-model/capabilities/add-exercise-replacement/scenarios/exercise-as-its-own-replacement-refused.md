---
kind: validation
routes:
  web: Web app
steps:
- text: The Athlete picks an Exercise as a replacement for itself
  kind: actor
  actor: athlete
  entities: [{entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
- text: 'The Product refuses: an exercise cannot be its own replacement'
  kind: product
  actor: athlete
  entities: [{entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
---

# An exercise is not its own replacement

## Trigger

The Athlete picks the exercise itself.

## Outcome

Nothing is added.

## Edge cases

- Picking an exercise that is already a replacement is refused as a duplicate.
