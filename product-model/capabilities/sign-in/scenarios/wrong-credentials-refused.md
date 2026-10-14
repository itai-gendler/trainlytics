---
kind: validation
routes:
  web: Web app
steps:
- text: The Visitor enters a username and password
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web: {place: 'web::sign-in::sign-in'}
- text: They match none of the accounts the operator configured
  kind: condition
  actor: visitor
  entities: [{entity: installation, effect: reads, facts: [Accounts]}]
  contexts:
    web: {place: 'web::sign-in::sign-in'}
- text: The Product refuses the sign-in and says the credentials are invalid
  kind: product
  actor: visitor
  entities: []
  contexts:
    web: {place: 'web::sign-in::sign-in'}
---

# Wrong username or password refused

## Trigger

A Visitor enters a username or password that does not match.

## Outcome

The Visitor stays signed out on the sign-in page.
