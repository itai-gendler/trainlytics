---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete opens a Strength session
  kind: actor
  actor: athlete
  entities: [{entity: strength-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::session'}
- text: The Product shows its exercises with every set's reps, weight, effort and note, duration, feeling, effort, calories and notes
  kind: product
  actor: athlete
  entities: [{entity: strength-session, effect: reads, facts: [Date, Title, Template, Exercises, Duration, Calories, Feeling, Effort, Notes]}, {entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::session'}
---

# View a strength session

## Trigger

The Athlete opens a strength session.

## Outcome

Every exercise with its sets, and the session's totals, feeling, effort and notes are shown.
