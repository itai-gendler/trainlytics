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
- text: The language model call fails
  kind: condition
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product says the AI call failed and offers Retry
  kind: product
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
---

# The AI service fails

## Trigger

The language model call fails or the key is rejected.

## Outcome

An error with Retry is shown; nothing changes.
