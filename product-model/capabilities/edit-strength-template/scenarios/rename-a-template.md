---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete changes only the name of a Strength template and saves
  kind: actor
  actor: athlete
  entities: [{entity: strength-template, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::templates'}
- text: The Product saves the name
  kind: product
  actor: athlete
  entities: [{entity: strength-template, effect: changes, facts: [Name]}]
  contexts:
    web: {place: 'web::app::templates'}
---

# Rename a template

## Trigger

The Athlete wants a clearer name.

## Outcome

The template has the new name; its version is unchanged.
