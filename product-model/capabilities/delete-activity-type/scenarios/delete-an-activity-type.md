---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Delete on an Activity type
  kind: actor
  actor: athlete
  entities: [{entity: activity-type, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
- text: The Product deletes the Activity type
  kind: product
  actor: athlete
  entities: [{entity: activity-type, effect: removes}]
  contexts:
    web: {place: 'web::app::settings'}
- text: Cardio sessions and Planned sessions of that type no longer name one
  kind: product
  actor: athlete
  entities: [{entity: cardio-session, effect: changes, facts: [Activity type]}, {entity: planned-session, effect: changes, facts: [Activity type]}]
  contexts:
    web: {place: 'web::app::settings'}
---

# Delete an activity type

## Trigger

The Athlete no longer does a kind of cardio.

## Outcome

The type is gone; sessions and plans that had it remain without one.
