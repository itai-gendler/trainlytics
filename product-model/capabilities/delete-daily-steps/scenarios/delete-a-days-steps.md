---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Delete on a day's entry and confirms
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::steps'}
- text: The Product deletes the Daily steps
  kind: product
  actor: athlete
  entities: [{entity: daily-steps, effect: removes}]
  contexts:
    web: {place: 'web::app::steps'}
---

# Delete a day's steps

## Trigger

A step count was entered by mistake.

## Outcome

The entry is gone.
