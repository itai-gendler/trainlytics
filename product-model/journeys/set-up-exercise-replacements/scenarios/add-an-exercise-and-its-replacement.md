---
kind: primary
result: achieved
routes:
  web: Web app
steps:
- text: The Athlete fills in a new exercise and chooses to save it and add a replacement
  kind: actor
  actor: athlete
  capability: create-exercise
  entities: [{entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
- text: The Product saves the Exercise and opens its editor with the replacement picker
  kind: product
  actor: athlete
  capability: create-exercise
  entities: [{entity: exercise, effect: creates, facts: [Name, Notes, Exercise types, Weight steps, Replacements]}]
  contexts:
    web: {place: 'web::app::settings'}
- text: The Athlete picks another Exercise as its replacement
  kind: actor
  actor: athlete
  capability: add-exercise-replacement
  entities: [{entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
- text: The Product adds it to the new exercise's replacements
  kind: product
  actor: athlete
  capability: add-exercise-replacement
  entities: [{entity: exercise, effect: changes, facts: [Replacements]}]
  contexts:
    web: {place: 'web::app::settings'}
---

# Add an exercise and its replacement

## Trigger

The Athlete adds an exercise that has an obvious alternative.

## Outcome

The exercise is saved with its replacement.
