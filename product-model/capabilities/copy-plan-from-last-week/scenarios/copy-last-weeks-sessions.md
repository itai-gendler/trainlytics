---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Copy from last week on an empty week
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::plan'}
- text: The Product copies each Planned session of the previous Weekly plan seven days later, with each template's current version and no skip note
  kind: product
  actor: athlete
  entities: [{entity: weekly-plan, effect: reads, facts: [Week start]}, {entity: planned-session, as: last-week, effect: reads, facts: [Planned date, Session type, Template, Activity type, Title, Notes, Planned segments, Order]}, {entity: strength-template, effect: reads, facts: [Version]}, {entity: planned-session, as: this-week, effect: creates, to: Planned, facts: [Planned date, Session type, Template, Template version, Activity type, Title, Notes, Planned segments, Order]}]
  contexts:
    web: {place: 'web::app::plan'}
---

# Copy last week's sessions

## Trigger

The Athlete opens an empty week and wants to repeat last week.

## Outcome

The week holds a copy of every session of the previous week on the same weekdays, all Planned and without skip notes.

## Edge cases

- When last week has no sessions, nothing is added.
