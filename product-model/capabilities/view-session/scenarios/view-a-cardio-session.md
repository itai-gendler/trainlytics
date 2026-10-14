---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete opens a Cardio session
  kind: actor
  actor: athlete
  entities: [{entity: cardio-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::session'}
- text: The Product shows its date, activity type, segments with pace, duration, heart rate and zones, feeling, effort, calories and notes
  kind: product
  actor: athlete
  entities: [{entity: cardio-session, effect: reads, facts: [Date, Title, Activity type, Segments, Total duration, Calories, Average heart rate, Time in heart rate zones, Feeling, Effort, Notes]}, {entity: activity-type, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::session'}
---

# View a cardio session

## Trigger

The Athlete opens a cardio session from History, Plan or Today.

## Outcome

Every segment, the heart rate zones and the session's feeling, effort and notes are shown.
