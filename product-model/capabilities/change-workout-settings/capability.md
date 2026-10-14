---
domain: settings
availability:
- {place: 'web::app'}
references:
- kind: code
  role: implementation
  target: frontend/src/pages/SettingsPage.tsx
- kind: code
  role: implementation
  target: frontend/src/lib/restLengthSync.ts
- kind: code
  role: implementation
  target: frontend/src/lib/hooks/useRestLength.ts
- kind: code
  role: implementation
  target: backend/app/schemas/user_settings.py#UserSettingsPatch
---

# Change workout settings

The Athlete sets how long workout mode's rest timer runs, in Settings › Workout or from workout mode's options. The length follows the Athlete to every device.
