---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete enters a date and a step count and chooses Add entry
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::steps'}
- text: The Product saves the Daily steps
  kind: product
  actor: athlete
  entities: [{entity: daily-steps, effect: creates, facts: [Date, Steps]}]
  contexts:
    web: {place: 'web::app::steps'}
---

# Add a day's steps

## Trigger

The Athlete wants to record today's steps.

## Outcome

The day's count is listed and shows in the weekly steps on History.
