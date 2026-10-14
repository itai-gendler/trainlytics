---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete opens History
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::history'}
- text: The Product lists Cardio sessions with distance, duration and average heart rate and Strength sessions with exercises, sets, volume and duration, newest first
  kind: product
  actor: athlete
  entities: [{entity: cardio-session, effect: reads, facts: [Date, Title, Segments, Total duration, Average heart rate, Calories]}, {entity: strength-session, effect: reads, facts: [Date, Title, Exercises, Duration, Calories]}, {entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::history'}
- text: The Product shows this week's cardio and strength minutes and calories, and minutes per week with Daily steps over recent weeks
  kind: product
  actor: athlete
  entities: [{entity: daily-steps, effect: reads, facts: [Date, Steps]}]
  contexts:
    web: {place: 'web::app::history'}
---

# Browse all sessions

## Trigger

The Athlete opens Stats › History.

## Outcome

Sessions are listed with their key numbers, under this week's minutes and calories and a chart of recent weeks.
