---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Edit on an Exercise type, changes the name and saves
  kind: actor
  actor: athlete
  entities: [{entity: exercise-type, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
- text: The Product saves the name
  kind: product
  actor: athlete
  entities: [{entity: exercise-type, effect: changes, facts: [Name]}]
  contexts:
    web: {place: 'web::app::settings'}
---

# Rename an exercise type

## Trigger

The Athlete wants a different tag name.

## Outcome

Exercises tagged with it show the new name.
