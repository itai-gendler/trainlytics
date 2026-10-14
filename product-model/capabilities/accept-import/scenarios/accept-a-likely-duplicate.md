---
kind: edge
routes:
  web: Web app
steps:
- text: The Athlete chooses Accept on an Import
  kind: actor
  actor: athlete
  entities: [{entity: import, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::imports'}
- text: A session logged within a day of it has a duration within a minute of it
  kind: condition
  actor: athlete
  entities: [{entity: cardio-session, effect: reads, facts: [Date, Total duration]}]
  contexts:
    web: {place: 'web::app::imports'}
- text: The Product shows the existing session's date and duration and holds the Import
  kind: product
  actor: athlete
  entities: [{entity: import, effect: reads, facts: [Proposed session]}]
  contexts:
    web: {place: 'web::app::imports'}
- text: The Athlete chooses to accept it anyway
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::imports'}
- text: The Product logs the Cardio session and marks the Import accepted
  kind: product
  actor: athlete
  entities: [{entity: cardio-session, effect: creates, facts: [Date, Title, Activity type, Segments, Total duration, Calories, Average heart rate, Notes]}, {entity: import, effect: changes, from: Pending, to: Accepted, facts: []}]
  contexts:
    web: {place: 'web::app::imports'}
---

# Accept a likely duplicate

## Trigger

The Athlete already logged the same workout by hand.

## Outcome

The Product points out the existing session; the Athlete decides whether to import it anyway.

## Edge cases

- Dismissing the warning leaves the Import pending.
