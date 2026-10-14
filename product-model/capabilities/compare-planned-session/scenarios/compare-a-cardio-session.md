---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete chooses Compare planned vs. actual on a Done cardio session
  kind: actor
  actor: athlete
  entities: [{entity: cardio-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::plan'}
- text: The Product compares the planned segments' distance and duration with the Cardio session that completed it
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: [Planned segments, Matched session]}, {entity: cardio-session, effect: reads, facts: [Segments, Total duration]}]
  contexts:
    web: {place: 'web::app::plan'}
---

# Compare a cardio session

## Trigger

A planned cardio session is Done.

## Outcome

Planned and actual distance and duration are shown side by side.
