---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses + Add under Exercises and enters a name, notes, exercise types and weight steps
  kind: actor
  actor: athlete
  entities: [{entity: exercise-type, effect: reads, facts: [Name]}, {entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
- text: The Product saves the Exercise
  kind: product
  actor: athlete
  entities: [{entity: exercise, effect: creates, facts: [Name, Notes, Exercise types, Weight steps, Replacements]}]
  contexts:
    web: {place: 'web::app::settings'}
---

# Add an exercise in Settings

## Trigger

The Athlete starts doing a new exercise.

## Outcome

The exercise can be logged, put in templates and given replacements.

## Edge cases

- Without a weight steps choice the exercise uses the default 10 lb stack.
