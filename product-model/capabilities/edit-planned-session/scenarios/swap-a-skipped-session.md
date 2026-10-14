---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete chooses Swap on a Skipped planned session and picks other content
  kind: actor
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::plan'}
- text: The Product saves the new content
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: changes, facts: [Session type, Template, Template version, Activity type, Title, Notes, Planned segments]}]
  contexts:
    web: {place: 'web::app::plan'}
---

# Swap a skipped session

## Trigger

A session was missed and the Athlete wants to replace it with something else.

## Outcome

The skipped day shows the new content and can be started on its planned date.
