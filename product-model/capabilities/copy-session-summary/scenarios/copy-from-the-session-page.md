---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete chooses Copy on a Strength session's page
  kind: actor
  actor: athlete
  entities: [{entity: strength-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::session'}
- text: The Product copies the Strength session as text, each exercise with its sets
  kind: product
  actor: athlete
  entities: [{entity: strength-session, effect: reads, facts: [Date, Title, Template, Exercises, Duration, Calories, Feeling, Effort, Notes]}, {entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::session'}
---

# Copy from the session page

## Trigger

The Athlete is looking at a session.

## Outcome

The clipboard holds the session as text.
