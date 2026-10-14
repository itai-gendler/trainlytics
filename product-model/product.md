---
id: trainlytics
summary: 'A personal training log for hybrid athletes: cardio and strength sessions, reusable strength templates, weekly plans checked against what was done, progress analytics, Strava and Apple Health imports, and AI coaching on the athlete''s own API key.'
category: health-and-fitness
tags:
- fitness
- training-log
- strength-training
- running
- self-hosted
authors:
- name: miptgirl
  url: https://github.com/miptgirl
license: Apache-2.0
languages:
- en
limitations:
- People sign in with an account the server's operator set up; there is no registration, password change or password reset in the app.
- 'AI coaching runs on each athlete''s own Anthropic or OpenAI API key, and it only writes suggestions and analysis: it never changes a plan, a template or a session.'
- Strava activities and Apple Health workouts come in only when the athlete asks (Sync now, uploading an export) and wait in the import queue until the athlete accepts them.
- A weekly plan runs Monday to Sunday, and a planned session counts as done only when a matching session is logged on its planned day.
- Cardio is kept in kilometres and minutes per kilometre and strength weights in kilograms.
references:
- kind: doc
  role: intent
  target: README.md
  title: README
- kind: doc
  role: intent
  target: specs/mission.md
  title: Mission
- kind: doc
  role: context
  target: specs/roadmap.md
  title: Roadmap
- kind: doc
  role: context
  target: CHANGELOG.md
  title: Changelog
---

# Trainlytics

Trainlytics is a personal fitness tracker for people who train across disciplines. An athlete logs
cardio sessions as segments with duration, distance, pace and heart rate zones, and strength
sessions as exercises with sets of reps, weight and effort, either in a full form or set by set in
workout mode with a rest timer. Reusable strength templates prefill a session and can be updated
from it; a weekly plan lays out strength and cardio sessions day by day, and each planned session
turns Done when a matching session is logged that day or Skipped when its day passes. Stats show
the workout history and analytics on volume, progression, personal records, cardio, readiness,
plan adherence and health metrics. Strava activities and Apple Health exports arrive through an
import queue, and an AI coach, running on the athlete's own API key, analyses the week and
suggests how to adapt a session.

## Intent

"A personal fitness operating system": "one customizable place to plan, log, analyze, and review
all fitness progress" for hybrid athletes, so they no longer stitch together a running app and a
gym app. It is "not just a workout log, but a centralized tool for planning, tracking, analyzing,
and continuously improving training", where training is "intentional, not just reactive" and the
athlete owns their data, sharing structured summaries with coaches or AI tools.
