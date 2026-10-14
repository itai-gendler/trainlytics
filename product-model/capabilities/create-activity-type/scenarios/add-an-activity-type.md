---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses + Add under Activity Types, enters a name and saves
  kind: actor
  actor: athlete
  entities: [{entity: activity-type, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
- text: The Product saves the Activity type
  kind: product
  actor: athlete
  entities: [{entity: activity-type, effect: creates, facts: [Name]}]
  contexts:
    web: {place: 'web::app::settings'}
---

# Add an activity type

## Trigger

The Athlete does a kind of cardio not listed yet.

## Outcome

The activity type can be picked when logging, planning and importing.
