---
updated: '2021-01-06'
cards-deck: AWS::Database::RDS
---

# RDS

Amazon RDS Multi-AZ deployments provide enhanced availability and durability for Database (DB) Instances, making them a natural fit for production database workloads. When you provision a Multi-AZ DB Instance, Amazon RDS automatically creates a primary DB Instance and synchronously replicates the data to a standby instance in a different Availability Zone (AZ). Each AZ runs on its own physically distinct, independent infrastructure, and is engineered to be highly reliable.

![https://img-a.udemycdn.com/redactor/raw/2020-07-16_13-19-48-136ac1cc55a1697f6dbb6f5e184fb02c.png?4CZ5DPD0lrQP8WvNmO_uM41q22VreIVoLCQ5Y2PJD49TA5y9JWf0MjwNRMxvmsVIp7ClGGAFDkOxe5yrUyUO7dDrO-pY7j72H2fd2IMaucTyl_sjVY0nrM4b_izRXVCPlMd4tlCqwMwiswng7N8fBSYNJ2yzB5Qv_IlMoHEx1JuraCnC](https://img-a.udemycdn.com/redactor/raw/2020-07-16_13-19-48-136ac1cc55a1697f6dbb6f5e184fb02c.png?4CZ5DPD0lrQP8WvNmO_uM41q22VreIVoLCQ5Y2PJD49TA5y9JWf0MjwNRMxvmsVIp7ClGGAFDkOxe5yrUyUO7dDrO-pY7j72H2fd2IMaucTyl_sjVY0nrM4b_izRXVCPlMd4tlCqwMwiswng7N8fBSYNJ2yzB5Qv_IlMoHEx1JuraCnC)

In case of an infrastructure failure, Amazon RDS performs an automatic failover to the standby (or to a read replica in the case of Amazon Aurora), so that you can resume database operations as soon as the failover is complete. Since the endpoint for your DB Instance remains the same after a failover, your application can resume database operation without the need for manual administrative intervention.

In this scenario, the best RDS configuration to use is an Oracle database in RDS with Multi-AZ deployments to ensure high availability even if the primary database instance goes down

## Features

- Engines Supported
    - MySQL
        - Supports [[IAM]] authentication
    - PostgreSQL
        - Supports [[IAM]] authentication
    - Oracle
    - Aurora
    - 
- Supports Multi-AZ deployments to provide HA

## Security

# Aurora Global

https://aws.amazon.com/rds/aurora/global-database/

https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-global-database.html

What relational database and come up with a disaster recovery plan to mitigate multi-region failure. The solution requires a Recovery Point Objective (RPO) of 1 second and a Recovery Time Objective (RTO) of less than 1 minute?

**Amazon Aurora Global Database** is designed for globally distributed applications, allowing a single Amazon Aurora database to span multiple AWS regions. It replicates your data with no impact on database performance, enables fast local reads with low latency in each region, and provides disaster recovery from region-wide outages.

Aurora Global Database supports storage-based replication that has a latency of less than 1 second. If there is an unplanned outage, one of the secondary regions you assigned can be promoted to read and write capabilities in less than 1 minute. This feature is called Cross-Region Disaster Recovery. An RPO of 1 second and an RTO of less than 1 minute provides you a strong foundation for a global business continuity plan.

## Notes

## Questions / Flashcards

- How to migrate existing Oracle database to AWS with High Availability?:: Create an Oracle database in RDS with multi-AZ deployments
^1609850382159
