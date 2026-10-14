---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete opens Today
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::today'}
- text: The Product shows each Planned session dated today with its title, planned segments, status and skip note
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: [Planned date, Session type, Title, Planned segments, Skip note]}]
  contexts:
    web: {place: 'web::app::today'}
- text: The Product shows a Resume card for each Workout draft with its type and how long ago it started
  kind: product
  actor: athlete
  entities: [{entity: workout-draft, effect: reads, facts: [Workout type, Started at]}]
  contexts:
    web: {place: 'web::app::today'}
- text: The Product shows this week's done, planned and skipped counts, the completion and the next Planned session
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: [Planned date, Title]}]
  contexts:
    web: {place: 'web::app::today'}
---

# View today's sessions and this week

## Trigger

The Athlete opens Trainlytics or chooses Today.

## Outcome

The Athlete sees today's planned sessions with their status, a Resume card per draft, and this week's progress.

## Edge cases

- Nothing planned today shows "Nothing planned today." with the Quick log choices still offered.
