---
cards-deck: AWS::Application Integration::SQS
updated: '2021-01-05'

---

# SQS

Simple Queuing Service

## Features

- Integrates with [[EC2#Autoscaling Groups]] to scale up/down based on [[CloudWatch]] Custom Metric/Alarm
- Allows horizontal scaling for consumers
- Automatically re-adds a message to the queue if it wasn't deleted in 30sec (default)
- Supports moving failed messages to a Dead Letter Queue after X amount of retries
- Default retention 4 days, maximum 14 days
- Message Size up to 256kb
- 2 modes
    - Standard
        - Unlimited amount of messages and throughput
        - Default retention 4 days, maximum 14 days
        - At least once delivery
        - Low latency
        - Unordered (best effort)
    - FIFO
        - Content Based deduplication
        - Limited throughput 300msg/s without batching, 3000msg with
        - Exactly-once delivery
        - Strict ordering

## Security

- In-flight encryption using HTTPS API
- At rest encryption using [[KMS]] keys
- Client side encryption

## Notes

## Questions / Flashcards

- What types of encryption is supported by SQS?:: In flight trough HTTPS, at rest using [[KMS]], and Client-side
^1609865710882
- What is the maximum size of a message in SQS?:: The maximum message size is 256Kb
^1609863601605
- What are the characteristics of SQS Standard Queues? #card
    - Default retention 4 days, maximum 14 days
    - Unlimited amount of messages and throughput
    - At least once delivery
    - Unordered (best effort)
^1609863511776
- What are the characteristics of SQS FIFO Queues? #card
    - Default retention 4 days, maximum 14 days
    - Limited throughput 300msg/s without batching, 3000msg with
    - Content Based deduplication
    - Exactly-once delivery
    - Strict ordering
^1609865710888
