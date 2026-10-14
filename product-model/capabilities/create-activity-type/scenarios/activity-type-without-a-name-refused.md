---
kind: validation
routes:
  web: Web app
steps:
- text: The Athlete saves an activity type with no name
  kind: actor
  actor: athlete
  entities: [{entity: activity-type, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::settings'}
- text: The Product says the name is required
  kind: product
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::settings'}
---

# An activity type without a name is refused

## Trigger

The Athlete saves an empty name.

## Outcome

Nothing is saved; the form says the name is required.
