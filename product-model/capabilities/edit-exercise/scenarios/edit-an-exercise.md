---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Edit on an Exercise, changes it and saves
  kind: actor
  actor: athlete
  entities: [{entity: exercise-type, effect: reads, facts: [Name]}, {entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
- text: The Product saves the changes
  kind: product
  actor: athlete
  entities: [{entity: exercise, effect: changes, facts: [Name, Notes, Exercise types, Weight steps]}]
  contexts:
    web: {place: 'web::app::settings'}
---

# Edit an exercise

## Trigger

The Athlete wants to correct or retag an exercise.

## Outcome

The exercise shows the changes everywhere it is used.

## Edge cases

- Clearing the weight steps choice returns to the default 10 lb stack.
