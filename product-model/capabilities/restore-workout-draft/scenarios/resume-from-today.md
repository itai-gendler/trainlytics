---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete chooses Resume on a Workout draft
  kind: actor
  actor: athlete
  entities: [{entity: workout-draft, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::today'}
- text: The Product opens the workout with the draft restored without asking
  kind: product
  actor: athlete
  entities: [{entity: workout-draft, effect: reads, facts: [Entered values, Started at]}]
  contexts:
    web: {place: 'web::app::workout-mode'}
---

# Resume from Today

## Trigger

The Athlete left a workout half-logged and comes back to Today.

## Outcome

Workout mode or the form opens with the draft, its rest timer still running.
