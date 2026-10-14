---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Edit on a Planned session and changes it
  kind: actor
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::plan'}
- text: The Product saves the changes
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: changes, facts: [Session type, Template, Template version, Activity type, Title, Notes, Planned segments]}]
  contexts:
    web: {place: 'web::app::plan'}
---

# Edit a planned session

## Trigger

The Athlete wants a different workout on a planned day.

## Outcome

The session shows the new content; it is still Planned.

## Decision points

### Was a different template chosen?

Whether the session now names another strength template.

- A different template → the Product records that template's current version.
- The same template → the version recorded when it was planned is kept.
