---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete turns Include workouts off and uploads the export
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::connections'}
- text: The Product saves each day's tracked Health metrics
  kind: product
  actor: athlete
  entities: [{entity: athlete, effect: reads, facts: [Tracked health metrics]}, {entity: health-metrics, effect: creates, facts: [Date, Resting heart rate, HRV, Body weight, Sleep, VO2 max, Active energy]}]
  contexts:
    web: {place: 'web::app::connections'}
---

# Import metrics only

## Trigger

The Athlete logs workouts by hand and only wants health metrics.

## Outcome

Only health metrics are saved; nothing is added to Imports.
