---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete edits an Exercise, chooses Add replacement and picks another Exercise
  kind: actor
  actor: athlete
  entities: [{entity: exercise, effect: reads, facts: [Name, Exercise types]}]
  contexts:
    web: {place: 'web::app::settings'}
- text: The Product adds it to the exercise's replacements
  kind: product
  actor: athlete
  entities: [{entity: exercise, effect: changes, facts: [Replacements]}]
  contexts:
    web: {place: 'web::app::settings'}
---

# Add a replacement

## Trigger

The Athlete has an alternative for an exercise when equipment is busy or something hurts.

## Outcome

The exercise lists the replacement.
