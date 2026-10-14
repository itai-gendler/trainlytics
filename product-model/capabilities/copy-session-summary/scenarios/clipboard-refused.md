---
kind: edge
routes:
  web: Web app
steps:
- text: The Athlete chooses Copy
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::history'}
- text: The clipboard cannot be written
  kind: condition
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::history'}
- text: The Product shows Failed
  kind: product
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::history'}
---

# Copying fails

## Trigger

The browser refuses access to the clipboard.

## Outcome

The button says Failed and nothing is copied.
