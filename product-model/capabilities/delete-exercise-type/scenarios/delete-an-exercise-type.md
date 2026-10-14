---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Delete on an Exercise type
  kind: actor
  actor: athlete
  entities: [{entity: exercise-type, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
- text: The Product deletes the Exercise type and takes it off every Exercise
  kind: product
  actor: athlete
  entities: [{entity: exercise-type, effect: removes}, {entity: exercise, effect: changes, facts: [Exercise types]}]
  contexts:
    web: {place: 'web::app::settings'}
---

# Delete an exercise type

## Trigger

The Athlete no longer uses a tag.

## Outcome

The tag is gone from every exercise.
