---
kind: alternative
routes:
  web: Web app
steps:
- text: The Athlete chooses Start on a Planned session of type Strength for today
  kind: actor
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::today'}
- text: The Product opens workout mode with the planned template's exercises and sets
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: [Template]}, {entity: strength-template, effect: reads, facts: [Exercises]}, {entity: workout-draft, effect: creates, facts: [Workout type, Entered values, Started at]}, {entity: exercise, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::workout-mode'}
- text: The Athlete completes each set with its reps, weight and optional effort
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::workout-mode'}
- text: The Product starts the rest timer after each set but the last, for the Athlete's rest timer length
  kind: product
  actor: athlete
  entities: [{entity: athlete, effect: reads, facts: [Rest timer length]}]
  contexts:
    web: {place: 'web::app::workout-mode'}
- text: The Athlete chooses Finish workout and adds duration, feeling, effort, notes and calories
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app::workout-mode'}
- text: The Product saves the Strength session and clears the Workout draft
  kind: product
  actor: athlete
  entities: [{entity: strength-session, effect: creates, facts: [Date, Title, Template, Exercises, Duration, Calories, Feeling, Effort, Notes]}, {entity: workout-draft, effect: removes}]
  contexts:
    web: {place: 'web::app::workout-mode'}
- text: The Planned session of that day with the same template is now Done
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: changes, from: Planned, to: Done, facts: [Matched session]}]
  contexts:
    web: {place: 'web::app::workout-mode'}
---

# Log set by set in workout mode

## Trigger

On a phone, the Athlete starts a strength workout at the gym.

## Outcome

The session is saved with every completed set, and the plan shows the matching session as Done.

## Edge cases

- Workout mode opens on screens narrower than 768 px; wider screens open the full form, and either can switch to the other keeping the draft.
- The duration is filled from the start time unless typed, at least one minute.
- The screen is kept awake while workout mode is open, where the device allows it.
