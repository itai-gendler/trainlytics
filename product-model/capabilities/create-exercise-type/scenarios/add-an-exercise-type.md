---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses + Add under Exercise Types, enters a name and saves
  kind: actor
  actor: athlete
  entities: [{entity: exercise-type, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
- text: The Product saves the Exercise type
  kind: product
  actor: athlete
  entities: [{entity: exercise-type, effect: creates, facts: [Name]}]
  contexts:
    web: {place: 'web::app::settings'}
---

# Add an exercise type

## Trigger

The Athlete wants to group exercises in a new way.

## Outcome

The tag can be put on exercises and appears in strength analytics.
