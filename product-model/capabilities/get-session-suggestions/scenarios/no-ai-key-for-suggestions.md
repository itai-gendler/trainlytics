---
kind: edge
routes:
  web: Web app
steps:
- text: The Athlete chooses Get suggestions
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Athlete has no AI key saved
  kind: condition
  actor: athlete
  entities: [{entity: athlete, effect: reads, facts: [AI key]}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product says no AI API key is configured and to add one in the profile
  kind: product
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
---

# No AI key

## Trigger

The Athlete has not saved an AI key.

## Outcome

No suggestions; the Product points to Profile to add a key.
