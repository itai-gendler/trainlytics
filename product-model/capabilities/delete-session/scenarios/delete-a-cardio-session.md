---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Delete on a Cardio session and confirms
  kind: actor
  actor: athlete
  entities: [{entity: cardio-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::session'}
- text: The Product deletes the Cardio session
  kind: product
  actor: athlete
  entities: [{entity: cardio-session, effect: removes}]
  contexts:
    web: {place: 'web::app::session'}
---

# Delete a cardio session

## Trigger

A cardio session was logged by mistake.

## Outcome

The session is gone and Today opens.

## Edge cases

- A planned session it completed is no longer Done.
