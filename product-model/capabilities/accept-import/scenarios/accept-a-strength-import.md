---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete chooses Accept on a strength Import
  kind: actor
  actor: athlete
  entities: [{entity: import, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::imports'}
- text: The Product logs a Strength session from the proposal and marks the Import accepted
  kind: product
  actor: athlete
  entities: [{entity: strength-session, effect: creates, facts: [Date, Title, Duration, Calories, Notes]}, {entity: import, effect: changes, from: Pending, to: Accepted, facts: []}]
  contexts:
    web: {place: 'web::app::imports'}
---

# Accept a strength import

## Trigger

A weight training activity waits in Imports.

## Outcome

A strength session with its date, duration and calories, and no exercises, is logged.
