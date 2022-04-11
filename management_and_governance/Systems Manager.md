---
updated: '2021-01-22'
cards-deck: AWS::Management & Governance::System Manager
---

# AWS System Manager

## Features

### Operations Management

### Application Management

#### Parameter store

- Tiers
    - Standard
        - Maximum amount of parameters: 10000
        - Maximum parameter size: 4Kb
        - Parameter policies: No
    - Advanced
        - Maximum amount of parameters: 100000
        - Maximum parameter size: 8Kb
        - Parameter policies: Yes
- Secure storage for configuration and secrets
- Optional [[KMS]] encryption
- Version tracking
- Notifications with [[CloudWatch#Events]]
- Integration with [[CloudFormation]]

### Change Management

### Node Management

### Shared Resources


## Security

## Notes

## Questions / Flashcards

- In SSM Parameter Store, what's the maximum amount of parameters under a standard tier parameter store?:: 10000
^1611480706327
- In SSM Parameter Store, what's the maximum size of a parameter under a standard tier parameter store?:: 4Kb
^1611480706334
- In SSM Parameter Store, are Parameter policies supported under a standard tier parameter store?:: No
^1611480706341
- In SSM Parameter Store, what's the maximum amount of parameters under an advanced tier parameter store?:: 100000
^1611480706347
- In SSM Parameter Store, what's the maximum size of a parameter under an advanced tier parameter store?:: 8Kb
^1611480706353
- In SSM Parameter Store, are Parameter policies supported under an advanced tier parameter store?:: Yes
^1611480706359
