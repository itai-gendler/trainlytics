---
kind: edge
routes:
  web: Web app
steps:
- text: The Athlete chooses Save Session
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The save does not reach the server
  kind: condition
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product keeps the form and the Workout draft and offers to retry
  kind: product
  actor: athlete
  entities: [{entity: workout-draft, effect: reads, facts: [Entered values]}]
  contexts:
    web: {place: 'web::app::log-workout'}
---

# A failed save keeps the draft

## Trigger

Saving fails, for example while the phone has no connection.

## Outcome

Nothing is lost: the form and the draft stay, with Retry.
