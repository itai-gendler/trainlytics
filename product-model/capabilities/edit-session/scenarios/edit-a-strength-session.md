---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete edits a Strength session's exercises, sets and details and saves
  kind: actor
  actor: athlete
  entities: [{entity: strength-session, effect: reads, facts: []}, {entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::session'}
- text: The Product saves the changes
  kind: product
  actor: athlete
  entities: [{entity: strength-session, effect: changes, facts: [Date, Title, Exercises, Duration, Calories, Feeling, Effort, Notes]}]
  contexts:
    web: {place: 'web::app::session'}
---

# Edit a strength session

## Trigger

A logged strength session has a mistake.

## Outcome

The session shows the corrected exercises and sets.

## Edge cases

- Moving a session to another day can change which planned session it completes.
