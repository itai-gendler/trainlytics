---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Add Session on a day, picks Strength and a Strength template
  kind: actor
  actor: athlete
  entities: [{entity: strength-template, effect: reads, facts: [Name]}]
  contexts:
    web: {place: 'web::app::plan'}
- text: The Product adds a Planned session recording the template's current version
  kind: product
  actor: athlete
  entities: [{entity: strength-template, effect: reads, facts: [Name, Version]}, {entity: planned-session, effect: creates, to: Planned, facts: [Planned date, Session type, Template, Template version, Title, Notes, Order]}]
  contexts:
    web: {place: 'web::app::plan'}
---

# Plan a strength session

## Trigger

The Athlete wants to do a template on a day of the week.

## Outcome

The day shows the new session as Planned, titled after the template unless the Athlete gave it a title.
