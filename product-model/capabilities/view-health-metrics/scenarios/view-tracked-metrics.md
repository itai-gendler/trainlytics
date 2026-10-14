---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete opens Stats › Analytics
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::analytics'}
- text: The Product charts each tracked metric of the Health metrics for the chosen period
  kind: product
  actor: athlete
  entities: [{entity: athlete, effect: reads, facts: [Tracked health metrics]}, {entity: health-metrics, effect: reads, facts: [Date, Resting heart rate, HRV, Body weight, Sleep, VO2 max, Active energy]}]
  contexts:
    web: {place: 'web::app::analytics'}
---

# View tracked metrics

## Trigger

The Athlete opens the Health Metrics section.

## Outcome

Each tracked metric is charted day by day for the chosen period; untracked metrics are not shown.
