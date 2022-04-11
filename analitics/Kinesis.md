---
updated: '2022-04-05'
cards-deck: AWS::Analytics::Kinesis

---

# Kinesis

## Features

- Useful for real-time systems

### Kinesis Data Streams
- Retention period is 1 day by default (max 365 days)
- Ability to reprocess/replay data
- Data inserted is immutable
- Multiple consumers of the same stream
- Real-time (~200ms latency)
- Manual scaling (shard splitting / merging)
- Made of shards
- Producers
    - 1 MB/sec or 1000 msg/sec per shard
    - AWS SDK
    - Kinesis Producer Library
    - Kinesis Agent
- Consumers
    - Types
        - Shared: 2MB/sec between all of the consumers
        - Enhanced: 2MB/sec per shard per consumer
    - Kinesis Client Library
        - Java
        - Node
        - Python
        - Ruby
        - .Net
    - AWS SDK
    - Lambda
    - [[#Kinesis Data Firehose]]
    - [[#Kinesis Data Analytics]]

### Kinesis Data Firehose
- Store data 
- Fully managed service
- Batch writes 
- Near realtime:
    - 60 sec (minimum latency)
    - 32Mb 
- Producers
    - 1 MB/sec
    - AWS SDK
    - Kinesis Producer Library
    - Kinesis Agent
    - [[#Kinesis Data Streams]]
    - [[CloudWatch]]
    - [[AWS IoT]]
 - Supports Data transformation
- Consumers
    - AWS:
        - [[S3]]
        - [[Amazon Redshift]] (COPY through S3)
        - [[ElasticSearch]]
    - 3rd Party
        - Datadog
        - Splunk
        - New relic
        - mongoDB
    - Custom Destination
        - HTTP Endpoint
 - Failed or All data can be put in S3

### Kinesis Data Analytics
- perform analytics on streams using SQL
- Fully managed, automatic scaling
- Real-time analytics
- Sources
    - [[#Kinesis Data Streams]]
    - [[#Kinesis Data Firehose]]
- Sinks
    - [[#Kinesis Data Streams]]
    - [[#Kinesis Data Firehose]]
 - Use cases
     - Time series analytics
     - Real-time dashboards
     - Real-time metrics

### Kinesis Video Streams
- capture, process and store video streams

## Security

- Control access/authorization using [[IAM]] policies
- Encryption in flight using HTTPS
- Encryption at rest using [[KMS]]
- Possibility to encrypt / decrypt data client side
- [[VPC#Endpoints]] to access within a [[VPC]]

## Notes

- Choose a partition key with high cardinality to avoid a hot partition

## Questions / Flashcards

- What's the maximum retention period on a Kinesis Data Stream?:: Data can be retained for a maximum of 365 days
^1610117701501
- How can I improve the throughput in cases of multiple consumers or Kinesis Data Streams?:: Enable enhanced fanout feature     
