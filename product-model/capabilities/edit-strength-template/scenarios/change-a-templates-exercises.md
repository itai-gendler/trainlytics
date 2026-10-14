---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Edit on a Strength template, changes its exercises or sets and saves
  kind: actor
  actor: athlete
  entities: [{entity: strength-template, effect: reads, facts: []}, {entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::templates'}
- text: The Product saves the change as the template's next version
  kind: product
  actor: athlete
  entities: [{entity: strength-template, effect: changes, facts: [Exercises, Version, Version history]}]
  contexts:
    web: {place: 'web::app::templates'}
---

# Change a template's exercises

## Trigger

The Athlete's routine changed.

## Outcome

The template has the new exercises and sets as its next version; sessions planned earlier still compare against the version they were planned with.
