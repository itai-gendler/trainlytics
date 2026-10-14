---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete opens Stats › Analytics
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::analytics'}
- text: The Product charts done and skipped Planned sessions per past week, and planned against actual strength volume and cardio distance
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: [Planned date, Session type, Template, Activity type, Planned segments]}, {entity: strength-template, effect: reads, facts: [Exercises]}, {entity: strength-session, effect: reads, facts: [Date, Template, Exercises]}, {entity: cardio-session, effect: reads, facts: [Date, Activity type, Segments]}]
  contexts:
    web: {place: 'web::app::analytics'}
---

# View weekly adherence

## Trigger

The Athlete opens the Plan Adherence section.

## Outcome

Done and skipped counts and planned against actual strength volume and cardio distance are charted for the past twelve completed weeks.
