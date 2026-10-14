---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Discard on the unsaved draft
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product deletes the Workout draft
  kind: product
  actor: athlete
  entities: [{entity: workout-draft, effect: removes}]
  contexts:
    web: {place: 'web::app::log-workout'}
---

# Discard and start fresh

## Trigger

An unsaved draft is waiting but the Athlete wants a new workout.

## Outcome

The draft is gone and an empty form, or the template asked for, is ready.
