---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Reschedule on a planned session and picks a day of the same week that has not passed
  kind: actor
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::plan'}
- text: The Product moves the Planned session to that day
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: changes, facts: [Planned date]}]
  contexts:
    web: {place: 'web::app::plan'}
---

# Reschedule within the week

## Trigger

The Athlete wants to do a planned session on another day.

## Outcome

The session sits on the chosen day.
