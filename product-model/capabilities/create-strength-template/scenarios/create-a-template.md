---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses New Template, names it and adds each Exercise with its sets
  kind: actor
  actor: athlete
  entities: [{entity: exercise, effect: reads, facts: [Name]}]
  contexts:
    web: {place: 'web::app::templates'}
- text: The Athlete chooses Save Template
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::templates'}
- text: The Product saves the Strength template as its first version
  kind: product
  actor: athlete
  entities: [{entity: strength-template, effect: creates, facts: [Name, Exercises, Version, Version history]}]
  contexts:
    web: {place: 'web::app::templates'}
---

# Create a template

## Trigger

The Athlete wants to stop rebuilding the same workout by hand.

## Outcome

The template is in the library as version 1 and can be used, planned and edited.
