---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete chooses Move to tomorrow on a Planned session for today
  kind: actor
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::today'}
- text: The Product moves the Planned session to tomorrow
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: changes, facts: [Planned date]}]
  contexts:
    web: {place: 'web::app::today'}
---

# Move today's session to tomorrow

## Trigger

The Athlete cannot do today's session today.

## Outcome

The session moves to tomorrow and leaves Today.

## Edge cases

- On Sundays Move to tomorrow is not offered, because tomorrow is in the next week.
