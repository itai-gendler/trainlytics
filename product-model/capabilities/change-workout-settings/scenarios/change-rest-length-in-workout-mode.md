---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete picks a rest length in workout mode's options
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::workout-mode'}
- text: The Product applies it at once and saves the rest timer length
  kind: product
  actor: athlete
  entities: [{entity: athlete, effect: changes, facts: [Rest timer length]}]
  contexts:
    web: {place: 'web::app::workout-mode'}
---

# Change the rest length in workout mode

## Trigger

Mid-workout, the Athlete wants a different rest.

## Outcome

The new length applies at once and is saved for every device.

## Edge cases

- If saving fails, the length still applies on this device and is saved later.
