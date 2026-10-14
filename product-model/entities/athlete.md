---
kind: person
acts: external
relations:
- {entity: cardio-session, verb: owns, cardinality: one-to-many}
- {entity: strength-session, verb: owns, cardinality: one-to-many}
- {entity: exercise, verb: owns, cardinality: one-to-many}
- {entity: exercise-type, verb: owns, cardinality: one-to-many}
- {entity: activity-type, verb: owns, cardinality: one-to-many}
- {entity: strength-template, verb: owns, cardinality: one-to-many}
- {entity: weekly-plan, verb: owns, cardinality: one-to-many}
- {entity: daily-steps, verb: owns, cardinality: one-to-many}
- {entity: workout-draft, verb: owns, cardinality: one-to-many}
- {entity: strava-connection, verb: owns, cardinality: one-to-one}
references:
- kind: code
  role: implementation
  target: backend/app/models/user_settings.py#UserSettings
- kind: code
  role: implementation
  target: backend/app/api/profile.py#patch_profile
- kind: code
  role: implementation
  target: backend/app/auth.py#authenticate_user
---

# Athlete

The signed-in person whose training Trainlytics keeps: everything they log, plan and import is theirs alone. The server's operator sets up each Athlete's account.

## Information kept

- **Username** — the name the Athlete signs in with, as the operator configured it
- **Display name** — the name shown on the profile
- **Birth year** — from which the AI coach is told the Athlete's age
- **Experience level** — Beginner, Intermediate or Advanced
- **Training goals** — goals, each with a description and a High, Medium or Low priority, listed by priority
- **Injury notes** — ongoing injuries or limitations the AI coach takes into account
- **Coach notes** — anything else the AI coach should know
- **AI provider** — Anthropic or OpenAI, the service AI coaching calls; Anthropic until chosen
- **AI key** — the Athlete's own API key for the AI provider, kept encrypted and never shown again once saved
- **Rest timer length** — how long workout mode's rest timer runs, 15 to 600 seconds in steps of 5; 90 seconds until set
- **Tracked health metrics** — which of resting heart rate, HRV, body weight, sleep, VO2 max and active energy are imported, shown and given to the AI coach; all of them until changed
