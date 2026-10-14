---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Sync now
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::connections'}
- text: The Product fetches the activities after the later of the sync start date and the last sync
  kind: product
  actor: athlete
  entities: [{entity: strava-connection, effect: reads, facts: [Sync start date, Last synced]}]
  contexts:
    web: {place: 'web::app::connections'}
- text: The Product stages each new activity as an Import, matching its type to the Athlete's activity types by name and its laps to segments
  kind: product
  actor: athlete
  entities: [{entity: activity-type, effect: reads, facts: [Name]}, {entity: import, effect: creates, to: Pending, facts: [Source, Proposed session, Suggested activity type]}]
  contexts:
    web: {place: 'web::app::connections'}
- text: The Product records when it synced and says activities are queued for review
  kind: product
  actor: athlete
  entities: [{entity: strava-connection, effect: changes, facts: [Last synced]}]
  contexts:
    web: {place: 'web::app::connections'}
---

# Sync now

## Trigger

The Athlete has new activities on Strava.

## Outcome

New activities wait in Imports for review and Last synced is updated.

## Edge cases

- An activity already accepted or discarded is not staged again; one still pending is refreshed.
- Weight training, CrossFit, yoga, pilates and stretching become strength sessions without exercises.
