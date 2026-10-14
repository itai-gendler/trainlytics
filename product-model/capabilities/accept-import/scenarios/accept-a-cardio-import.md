---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Accept on a cardio Import
  kind: actor
  actor: athlete
  entities: [{entity: import, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::imports'}
- text: No session logged within a day of it has a duration within a minute of it
  kind: condition
  actor: athlete
  entities: [{entity: cardio-session, effect: reads, facts: [Date, Total duration]}, {entity: strength-session, effect: reads, facts: [Date, Duration]}]
  contexts:
    web: {place: 'web::app::imports'}
- text: The Product logs a Cardio session from the proposal and marks the Import accepted
  kind: product
  actor: athlete
  entities: [{entity: activity-type, effect: reads, facts: [Name]}, {entity: cardio-session, effect: creates, facts: [Date, Title, Activity type, Segments, Total duration, Calories, Average heart rate, Notes]}, {entity: import, effect: changes, from: Pending, to: Accepted, facts: []}]
  contexts:
    web: {place: 'web::app::imports'}
---

# Accept a cardio import

## Trigger

A run or ride from Strava or Apple Health waits in Imports.

## Outcome

A cardio session with the imported segments, duration, distance, calories and heart rate is logged; the import is accepted.
