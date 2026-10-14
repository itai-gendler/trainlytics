---
kind: edge
routes:
  web: Web app
steps:
- text: The Athlete chooses Analyse this week
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::history'}
- text: The language model call fails
  kind: condition
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::history'}
- text: The Product says the AI call failed and offers Retry
  kind: product
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::history'}
---

# The AI service fails

## Trigger

The language model call fails.

## Outcome

An error with Retry is shown.
