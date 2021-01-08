---
updated: '2021-01-04'
cards-deck: AWS::Compute::EC2
---

# EC2

Elastic Cloud Compute

## Features

- Launch Virtual Machines
- Store data on virtual drives
- Load Balancers
- Autoscaling groups
- Can customize instances by using EC2 User Data the first time first boots

### EC2 Instances

- You can reduce pricing for very long running (minimum 1year) instances using Reserved Instances (but you will not be able to change instance type)
- Scheduled reserved instances allows you to reduce costs based on a schedule

### EC2 Launch Templates

### Reserved Instances

- Can be Standard or Convertible (depending if you are allowed to change instance type) 

### Scheduled Instances

- Purchase EC2 "time" when you required a fraction of day/week/month

### Spot Instances

- The most cost efficient instance type
- Require fault tolerant workloads(batch jobs, data analysis, image processing), as you can "loose" them depending on price 

### AMIs

- https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/CopyingAMIs.html

### Elastic Block Store

- RAID Configuration https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/raid-config.html

#### Volumes

- Network attached hard drives
- EBS volume types
    - GP2
        - Price-Performance balance variety of workloads
        - Good for small random operations
        - Burstable to 3000 when size < 1000Gb
        - 3 IOPS per GB, min 100 IOPS, max 16000 IOPS
        - Min size is 1GiB, Max size is 16TiB
    - IO1
        - High throughput workloads or low latency (Databases)
        - Good for small random operations
        - 50 IOPS per GiB, provisioned IOPS, min 100, max 32000 (64000 when using nitro instances)
        - Min size is 4GiB, Max size is 16TiB
    - ST1
        - Throughput intensive workloads (Big data, Video Processing)
        - Good for large sequential operations
        - Max IOPS 500
        - Throughput is 40Mb/s per TiB, max throughput 500Mib/s - can burst
        - Min size is 500Gib, Max size is 16Tib
    - SC1
        - Large volumes of less frequent accessed throughput oriented data workloads
        - Good for large sequential operations
        - Max IOPS 250
        - Throughput is 12Mib/s per TiB, max throughput 250Mib/s - can burst
        - Min size is 500Gib, Max size is 16Tib

#### Snapshots

- They are incremental, they only backup changed blocks
- They use IO which means that it's recommended to detach the volume but it's not required
- Max 100000 snapshots

#### Lifecycle Policy

- Useful for automated backup solutions
- You can use it to create automated snapshots of volumes by Tags/Name

### Security Groups

- Please refer to [[VPC#Security Groups]] page

### Elastic IPs

- Please refer to [[VPC#Elastic IPs]] page

### Load Balancers

#### Application Load Balancers

#### Network Load Balancers

### Autoscaling Groups

- You can configure scaling by policies:
    - Target Tracking
        - Maintain metric at certain value i.e CPU Usage always 50%
    - Simple / Step Scaling
        - [[CloudWatch]] alarm performs action i.e add/remove instances
    - Schedule
        - You know in advance when the peaks are i.e Monday 9AM
- You can use Scaling Cooldowns to control how fast the scaling activity affects your counters, the default is 300 sec

## Security

## Notes

## Questions / Flashcards

- How many EBS volume types are?:: There are 4 volume types GP2 (General Purpose), IO1 (Throughput) , ST1 (Mechanical throughput), SC1 (Cheap mechanical less frequent)
^1609849505382
- Can I change my instance type if I purchased reserved instances?:: It depends if when purchasing you selected the Convertible option
^1609849505386
- Cal I change an EBS volume to a different Availability Zone?:: No, EBS volumes are tied to an specific AZ, you can however copy a snapshot of the EBS to another AZ and then delete the old one.
^1609849505389
- What are the constrains of a GP2 volume? #card
    - Price-Performance balance variety of workloads
    - Burstable to 3000 when size < 1000Gb
    - 3 IOPS per GB, min 100 IOPS, max 16000 IOPS
    - Min size is 1GiB, Max size is 16TiB
^1609849505393
- What are the constrains of a IO1 volume? #card
    - High throughput workloads or low latency (Databases)
    - 50 IOPS per GiB, provisioned IOPS, min 100, max 32000 (64000 when using nitro instances)
    - Min size is 4GiB, Max size is 16TiB
^1609849538538
- What are the constrains of a ST1 volume? #card
    - Throughput intensive workloads (Big data, Video Processing)
    - Max IOPS 500
    - Throughput is 40Mb/s per TiB, max throughput 500Mib/s - can burst
    - Min size is 500Gib, Max size is 16Tib
^1609849546486
- What are the constrains of a SC1 volume? #card
    - Large volumes of less frequent accessed throughput oriented data workloads
    - Max IOPS 250
    - Throughput is 12Mib/s per TiB, max throughput 250Mib/s - can burst
    - Min size is 500Gib, Max size is 16Tib
^1609849552266
- What are the supported types of Scaling Policies in an Autoscaling Group?:: There are 4 types of polices: Target Tracking, Simple Scaling, Step Scaling and Scheduled
^1609851205223
