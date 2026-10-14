---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Disconnect and confirms
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::connections'}
- text: The Product deletes the Strava connection
  kind: product
  actor: athlete
  entities: [{entity: strava-connection, effect: removes}]
  contexts:
    web: {place: 'web::app::connections'}
---

# Disconnect the Strava account

## Trigger

The Athlete stops using Strava with Trainlytics.

## Outcome

Strava shows as not connected; imports already in the queue stay.
