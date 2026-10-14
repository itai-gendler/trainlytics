---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Remove under AI Provider
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::profile'}
- text: The Product deletes the stored key
  kind: product
  actor: athlete
  entities: [{entity: athlete, effect: changes, facts: [AI key]}]
  contexts:
    web: {place: 'web::app::profile'}
---

# Remove the key

## Trigger

The Athlete no longer wants AI requests made with their key.

## Outcome

No key is configured; AI features ask for one.
