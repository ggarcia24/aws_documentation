---
updated: '2021-01-16'
cards-deck: AWS::Security, Identity, & Compliance::Cognito

---

# Cognito

Identity managment

## Features

### Cognito User Pools

- Database of users
- Username / Password combination
- Automates
    - Verifiy emails
    - Phone numbers
    - MFA
- User sources
    - Facebook
    - Google
    - SAML
- Returns JWT
- Integrates with [[API Gateway]] for authentication

### Cognito Identity Pools

- Supports many Identity Providers
    - Google
    - Facebook
    - SAML
    - OpenID
    - [[Cognito#Cognito User Pools]]
- Provide access to AWS resources using [[STS]]
    - i.e Facebook user access to S3 bucket
- Get temporary AWS credentials
- predefined IAM policy stating permissions

### Cognito Sync

- Deprecated in favor of [[AppSync]]
- Cross device synchronization
- Offline capability (sync when online)
- Requires [[Cognito#Cognito Identity Pools]]

## Security

## Notes

## Questions / Flashcards
