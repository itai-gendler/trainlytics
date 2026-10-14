---
appliesTo:
- type: entity
  id: athlete
  facts: [Rest timer length]
- type: capability
  id: change-workout-settings
references:
- kind: code
  role: implementation
  target: backend/app/schemas/user_settings.py#UserSettingsPatch
- kind: code
  role: implementation
  target: frontend/src/lib/workoutMode.ts#isValidRestLength
---

# A rest timer runs 15 to 600 seconds in steps of 5

The rest timer length is 15 to 600 seconds in steps of 5; until the Athlete picks one it is 90 seconds.
