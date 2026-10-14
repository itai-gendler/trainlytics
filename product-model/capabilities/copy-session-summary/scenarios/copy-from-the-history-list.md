---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Copy on a session in History
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::history'}
- text: 'The Product copies the Cardio session as text: title, date, type, duration, distance, calories, feeling, effort, each segment with distance, duration and pace, and notes'
  kind: product
  actor: athlete
  entities: [{entity: cardio-session, effect: reads, facts: [Date, Title, Activity type, Segments, Total duration, Calories, Average heart rate, Time in heart rate zones, Feeling, Effort, Notes]}]
  contexts:
    web: {place: 'web::app::history'}
---

# Copy from the history list

## Trigger

The Athlete wants to share a session.

## Outcome

The clipboard holds the session as text and the button briefly says Copied!

## Edge cases

- A strength session lists each exercise with its sets as weight × reps and set effort.
