---
kind: primary
result: achieved
routes:
  web: Web app
steps:
- text: The Athlete logs the run's segments, feeling and effort and chooses Save Session
  kind: actor
  actor: athlete
  capability: log-session
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product saves the Cardio session and opens it
  kind: product
  actor: athlete
  capability: log-session
  entities: [{entity: cardio-session, effect: creates, facts: [Date, Title, Activity type, Segments, Total duration, Calories, Average heart rate, Time in heart rate zones, Feeling, Effort, Notes]}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Athlete chooses Copy on the new session
  kind: actor
  actor: athlete
  capability: copy-session-summary
  entities: []
  contexts:
    web: {place: 'web::app::session'}
- text: The Product copies the Cardio session as text
  kind: product
  actor: athlete
  capability: copy-session-summary
  entities: [{entity: cardio-session, effect: reads, facts: [Date, Title, Activity type, Segments, Total duration, Calories, Average heart rate, Time in heart rate zones, Feeling, Effort, Notes]}]
  contexts:
    web: {place: 'web::app::session'}
---

# Log a run and copy it

## Trigger

The Athlete finished a run they want feedback on.

## Outcome

The run is logged and its text summary is ready to paste.
