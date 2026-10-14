---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete chooses Start on a Planned session of type Cardio
  kind: actor
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::today'}
- text: The Product opens Log Workout with the planned activity type and segments filled in
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: [Activity type, Planned segments]}, {entity: activity-type, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Athlete adjusts what was actually done and chooses Save Session
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product saves the Cardio session
  kind: product
  actor: athlete
  entities: [{entity: cardio-session, effect: creates, facts: [Date, Title, Activity type, Segments, Total duration, Calories, Average heart rate, Time in heart rate zones, Feeling, Effort, Notes]}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Planned session of that day with the same activity type is now Done
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: changes, from: Planned, to: Done, facts: [Matched session]}, {entity: activity-type, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::log-workout'}
---

# Log a planned cardio session

## Trigger

The Athlete starts a cardio session planned for today.

## Outcome

The cardio session is saved and the planned session shows as Done.
