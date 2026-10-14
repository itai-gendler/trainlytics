---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete logs a session from a Strength template, changing exercises or sets, and chooses Save Session
  kind: actor
  actor: athlete
  entities: [{entity: strength-template, effect: reads, facts: []}, {entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product lists how the session differs from the template and asks whether to update it
  kind: product
  actor: athlete
  entities: [{entity: strength-template, effect: reads, facts: [Exercises]}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Athlete chooses to update the template
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product saves the session's exercises and sets to the Strength template as a new version
  kind: product
  actor: athlete
  entities: [{entity: strength-template, effect: changes, facts: [Exercises, Version, Version history]}, {entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product saves the Strength session and opens it
  kind: product
  actor: athlete
  entities: [{entity: strength-session, effect: creates, facts: [Date, Title, Template, Exercises, Duration, Calories, Feeling, Effort, Notes]}]
  contexts:
    web: {place: 'web::app::log-workout'}
---

# Update the template from the session

## Trigger

The Athlete did a template differently and wants the template to follow.

## Outcome

The template takes the session's exercises and sets as a new version, and the session is saved.

## Edge cases

- Set notes and set effort are never written to the template.
- If the save then fails, a retry neither asks again nor updates the template twice.
