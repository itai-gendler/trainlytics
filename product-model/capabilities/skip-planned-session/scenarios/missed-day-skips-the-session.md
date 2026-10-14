---
kind: edge
routes:
  web: Web app
steps:
- text: The planned day of a Planned session has passed and no matching session was logged on it
  kind: condition
  unattended: true
  entities: [{entity: planned-session, effect: reads, facts: [Planned date]}]
  contexts:
    web: {place: 'web::app::plan'}
- text: The Product shows the Planned session as Skipped
  kind: product
  entities: [{entity: planned-session, effect: changes, from: Planned, to: Skipped, facts: []}]
  contexts:
    web: {place: 'web::app::plan'}
---

# A missed day skips the session

## Trigger

The day of a Planned session ends without a matching session logged on it.

## Outcome

The session shows as Skipped on the plan, where a reason can be added.
