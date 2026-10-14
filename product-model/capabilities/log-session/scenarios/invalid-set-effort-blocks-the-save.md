---
kind: validation
routes:
  web: Web app
steps:
- text: The Athlete chooses Save Session with a set effort outside 1 to 10
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product refuses to save and names the exercise and set
  kind: product
  actor: athlete
  entities: [{entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::log-workout'}
---

# An invalid set effort blocks the save

## Trigger

A set effort outside 1 to 10 is entered, for example from an old draft.

## Outcome

Nothing is saved; the message names the exercise and set to fix.
