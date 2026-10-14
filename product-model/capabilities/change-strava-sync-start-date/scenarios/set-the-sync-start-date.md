---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete picks a sync start date
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::connections'}
- text: The Product saves it
  kind: product
  actor: athlete
  entities: [{entity: strava-connection, effect: changes, facts: [Sync start date]}]
  contexts:
    web: {place: 'web::app::connections'}
---

# Set the sync start date

## Trigger

The Athlete wants older, or fewer, activities fetched.

## Outcome

The next sync starts from that day unless a later sync already happened.
