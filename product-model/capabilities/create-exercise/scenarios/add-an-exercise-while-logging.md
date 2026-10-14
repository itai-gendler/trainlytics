---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete types a new exercise name in the strength form and chooses Create
  kind: actor
  actor: athlete
  entities: [{entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product saves the Exercise and puts it in the session
  kind: product
  actor: athlete
  entities: [{entity: exercise, effect: creates, facts: [Name, Notes, Exercise types, Weight steps, Replacements]}]
  contexts:
    web: {place: 'web::app::log-workout'}
---

# Add an exercise while logging

## Trigger

The exercise the Athlete is doing is not in the library yet.

## Outcome

The new exercise is created and placed in the session being logged.
