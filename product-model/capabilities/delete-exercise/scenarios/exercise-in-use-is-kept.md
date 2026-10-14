---
kind: validation
routes:
  web: Web app
steps:
- text: The Athlete chooses Delete on an Exercise
  kind: actor
  actor: athlete
  entities: [{entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
- text: A Strength session or Strength template lists the Exercise
  kind: condition
  actor: athlete
  entities: [{entity: strength-session, effect: reads, facts: [Exercises]}, {entity: strength-template, effect: reads, facts: [Exercises]}, {entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
- text: The Product does not delete the Exercise
  kind: product
  actor: athlete
  entities: [{entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
---

# An exercise in use is kept

## Trigger

The exercise is listed in a logged session or a template.

## Outcome

The exercise is not deleted.
