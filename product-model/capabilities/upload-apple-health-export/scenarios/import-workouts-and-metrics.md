---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses the export zip with Include workouts on and uploads it
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::connections'}
- text: The Product reads the export in the background, showing progress until it is done
  kind: product
  actor: athlete
  entities: [{entity: athlete, effect: reads, facts: [Tracked health metrics]}]
  contexts:
    web: {place: 'web::app::connections'}
- text: The Product stages each workout as an Import and saves each day's tracked Health metrics
  kind: product
  actor: athlete
  entities: [{entity: activity-type, effect: reads, facts: [Name]}, {entity: import, effect: creates, to: Pending, facts: [Source, Proposed session, Suggested activity type]}, {entity: health-metrics, effect: creates, facts: [Date, Resting heart rate, HRV, Body weight, Sleep, VO2 max, Active energy]}]
  contexts:
    web: {place: 'web::app::connections'}
- text: The Product reports how many workouts were staged and how many days of metrics were saved
  kind: product
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::connections'}
---

# Import workouts and metrics

## Trigger

The Athlete exported all health data on their iPhone.

## Outcome

Workouts wait in Imports and tracked metrics show in Analytics; the Product reports how many of each it took.

## Edge cases

- A day already imported takes the newer values.
- A workout already accepted or discarded is not staged again.
