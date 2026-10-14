---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete removes a replacement from an Exercise
  kind: actor
  actor: athlete
  entities: [{entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
- text: The Product takes it off the exercise's replacements
  kind: product
  actor: athlete
  entities: [{entity: exercise, effect: changes, facts: [Replacements]}]
  contexts:
    web: {place: 'web::app::settings'}
---

# Remove a replacement

## Trigger

A replacement no longer suits.

## Outcome

The exercise no longer lists it.
