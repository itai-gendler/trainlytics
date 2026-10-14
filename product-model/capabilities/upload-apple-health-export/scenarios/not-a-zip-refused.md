---
kind: validation
routes:
  web: Web app
steps:
- text: The Athlete uploads a file that is not a .zip
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::connections'}
- text: The Product refuses it and says the file must be a .zip archive
  kind: product
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::connections'}
---

# A file that is not a zip is refused

## Trigger

The Athlete picks another kind of file.

## Outcome

Nothing is imported; the Product asks for a .zip archive.
