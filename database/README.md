---
cards-deck: AWS::Database
---

# Databases

- How to select the right database:
    - Read/Write heavy or balanced workload?
    - Throughput needs?
    - Scalling or fluctuations through the day?
    - Data:
        - How much?
        - Will it Grow?
        - Average object size?
        - Durability?
    - Latency and Concurrency
    - Data model
    - Schema
    - Licencing costs

## Database Types

### [[RDS]]

- Operations
    - Small downtime when failover/maintenance happens
    - Scaling through read replicas
    - Restoring implies manual intervention
- Security
    - AWS is responsible for OS security
    - We are responsible for
        - Encryption with [[KMS]] or SSL/TLS
        - [[VPC#Security Groups]]
        - [[IAM]] policies
- Reliability
    - Multi-AZ feature
    - Failover in case of failures
- Performance
    - EC2 instance type
    - EBS volume type
    - Ability to use read replicas
- Cost
    - Pay per hour based on [[EC2]] and [[EC2#Elastic Block Store]]

### [[RDS#Aurora]]

- Operations
- Security
- Performance
- Reliability
- Cost

### [[ElasticCache]]

- Operations
- Security
- Performance
- Reliability
- Cost

### [[DynamoDB]]

- Operations
- Security
- Performance
- Reliability
- Cost

### [[S3]]

- Operations
- Security
- Performance
- Reliability
- Cost

### [[Athena]]

- Operations
- Security
- Performance
- Reliability
- Cost

### [[Amazon Redshift]]

- Operations
- Security
- Performance
- Reliability
- Cost

### [[Neptune]]

- Operations
- Security
- Performance
- Reliability
- Cost

### [[ElasticSearch]]

- Operations
- Security
- Performance
- Reliability
- Cost
