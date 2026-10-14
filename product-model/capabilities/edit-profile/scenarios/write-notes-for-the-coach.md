---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete writes injury or limitation notes and AI coach notes
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::profile'}
- text: The Product saves the notes
  kind: product
  actor: athlete
  entities: [{entity: athlete, effect: changes, facts: [Injury notes, Coach notes]}]
  contexts:
    web: {place: 'web::app::profile'}
---

# Write notes for the AI coach

## Trigger

The Athlete has an injury or other context to share.

## Outcome

The notes are saved and included in every AI request.
