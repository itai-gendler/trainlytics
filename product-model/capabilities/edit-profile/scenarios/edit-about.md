---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete changes the display name, birth year or experience level
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::profile'}
- text: The Product saves them
  kind: product
  actor: athlete
  entities: [{entity: athlete, effect: changes, facts: [Display name, Birth year, Experience level]}]
  contexts:
    web: {place: 'web::app::profile'}
---

# Edit about

## Trigger

The Athlete fills in their profile.

## Outcome

Display name, birth year and experience level are saved.
