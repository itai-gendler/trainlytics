---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete changes an Import's date, activity type, title or notes
  kind: actor
  actor: athlete
  entities: [{entity: activity-type, effect: reads, facts: [Name]}, {entity: import, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::imports'}
- text: The Product saves the corrections to the proposal
  kind: product
  actor: athlete
  entities: [{entity: import, effect: changes, facts: [Proposed session]}]
  contexts:
    web: {place: 'web::app::imports'}
---

# Correct an import

## Trigger

An import has the wrong activity type or a poor title.

## Outcome

The import shows the corrections and will be logged with them.
