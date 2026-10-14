---
kind: primary
result: achieved
routes:
  web: Web app
steps:
- text: The Athlete chooses Connect Strava and allows access on Strava
  kind: actor
  actor: athlete
  capability: connect-strava
  entities: []
  contexts:
    web: {place: 'web::app::connections'}
- text: The Product saves the Strava connection and returns the Athlete to Connections
  kind: product
  actor: athlete
  capability: connect-strava
  entities: [{entity: strava-connection, effect: creates, facts: [Strava athlete name, Strava athlete photo]}]
  contexts:
    web: {place: 'web::app::connections'}
- text: The Athlete chooses Sync now
  kind: actor
  actor: athlete
  capability: sync-strava-activities
  entities: []
  contexts:
    web: {place: 'web::app::connections'}
- text: The Product stages the fetched activities as Imports and records the sync
  kind: product
  actor: athlete
  capability: sync-strava-activities
  entities: [{entity: import, effect: creates, to: Pending, facts: [Source, Proposed session, Suggested activity type]}, {entity: strava-connection, effect: changes, facts: [Last synced]}]
  contexts:
    web: {place: 'web::app::connections'}
---

# Connect Strava, then sync

## Trigger

The Athlete records runs on Strava and wants them in Trainlytics.

## Outcome

The Strava account is connected and its activities are queued for review.
