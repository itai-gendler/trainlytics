---
kind: validation
routes:
  web: Web app
steps:
- text: The Athlete types a length outside 15 to 600 seconds in steps of 5 and chooses Save
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::settings'}
- text: The Product refuses it and shows the allowed range
  kind: product
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::settings'}
---

# A length out of range is refused

## Trigger

The Athlete types a length below 15 or above 600 seconds, or not in steps of 5.

## Outcome

Nothing is saved; the allowed range is shown.
