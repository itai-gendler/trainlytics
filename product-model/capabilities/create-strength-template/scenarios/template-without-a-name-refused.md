---
kind: validation
routes:
  web: Web app
steps:
- text: The Athlete chooses Save Template with no name
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::templates'}
- text: The Product says the name is required
  kind: product
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::templates'}
---

# A template without a name is refused

## Trigger

The Athlete saves without a name.

## Outcome

Nothing is saved; the form says the name is required.
