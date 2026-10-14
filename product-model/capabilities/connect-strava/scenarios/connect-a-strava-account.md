---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Connect Strava
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::connections'}
- text: The Product sends the Athlete to Strava to allow reading their activities
  kind: product
  actor: athlete
  entities: [{entity: installation, effect: reads, facts: [Strava app]}]
  contexts:
    web: {place: 'web::app::connections'}
- text: The Athlete allows access on Strava
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::connections'}
- text: The Product saves the Strava connection and returns the Athlete to Connections, saying Strava connected successfully
  kind: product
  actor: athlete
  entities: [{entity: strava-connection, effect: creates, facts: [Strava athlete name, Strava athlete photo]}]
  contexts:
    web: {place: 'web::app::connections'}
---

# Connect a Strava account

## Trigger

The Athlete records activities on Strava.

## Outcome

Strava shows as connected with the Strava account's name and photo, and Sync now is offered.
