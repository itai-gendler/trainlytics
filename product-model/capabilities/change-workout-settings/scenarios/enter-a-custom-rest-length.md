---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete types a length in seconds or minutes and seconds and chooses Save
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::settings'}
- text: The Product saves the rest timer length
  kind: product
  actor: athlete
  entities: [{entity: athlete, effect: changes, facts: [Rest timer length]}]
  contexts:
    web: {place: 'web::app::settings'}
---

# Enter a custom rest length

## Trigger

None of the preset lengths fits.

## Outcome

The typed length is saved.
