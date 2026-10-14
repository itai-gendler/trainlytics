---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete opens Plan
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::plan'}
- text: The Product shows the Weekly plan's days with each Planned session's title, type, segments, status and skip note
  kind: product
  actor: athlete
  entities: [{entity: weekly-plan, effect: reads, facts: [Week start]}, {entity: planned-session, effect: reads, facts: [Planned date, Session type, Title, Planned segments, Skip note, Order]}]
  contexts:
    web: {place: 'web::app::plan'}
- text: The Product shows the planned, done and skipped counts and the completion of done against done and skipped
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::plan'}
- text: The Product compares planned cardio distance and time and strength exercises and volume with the done sessions
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: [Planned segments, Template]}, {entity: strength-template, effect: reads, facts: [Exercises]}, {entity: cardio-session, effect: reads, facts: [Segments, Total duration]}, {entity: strength-session, effect: reads, facts: [Exercises]}, {entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::plan'}
---

# View this week's plan

## Trigger

The Athlete opens Plan.

## Outcome

The Athlete sees the current Monday-to-Sunday week with every planned session's status and how planned volume compares with what was done.
