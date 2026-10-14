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
- text: The Product shows all-time sessions, minutes and distance, which days of the past year had cardio or strength, and weekly time and calories of each
  kind: product
  actor: athlete
  entities: [{entity: cardio-session, effect: reads, facts: [Date, Segments, Total duration, Calories, Feeling, Effort]}, {entity: strength-session, effect: reads, facts: [Date, Duration, Calories, Feeling, Effort]}, {entity: planned-session, effect: reads, facts: [Planned date]}]
  contexts:
    web: {place: 'web::app::analytics'}
---

# View the overview

## Trigger

The Athlete opens Analytics.

## Outcome

All-time sessions, minutes and distance, a day-by-day heatmap of the last year and weekly minutes and calories by type are shown; on a phone a glance of this week, the latest record and the last week's feeling and effort comes first.
