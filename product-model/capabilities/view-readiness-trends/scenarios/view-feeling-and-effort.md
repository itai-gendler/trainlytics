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
- text: The Product shows weekly average feeling and effort, and each session's feeling against its effort
  kind: product
  actor: athlete
  entities: [{entity: cardio-session, effect: reads, facts: [Date, Feeling, Effort]}, {entity: strength-session, effect: reads, facts: [Date, Feeling, Effort]}]
  contexts:
    web: {place: 'web::app::analytics'}
---

# View feeling and effort

## Trigger

The Athlete opens the Readiness section.

## Outcome

Weekly average feeling and effort, and each session's feeling against its effort, are shown.
