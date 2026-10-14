---
kind: primary
routes:
  web: Web app
steps:
- text: The Athlete chooses Sign out
  kind: actor
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app'}
- text: The Product ends the session and clears what the app cached on this device
  kind: product
  actor: athlete
  entities: []
  contexts:
    web: {place: 'web::app'}
---

# Sign out from the menu

## Trigger

The Athlete is done using Trainlytics on a device.

## Outcome

The session ends, the app forgets what it cached for the Athlete on this device, and the sign-in page opens.
