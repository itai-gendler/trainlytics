---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete adds an Exercise to the session
  kind: actor
  actor: athlete
  entities: [{entity: exercise, effect: reads, facts: [Name, Notes]}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product fills its sets with the reps and weight of the last Strength session that had it
  kind: product
  actor: athlete
  entities: [{entity: strength-session, as: last-time, effect: reads, facts: [Date, Exercises]}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Athlete records the sets and chooses Save Session
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product saves the Strength session
  kind: product
  actor: athlete
  entities: [{entity: strength-session, as: new, effect: creates, facts: [Date, Title, Template, Exercises, Duration, Calories, Feeling, Effort, Notes]}]
  contexts:
    web: {place: 'web::app::log-workout'}
---

# Add an exercise with last session's sets

## Trigger

The Athlete adds an exercise that is not in the template, or logs without a template.

## Outcome

The new exercise starts with the sets last logged for it, shown as filled from last session.

## Edge cases

- Set effort is never prefilled.
- An exercise never logged before starts with empty sets (three in workout mode).
