---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Delete on an Exercise
  kind: actor
  actor: athlete
  entities: [{entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
- text: No Strength session or Strength template lists the Exercise
  kind: condition
  actor: athlete
  entities: [{entity: strength-session, effect: reads, facts: [Exercises]}, {entity: strength-template, effect: reads, facts: [Exercises]}, {entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
- text: The Product deletes the Exercise
  kind: product
  actor: athlete
  entities: [{entity: exercise, effect: removes}]
  contexts:
    web: {place: 'web::app::settings'}
---

# Delete an unused exercise

## Trigger

The Athlete added an exercise they never used.

## Outcome

The exercise is gone, and so is it from other exercises' replacements.

## Edge cases

- Other exercises that listed it as a replacement no longer do.
