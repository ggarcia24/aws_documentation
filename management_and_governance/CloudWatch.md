---
updated: '2021-01-06'
cards-deck: AWS::Management & Governance::CloudWatch

---

# CloudWatch

## Features

### Logging
- Types
    - LogGroups
    - Streams
- Sources
    - [[ElasticBeanStalk]]
    - [[ECS]]
    - [[Lambda]]
    - [[VPC]]
    - [[API Gateway]]
    - [[CloudTrail]]
    - CloudWatch log agents
    - [[Route 53]]
- Requires correct [[IAM]] policies
- Export
    - [[S3]] for archival
    - [[ElasticSearch]]
    - [[Lambda]] function
- Set retention policies to discard (as you pay for data retention)
- Filter expressions to search
- Log Insights to query and add to Dashboard

### Metrics

- for every service in AWS
- belong to namespaces
- Can create #Global Dashboards
- Dashboards of metrics
    - Can include graphics from different regions
    - Change TimeZone and Time range
    - Automatic refresh ()
- Support for custom metrics

### Alarms

- Trigger notification for any metric
- Action
    - [[]]

### Events

## Security

- Encryption using [[KMS]] at Group Level

## Notes

- CloudWatch unified agent is the new version
    - Collects addition metrics
        - CPU (active guest, idle, system, user, steal)
        - Disk metrics (free, used, total)
        - Disk IO (writes, reads, bytes, iops)
        - RAM (free, inactive, used, total, cached)
        - Netstat (number of TCP/UDP connections, net packets, bytes)
        - Processes ((total, dead, blocked, idle running, sleep))
        - swap space
    - Collects logs 
    - Configuration ussing [[SSM Parameter Store]]


## Questions / Flashcards

- Can I monitor memory and disk utilization using CloudWatch?:: You need to install CloudWatch Agent on the [[EC2]] instance to gather that information from the instances.
^1609943112805
- What CloudWatch monitors by default in [[EC2]] instances?:: CloudWatch monitors by default CPU utilization, Network utilization, Disk performance, and Disk Reads/Writes
^1609943112816
-
