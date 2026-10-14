---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete enters steps for a date that already has an entry
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::steps'}
- text: The Product replaces that day's count
  kind: product
  actor: athlete
  entities: [{entity: daily-steps, effect: changes, facts: [Steps]}]
  contexts:
    web: {place: 'web::app::steps'}
---

# Replace a day's steps

## Trigger

The Athlete enters steps for a day that already has a count.

## Outcome

The day keeps one count, the new one.
