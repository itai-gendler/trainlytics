---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Edit on an Activity type, changes the name and saves
  kind: actor
  actor: athlete
  entities: [{entity: activity-type, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
- text: The Product saves the name
  kind: product
  actor: athlete
  entities: [{entity: activity-type, effect: changes, facts: [Name]}]
  contexts:
    web: {place: 'web::app::settings'}
---

# Rename an activity type

## Trigger

The Athlete wants a different name.

## Outcome

Everywhere the type appears it has the new name.
