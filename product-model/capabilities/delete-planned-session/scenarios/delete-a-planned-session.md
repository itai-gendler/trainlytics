---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Delete on a planned session and confirms
  kind: actor
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::plan'}
- text: The Product removes the Planned session
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: removes, from: Planned}]
  contexts:
    web: {place: 'web::app::plan'}
---

# Delete a planned session

## Trigger

The Athlete no longer wants a session in the plan.

## Outcome

The session is gone from the week.

## Edge cases

- A skipped session is deleted the same way; a done one offers no Delete.
