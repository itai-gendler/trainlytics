---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Edit Session on a Cardio session, changes it and saves
  kind: actor
  actor: athlete
  entities: [{entity: cardio-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::session'}
- text: The Product saves the changes
  kind: product
  actor: athlete
  entities: [{entity: cardio-session, effect: changes, facts: [Date, Title, Activity type, Segments, Total duration, Calories, Average heart rate, Time in heart rate zones, Feeling, Effort, Notes]}]
  contexts:
    web: {place: 'web::app::session'}
---

# Edit a cardio session

## Trigger

A logged cardio session has a mistake.

## Outcome

The session shows the corrected values.
