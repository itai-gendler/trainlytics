---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete picks a Strength template
  kind: actor
  actor: athlete
  entities: [{entity: strength-template, effect: reads, facts: [Name]}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product fills in the template's exercises and sets and its name as the title
  kind: product
  actor: athlete
  entities: [{entity: strength-template, effect: reads, facts: [Name, Exercises]}, {entity: workout-draft, effect: creates, facts: [Workout type, Entered values, Started at]}, {entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Athlete records reps, weight and effort for each set, marks sets done, and chooses Save Session
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The session's exercises and sets match the template
  kind: condition
  actor: athlete
  entities: [{entity: strength-template, effect: reads, facts: [Exercises]}, {entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product saves the Strength session, clears the Workout draft and opens the new session
  kind: product
  actor: athlete
  entities: [{entity: strength-session, effect: creates, facts: [Date, Title, Template, Exercises, Duration, Calories, Feeling, Effort, Notes]}, {entity: workout-draft, effect: removes}]
  contexts:
    web: {place: 'web::app::log-workout'}
---

# Log a strength session from a template

## Trigger

The Athlete trains one of their templates and opens Log Workout with it.

## Outcome

A strength session matching the template is saved and its page opens.

## Edge cases

- Which sets are marked done is never saved with the session.
- A template that does not load within 10 seconds shows an error with Retry.
