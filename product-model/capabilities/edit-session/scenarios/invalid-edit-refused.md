---
kind: validation
routes:
  web: Web app
steps:
- text: The Athlete saves a session with a value out of range
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::session'}
- text: The Product refuses and says which field is wrong
  kind: product
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::session'}
---

# An invalid edit is refused

## Trigger

The edit holds a value out of range, such as a set effort above 10.

## Outcome

Nothing is saved; the error names the field.
