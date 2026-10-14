---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete picks 60, 90, 120 or 180 seconds under Rest timer
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::settings'}
- text: The Product saves the rest timer length
  kind: product
  actor: athlete
  entities: [{entity: athlete, effect: changes, facts: [Rest timer length]}]
  contexts:
    web: {place: 'web::app::settings'}
---

# Pick a rest length

## Trigger

The Athlete wants longer or shorter rests.

## Outcome

Workout mode's rest timer runs for the chosen length on every device.
