---
kind: validation
routes:
  web: Web app
steps:
- text: The Athlete chooses Add to Plan with Strength and no template
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::plan'}
- text: The Product refuses it and says the template is required
  kind: product
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::plan'}
---

# A strength session without a template is refused

## Trigger

The Athlete picks Strength but no template.

## Outcome

Nothing is added; the form says a template is required.

## Edge cases

- Cardio without an activity type or without a segment is refused the same way.
