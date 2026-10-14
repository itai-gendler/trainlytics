---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete picks Cardio and an Activity type and enters segments with duration and distance
  kind: actor
  actor: athlete
  entities: [{entity: activity-type, effect: reads, facts: [Name]}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product calculates each segment's pace and keeps what is entered as a Workout draft on this device
  kind: product
  actor: athlete
  entities: [{entity: workout-draft, effect: creates, facts: [Workout type, Entered values, Started at]}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Athlete adds feeling, effort, heart rate, time in zones, calories, a title and notes, and chooses Save Session
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product saves the Cardio session, clears the Workout draft and opens the new session
  kind: product
  actor: athlete
  entities: [{entity: cardio-session, effect: creates, facts: [Date, Title, Activity type, Segments, Total duration, Calories, Average heart rate, Time in heart rate zones, Feeling, Effort, Notes]}, {entity: workout-draft, effect: removes}]
  contexts:
    web: {place: 'web::app::log-workout'}
---

# Log a cardio session

## Trigger

The Athlete finished a run, ride or other cardio and opens Log Workout.

## Outcome

A new cardio session is saved and its page opens.

## Edge cases

- A typed pace overrides the calculated one.
- Without a title the form suggests one such as "Run – 8 km".
