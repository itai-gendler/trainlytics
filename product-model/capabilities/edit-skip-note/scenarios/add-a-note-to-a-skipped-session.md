---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Add note on a Skipped planned session and writes the reason
  kind: actor
  actor: athlete
  entities: [{entity: planned-session, effect: reads, facts: []}]
  contexts:
    web: {place: 'web::app::plan'}
- text: The Product saves the skip note
  kind: product
  actor: athlete
  entities: [{entity: planned-session, effect: changes, facts: [Skip note]}]
  contexts:
    web: {place: 'web::app::plan'}
---

# Add a note to a skipped session

## Trigger

A planned session was missed and the Athlete wants to record why.

## Outcome

The skipped session shows the reason; the AI coach sees recent reasons.

## Edge cases

- A session that already has a note offers Edit note and replaces it.
