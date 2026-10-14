---
kind: validation
routes:
  web: Web app
steps:
- text: The Athlete asks to copy last week into a week that has sessions
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::plan'}
- text: The Weekly plan already holds Planned sessions
  kind: condition
  actor: athlete
  entities: [{entity: weekly-plan, effect: reads, facts: []}, {entity: planned-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::plan'}
- text: The Product refuses and says the week already has a plan
  kind: product
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::plan'}
---

# A week that already has sessions is not overwritten

## Trigger

The Athlete tries to copy into a week that already has sessions.

## Outcome

Nothing changes; the Product says the week already has a plan.
