---
updated: '2021-01-04'
cards-deck: AWS::Database::DynamoDB
---

# DynamoDB

## Features

- #Managed NoSQL
- Highly Available with replication across 3 AZ
- Scales automatically
- Distributed DB 
- Event driven development with DynamoDB stream (execute [[Lambda]] Functions)
- Working Modes
    - Provisioned Throughput
        - Read Capacity Units (RCU): 1 strongly consistent read or 2 eventually consistent read of 4Kb/s
        - Write Capacity Units (WCU): 1 write of 1Kb/s
        - Burst capacity using credits
        - Auto scaling
    - On-demand
        - Scales automatically WCU/RCU
        - 2.5 more expensive
- Transactions
    - Coordinated Insert, Update, Delete across multiple tables
- Data Types
    - String
    - Number
    - Binary
    - Boolean
    - Null
    - List
    - Map
    - String Set
    - Number Set
    - Binary Set
- DynamoDB Accelerator
    - Micro second latency for cached reads & queries
    - 5 minutes TTL by default
- Amazon DMS to migrate from
    - Mongo
    - Oracle
    - MySQL
    - S3
    - etc
- Global Tables: Active to Active replications

## Security

- Supports [[VPC#Endpoints]]
- Access controlled through [[IAM]]
- Encryption at rest using [[KMS]]
- Encryption in transit using SSL/TLS
- Point in time restore

## Notes

## Questions / Flashcards

- In DynamoDB, how can I distribute the workload evenly and using the provisioned throughput efficiently?:: Design partition keys with high-cardinality attributes, which have a large number of distinct values for each item to prevent "hot" partitions.
^1609852991305
- What's the maximum size of an item in DynamoDB?:: 400Kb
- What are DynamoDB streams?:: An ordered flow of information about changes made to a DynamoDB table.
^1609853682975

