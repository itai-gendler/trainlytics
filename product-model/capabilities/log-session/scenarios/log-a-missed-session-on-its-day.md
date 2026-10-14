---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete chooses Start on a Skipped planned session
  kind: actor
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::plan'}
- text: The Product opens Log Workout dated on the planned day
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: [Planned date, Template]}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Athlete enters the sets and chooses Save Session
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product saves the Strength session
  kind: product
  actor: athlete
  entities: [{entity: strength-session, effect: creates, facts: [Date, Title, Template, Exercises, Duration, Calories, Feeling, Effort, Notes]}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Planned session is now Done
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: changes, from: Skipped, to: Done, facts: [Matched session]}]
  contexts:
    web: {place: 'web::app::log-workout'}
---

# Log a missed session on its planned day

## Trigger

The Athlete did a skipped session but did not log it on the day.

## Outcome

The session is saved on the planned day and the planned session turns from Skipped to Done.
