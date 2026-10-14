---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Compare planned vs. actual on a Done strength session
  kind: actor
  actor: athlete
  entities: [{entity: strength-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::plan'}
- text: The Product compares the template version the session was planned with against the Strength session that completed it
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: [Template, Template version, Matched session]}, {entity: strength-template, effect: reads, facts: [Version history]}, {entity: strength-session, effect: reads, facts: [Exercises]}]
  contexts:
    web: {place: 'web::app::plan'}
---

# Compare a strength session

## Trigger

A planned strength session is Done.

## Outcome

Each exercise shows planned and actual sets and volume, including exercises only planned or only done, and the totals with their difference.
