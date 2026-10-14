---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete turns a metric off under Tracked metrics
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::connections'}
- text: The Product saves the choice
  kind: product
  actor: athlete
  entities: [{entity: athlete, effect: changes, facts: [Tracked health metrics]}]
  contexts:
    web: {place: 'web::app::connections'}
---

# Stop tracking a metric

## Trigger

The Athlete does not want, say, body weight in Trainlytics.

## Outcome

The metric is no longer imported, charted or sent to the AI coach.

## Edge cases

- Turning a metric back on charts the values already imported.
