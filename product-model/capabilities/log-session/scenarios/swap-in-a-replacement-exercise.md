---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete chooses Swap exercise on an Exercise and picks one of its replacements
  kind: actor
  actor: athlete
  entities: [{entity: exercise, effect: reads, facts: [Name, Replacements]}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product puts the replacement in its place, with the sets last logged for it
  kind: product
  actor: athlete
  entities: [{entity: strength-session, as: last-time, effect: reads, facts: [Exercises]}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Athlete chooses Save Session
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

# Swap an exercise for a replacement

## Trigger

A machine is taken or an exercise does not suit today.

## Outcome

The session lists the replacement in that exercise's place.
