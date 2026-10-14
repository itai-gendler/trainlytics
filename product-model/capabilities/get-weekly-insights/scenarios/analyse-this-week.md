---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Analyse this week
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::history'}
- text: The Product sends six weeks of sessions, recent skip notes, the athlete profile and recent health metrics to the language model of the Athlete's AI provider
  kind: product
  actor: athlete
  entities: [{entity: athlete, effect: reads, facts: [AI provider, AI key, Experience level, Birth year, Training goals, Injury notes, Coach notes, Tracked health metrics]}, {entity: cardio-session, effect: reads, facts: [Date, Title, Segments, Feeling, Effort]}, {entity: strength-session, effect: reads, facts: [Date, Title, Exercises, Feeling, Effort]}, {entity: planned-session, effect: reads, facts: [Planned date, Title, Skip note]}, {entity: health-metrics, effect: reads, facts: [Date, Resting heart rate, HRV, Body weight, Sleep, VO2 max, Active energy]}]
  contexts:
    web: {place: 'web::app::history'}
- text: The Product shows the analysis
  kind: product
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::history'}
---

# Analyse this week

## Trigger

The Athlete wants a coach's read on their training.

## Outcome

A short analysis of volume change, progression, records, wellbeing and effort patterns and imbalances appears.
