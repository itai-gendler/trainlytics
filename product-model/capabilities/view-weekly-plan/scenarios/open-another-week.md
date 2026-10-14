---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete moves to the next week
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::plan'}
- text: The Product starts an empty Weekly plan for that week the first time it is opened
  kind: product
  actor: athlete
  entities: [{entity: weekly-plan, effect: creates, facts: [Week start]}]
  contexts:
    web: {place: 'web::app::plan'}
---

# Open another week

## Trigger

The Athlete moves to the previous or next week.

## Outcome

The chosen week's plan is shown; a week never opened before starts empty.

## Edge cases

- An empty week offers Copy from last week.
