---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete opens Stats › Analytics
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::analytics'}
- text: The Product shows weekly minutes per heart rate zone, time and distance by Activity type, walking segments over time and rolling four- and eight-week load
  kind: product
  actor: athlete
  entities: [{entity: cardio-session, effect: reads, facts: [Date, Activity type, Segments, Total duration, Time in heart rate zones]}, {entity: activity-type, effect: reads, facts: [Name]}, {entity: strength-session, effect: reads, facts: [Date, Duration]}]
  contexts:
    web: {place: 'web::app::analytics'}
---

# View cardio charts

## Trigger

The Athlete opens the Cardio section.

## Outcome

Zone minutes per week, time by activity type, distance per activity type and the four- and eight-week training load are shown.
