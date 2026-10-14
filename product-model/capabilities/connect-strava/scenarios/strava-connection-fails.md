---
kind: edge
routes:
  web: Web app
steps:
- text: The Athlete chooses Connect Strava
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::connections'}
- text: Strava returns no authorization
  kind: condition
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::connections'}
- text: The Product returns the Athlete to Connections saying the Strava connection failed
  kind: product
  actor: athlete
  entities: [{entity: strava-connection, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::connections'}
---

# Connecting fails

## Trigger

The Athlete declines on Strava or Strava does not answer.

## Outcome

Nothing is connected; Connections says the connection failed.
