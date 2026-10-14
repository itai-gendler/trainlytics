---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Accept all
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::imports'}
- text: The Product logs a Cardio session for each pending cardio Import without a likely duplicate and marks it accepted
  kind: product
  actor: athlete
  entities: [{entity: cardio-session, as: existing, effect: reads, facts: [Date, Total duration]}, {entity: cardio-session, as: imported, effect: creates, facts: [Date, Title, Activity type, Segments, Total duration, Calories, Average heart rate, Notes]}, {entity: import, effect: changes, from: Pending, to: Accepted, facts: []}]
  contexts:
    web: {place: 'web::app::imports'}
- text: The Product reports how many were accepted and leaves likely duplicates pending
  kind: product
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::imports'}
---

# Accept the whole queue

## Trigger

The Athlete trusts what was imported.

## Outcome

Every import without a likely duplicate becomes a session; the Product says how many were accepted and which are left as likely duplicates.
