---
updated: '2021-01-05'
cards-deck: AWS::Analytics::Kinesis

---

# Kinesis

## Features

- Managed alternative to Apache Kafka
- Usefull for real-time systems
- Data is replicated to 3 AZs
- Data retention is 1 day by default (max 7days)
- 3 Types
    - Kinesis Streams: low latency streams
    - Kinesis Analytics: perform analytics on streams using SQL
    - Kinesis Firehose: put stream data into [[S3]], [[Amazon Redshift]], [[ElasticSearch]], [[Splunk]] 
- Scales using SHARDs
    - 1 SHARD = 1 MiB/1000 msgs write and 2Mib read
- Ability to reprocess/replay data
- Multiple consumers of the same stream
- Real-time process with scale of throughput
- Data inserted is immutable
- Kinesis Client Library
    - Enable consuming messages from Kinesis efficiently
    - Supports
        - Java
        - Node
        - Python
        - Ruby
        - .Net

## Security

- Control access/authorization using [[IAM]] policies
- Encryption in flight using HTTPS
- Encryption at rest using [[KMS]]
- Possibility to encrypt / decrypt data client side
- [[VPC#Endpoints]] to access within a [[VPC]]

## Notes

- Choose a partition key with high cardinality to avoid a hot partition

## Questions / Flashcards

- What's the maximum retention period on a Kinesis Stream?:: Data can be retained for a maximum of 7 days
^1610117701501
