---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete adds a goal, writes it and picks its priority, or removes one
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::profile'}
- text: The Product saves the goals in priority order
  kind: product
  actor: athlete
  entities: [{entity: athlete, effect: changes, facts: [Training goals]}]
  contexts:
    web: {place: 'web::app::profile'}
---

# Set training goals

## Trigger

The Athlete wants the AI coach to know what they train for.

## Outcome

The goals are saved and listed high priority first.
