---
updated: '2021-01-04'
cards-deck: AWS::Database::DynamoDB
---

# DynamoDB

## Features

- Supports triggering execution of [[Lambda]] Functions with a DynamoDB stream

## Security

## Notes

## Questions / Flashcards

- In DynamoDB, how can I distribute the workload evenly and using the provisioned throughput efficiently?:: Design partition keys with high-cardinality attributes, which have a large number of distinct values for each item to prevent "hot" partitions.
^1609852991305
- What are DynamoDB streams?:: An ordered flow of information about changes made to a DynamoDB table.
^1609853682975
