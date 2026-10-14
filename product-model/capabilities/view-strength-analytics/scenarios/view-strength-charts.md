---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete opens Stats › Analytics
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::analytics'}
- text: The Product shows weekly volume by Exercise type, exercises per type per week, and each exercise's heaviest weight, best reps at it and best single-set volume
  kind: product
  actor: athlete
  entities: [{entity: strength-session, effect: reads, facts: [Date, Exercises]}, {entity: exercise, effect: reads, facts: [Name, Exercise types]}, {entity: exercise-type, effect: reads, facts: [Name]}]
  contexts:
    web: {place: 'web::app::analytics'}
---

# View strength charts

## Trigger

The Athlete opens the Strength section.

## Outcome

Weekly volume by exercise type, exercises per type per week and personal records grouped by type are shown.
