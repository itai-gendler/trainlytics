---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete chooses Add Session, picks Cardio, an Activity type and enters at least one segment
  kind: actor
  actor: athlete
  entities: [{entity: activity-type, effect: reads, facts: [Name]}]
  contexts:
    web: {place: 'web::app::plan'}
- text: The Product adds the Planned session
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: creates, to: Planned, facts: [Planned date, Session type, Activity type, Title, Notes, Planned segments, Order]}]
  contexts:
    web: {place: 'web::app::plan'}
---

# Plan a cardio session

## Trigger

The Athlete wants to do a run, ride or other cardio on a day of the week.

## Outcome

The day shows the new cardio session as Planned with its segments.
