---
kind: primary
routes:
  web: Web app
steps:
- text: The Product says there is an unsaved draft, naming its title, date and sets done, and holds the form until the Athlete decides
  kind: product
  actor: athlete
  entities: [{entity: workout-draft, effect: reads, facts: [Workout type, Entered values]}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Athlete chooses Restore
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product fills the form from the Workout draft
  kind: product
  actor: athlete
  entities: [{entity: workout-draft, effect: reads, facts: [Entered values, Started at]}]
  contexts:
    web: {place: 'web::app::log-workout'}
---

# Restore on Log Workout

## Trigger

The Athlete opens Log Workout while an unsaved draft of that type exists.

## Outcome

The form holds everything from the draft again.

## Edge cases

- When a planned session is also being started, the Athlete chooses between the draft and the planned session.
