---
updated: '2021-01-05'
cards-deck: AWS::Application Integration::SNS

---

# SNS

## Features

- Supports up to 10 million subscriptions per topic
- Up to 100 thousand topics
- Supported Subscribers
    - [[SQS]]
    - HTTP(S)
    - [[Lambda]]
    - Emails
    - SMS Messages
    - Mobile Notifications
- AWS Supported Integrations
    - [[CloudWatch]]
    - [[EC2#Autoscaling Groups]]
    - [[S3]]
    - [[CloudFormation]]

## Security

- In-flight encryption using HTTPS API
- At rest encryption using [[KMS]] keys
- Client side encryption

## Notes

- Data is not persisted, which means that it will be lost if there are no consumers

## Questions / Flashcards

- What's the maximum amount of subscriptions that an SNS topic can have?:: You can have up to 10 million subscriptions per topic
^1609866348151
