---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete logs a session from a Strength template with changes and chooses Save Session
  kind: actor
  actor: athlete
  entities: [{entity: strength-template, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product lists how the session differs from the template and asks whether to update it
  kind: product
  actor: athlete
  entities: [{entity: strength-template, effect: reads, facts: [Exercises]}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Athlete chooses to keep the template
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product saves the Strength session and opens it
  kind: product
  actor: athlete
  entities: [{entity: strength-session, effect: creates, facts: [Date, Title, Template, Exercises, Duration, Calories, Feeling, Effort, Notes]}]
  contexts:
    web: {place: 'web::app::log-workout'}
---

# Keep the template unchanged

## Trigger

The Athlete did a template differently just this once.

## Outcome

Only the session is saved; the template is unchanged.
