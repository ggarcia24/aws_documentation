---
updated: '2021-01-04'
cards-deck: AWS::Networking & Content Delivery::API Gateway
---

# API Gateway

## Features

- API versioning
- Environment management (DEV, TEST, PROD)
- Integration
    - [[Lambda]]
    - HTTP: expose internal HTTP endpoint / load balance
    - Mock
    - AWS Service
    - VPC Link
- Endpoint Types
    - Edge-Optimized
        - exists in singe region
        - requests Routed through [[CloudFront#Edge Locations]]
        - improves latency
    - Regional
        - Can manually configure [[CloudFront]] to have more control over caching and distribution
    - Private
        - Only acceded through [[VPC#Endpoints]]
        - Resource Policy to define access
- Protocols
    - HTTP
    - WebSocket
- Define through Swagger / OpenAPI
- Request Transformation
- Request validation
- Response validation
- Support caching responses
- Supports standard and burst throttling levels at global level and by service call
- Generate Client SDK
    - Support exponential backoff (429 HTTP response)

## Security

- [[IAM]] Permissions:
    - Signature v4
    - Users in your AWS Account
- [[Lambda]] Authorizer (Custom Authorizer)
    - Validate the request using a lambda function
    - Can cache the authentication result
    - Returns an IAM policy
- [[Cognito]]
    - Only for authentication
- Throttling through API Keys
- Authentication and Authorization
- Request throttling

## Questions / Flashcards

- In API Gateway, how can a protect backend systems from traffic spikes?:: You can enable throttling limits and result caching.
^1609854700821
