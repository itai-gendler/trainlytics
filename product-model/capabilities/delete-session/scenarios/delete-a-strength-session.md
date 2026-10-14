---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete chooses Delete on a Strength session and confirms
  kind: actor
  actor: athlete
  entities: [{entity: strength-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::session'}
- text: The Product deletes the Strength session
  kind: product
  actor: athlete
  entities: [{entity: strength-session, effect: removes}]
  contexts:
    web: {place: 'web::app::session'}
---

# Delete a strength session

## Trigger

A strength session was logged twice.

## Outcome

The session is gone and Today opens.
