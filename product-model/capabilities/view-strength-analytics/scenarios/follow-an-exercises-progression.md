---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete picks an Exercise in the progression chart
  kind: actor
  actor: athlete
  entities: [{entity: exercise, effect: reads, facts: [Name]}]
  contexts:
    web: {place: 'web::app::analytics'}
- text: The Product charts the heaviest weight and total volume of every day the Exercise was logged
  kind: product
  actor: athlete
  entities: [{entity: strength-session, effect: reads, facts: [Date, Exercises]}, {entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::analytics'}
---

# Follow an exercise's progression

## Trigger

The Athlete wants to see how one lift has gone.

## Outcome

The exercise's heaviest set and volume per session day are charted.
