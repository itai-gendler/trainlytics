---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete picks a type and a date range
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::history'}
- text: The Product lists only the matching sessions
  kind: product
  actor: athlete
  entities: [{entity: cardio-session, effect: reads, facts: [Date]}, {entity: strength-session, effect: reads, facts: [Date]}]
  contexts:
    web: {place: 'web::app::history'}
---

# Filter by type and dates

## Trigger

The Athlete looks for particular sessions.

## Outcome

Only sessions of the chosen type between the chosen dates are listed.
