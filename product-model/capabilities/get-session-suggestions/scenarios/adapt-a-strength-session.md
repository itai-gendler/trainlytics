---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Adapt this session, describes how they feel and chooses Get suggestions
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product sends the session so far with each exercise's replacements, the last four weeks of training, the athlete profile and recent health metrics to the language model of the Athlete's AI provider
  kind: product
  actor: athlete
  entities: [{entity: athlete, effect: reads, facts: [AI provider, AI key, Experience level, Birth year, Training goals, Injury notes, Coach notes, Tracked health metrics]}, {entity: exercise, effect: reads, facts: [Name, Replacements]}, {entity: strength-session, effect: reads, facts: [Date, Exercises, Feeling, Effort]}, {entity: cardio-session, effect: reads, facts: [Date, Segments]}, {entity: health-metrics, effect: reads, facts: [Date, Resting heart rate, HRV, Body weight, Sleep, VO2 max, Active energy]}]
  contexts:
    web: {place: 'web::app::log-workout'}
- text: The Product shows the suggestions
  kind: product
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::log-workout'}
---

# Adapt a strength session

## Trigger

The Athlete is about to train a strength session but something hurts or feels off.

## Outcome

Concrete suggestions, such as swaps to listed replacements or volume cuts, appear; the session is unchanged.
