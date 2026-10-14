---
kind: primary
routes:
  web: Web app
steps:
- text: The Visitor enters their username and password
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web: {place: 'web::sign-in::sign-in'}
- text: The Product checks them against the accounts the operator configured and signs the Visitor in
  kind: product
  actor: visitor
  entities: [{entity: installation, effect: reads, facts: [Accounts]}]
  contexts:
    web: {place: 'web::sign-in::sign-in'}
---

# Sign in with username and password

## Trigger

A Visitor opens Trainlytics and is not signed in.

## Outcome

The Visitor is signed in as their Athlete account and lands on Today.
