---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete chooses Adapt this session on the cardio form, describes the problem and chooses Get suggestions
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product sends the Planned session's segments, the last four weeks of cardio, the athlete profile and recent health metrics to the language model
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: [Title, Activity type, Planned segments]}, {entity: cardio-session, effect: reads, facts: [Date, Segments]}, {entity: athlete, effect: reads, facts: [AI provider, AI key, Experience level, Birth year, Training goals, Injury notes, Coach notes, Tracked health metrics]}, {entity: health-metrics, effect: reads, facts: [Date, Resting heart rate, HRV, Body weight, Sleep, VO2 max, Active energy]}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product shows the suggestions
  kind: product
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
---

# Adapt a planned cardio session

## Trigger

The Athlete logs the activity type of a cardio session planned for today and wants to adjust it.

## Outcome

Suggestions that refer to the planned distances, durations and paces appear; the plan is unchanged.
