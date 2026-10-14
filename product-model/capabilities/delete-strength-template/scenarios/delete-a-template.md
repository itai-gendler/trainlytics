---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Delete on a Strength template and confirms
  kind: actor
  actor: athlete
  entities: [{entity: strength-template, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::templates'}
- text: The Product deletes the Strength template
  kind: product
  actor: athlete
  entities: [{entity: strength-template, effect: removes}]
  contexts:
    web: {place: 'web::app::templates'}
- text: Planned sessions and Strength sessions that named it no longer name a template
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: changes, facts: [Template]}, {entity: strength-session, effect: changes, facts: [Template]}]
  contexts:
    web: {place: 'web::app::templates'}
---

# Delete a template

## Trigger

The Athlete no longer uses a template.

## Outcome

The template and its versions are gone; sessions and plans that used it stay without it.
