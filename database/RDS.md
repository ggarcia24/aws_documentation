---
updated: '2021-01-06'
cards-deck: AWS::Database::RDS
---

# RDS

Relational Database Service

## Features

- Managed DB service for SQL Databases
- Backups
    - Can be disabled
    - retention time min 0, max 35 days default 7
    - Continuous
    - Daily full backup (during maintenance window)
    - Transaction logs are backed up every 5 minutes
- Support manually taking DB snapshots and retaining for as long as you want
- Point in Time Restore: Restore to specific timestamp
- Read replicas ^7b0455
    - Asynchronous replication
    - For
        - scaling reads horizontally
        - executing reports without affecting "master" db
    - Location
        - Within AZ: Avoid network costs
        - Cross AZ / Cross Region: Have to pay extra network costs for data transfers
    - Can be promoted to their own DB
- Multi-AZ (High Availability / Disaster Recovery)
    - Synchronous replication with standby instances
    - Automatic failover to standby instance
    - single DNS name
- Enhanced monitoring metrics: CPU usage of process and threads
- #Monitoring and #Logging through [[CloudWatch]]
- Maintenance windows for upgrades
- Scaling capability
- Engines Supported
    - Aurora
    - MySQL
    - MariaDB
    - PostgreSQL
    - Oracle
    - Microsoft SQL Server

### Aurora

- Proprietary DB engine
- Supports Postgres and MySQL
- Automatically grow storage from 10Gb to 64Tb (10Gb increments)
- HA native
    - store 6 copies of data across 3 AZ
    - Automated failover
    - Supports Auto Scaling
- Type
    - Regional DB
        - Read Replicas 15 max
    - Aurora Global Database
        - 1 primary region / 5 secondary read-only regions
        - 16 read replicas per secondary region
        - Cross Region Read Replicas
        - Promote another region as primary in < 1 min (RTO)
        - Asynchronous replication with up to 1 sec lag 
- Working mode
    - One Writer / Multiple readers
    - One Writer / Multiple readers - parallel query
    - Multiple writers
    - #Serverless

### MySQL

- Supports [[IAM]] authentication
- Read Replicas 5 max

### MariaDB

### PostgreSQL

- Supports [[IAM]] authentication

### Oracle

#### Microsoft SQL Server

## Security

- Uses [[VPC#Security Groups]] to control what IP can connect
- In-flight encryption with SSL / TLS
- At rest encryption with [[KMS]]

## Notes

- To encrypt an existent un-encrypted DB:
    1. Create a snapshot of the DB
    2. Copy the snapshot
    3. Enable encryption for the snapshot
    4. Create a new DB from encrypted snapshot
    5. Migrate application

## Questions / Flashcards

- How to migrate existing Oracle database to AWS with High Availability?:: Create an Oracle database in RDS with multi-AZ deployments
^1609850382159
