---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete picks the AI provider, pastes their API key and chooses Save
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::profile'}
- text: The Product stores the key encrypted and shows it as configured without showing it again
  kind: product
  actor: athlete
  entities: [{entity: athlete, effect: changes, facts: [AI provider, AI key]}]
  contexts:
    web: {place: 'web::app::profile'}
---

# Save a key

## Trigger

The Athlete wants AI coaching.

## Outcome

The key is configured; Analyse this week and Adapt this session work.

## Edge cases

- Saving another key replaces the previous one.
