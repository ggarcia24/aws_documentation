---
updated: '2021-01-04'
cards-deck: AWS::Compute::EC2
---

# EC2

Elastic Cloud Compute

## Features

- Manage Virtual Machines
- Manage Virtual drives (Block)
- Load Balancers
- Auto Scaling

### EC2 Instances

- You can reduce pricing for very long running (minimum 1year) instances using Reserved Instances (but you will not be able to change instance type)
- Scheduled reserved instances allows you to reduce costs based on a schedule
- Can customize instances by using EC2 User Data the first time first boots

### EC2 Launch Templates

- Can have multiple versions
- Provision using on-demand or spot instances or a mix
- Can use T2 unlimited burst feature
- recommended by AWS 

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

### Elastic Load Balancers

- Supports Cross-Zone load balancing to redirect traffic to all instances
- Support Health Checks to know if they should forward traffic
- Deregistration Delay
    - Allow instances to finish processing requests before termination/unhealthy
    - Beween 0 (disabled) to 3600 (300 default)
- SSL/TLS
    - Using [[ACM]]
    - Using [[IAM]]
    - Import
- Can be
    - Internal: Accesible only from your Private network
    - External: Accessible from the public

#### Classic Load Balancers

- Fixed hostname i.e `xxxx.region.elb.amasonws.com`
- Cross-Zone load balancing is disabled by default
- Instances are "added" to the load balancer
- Heath checks based on TCP or HTTP
- SSL/TLS
    - Single certificates (no Server Name Indication)
- Uses [[VPC#Security Groups]]
- Supports Stickiness
- Support
    - HTTP/HTTPS
    - TCP

#### Application Load Balancers

- Fixed hostname i.e `xxxx.region.elb.amasonws.com`
- Cross-Zone load balancing is enabled by default and cannot be disabled
- Uses Target Groups to match instances
- 400 ms latency
- Health Checks are done at the Target Group level
- Uses [[VPC#Security Groups]]
- Supports Stickiness at the routing level
- SSL/TLS
    - Multiple certificates (Server Name Indication)
- Routing is rule based
    - Path in URL
    - HTTP header
    - HTTP request method
    - Query Strings
    - Source IP
- Routing Actions
    - Forward to
    - Redirect to
    - Fixed response
- Support
    - HTTP/HTTPS
    - WebSocket

#### Network Load Balancers

- one static IP per AZ with [[VPC#Elastic IPs]] support
- Cross-Zone load balancing is disabled by default
- Handle millions of requests per second
- 100 ms latency
- Doesn't support [[VPC#Security Groups]]
- You cannot change the AZ after created
- SSL/TLS
    - Multiple certificates (Server Name Indication)
- Support
    - TLS
    - TCP
    - UDP

### Auto Scaling Groups

- Allows automatic Scale Out / Scale In
- Ensure minimum,desired,maximum instances running
- Launch Template / Configuration
    - AMI + Instance Type
    - EC2 User Data
    - EBS Volumes
    - Security Groups
    - SSH Key Pair
- Automatically register instances to Load Balancers / Target Groups
- Terminates instances if marked as unhealthy by the Health Check
    - EC2 (default)
    - ELB (optional)
- Scaling policies
    - Target Tracking
        - Maintain metric at certain value i.e CPU Usage always 50%
    - Simple / Step Scaling
        - [[CloudWatch]] alarm performs action i.e add/remove instances
    - Schedule
        - You know in advance when the peaks are i.e Monday 9AM
- You can use Scaling Cooldowns to control how fast the scaling activity affects your counters, the default is 300 sec
- Termination Policy
    - Default: Remove the oldest launch configuration from the AZ with the higher number of instances
- Lifecycle Hooks
    - Instance Launching
    - Instance Terminating

## Security

## Notes

- Load balancers can scale but are not instantaneous, some times you'll need to contact AWS for a "warm-up"
- To update an Auto Scaling  Group you must provide a new launch configuration

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
- Are changes on the launch configuration reflected on the Auto Scaling Group?:: No, to update an Auto Scaling group you need create a new launch configuration
^1610295886405
- What are the supported types of Scaling Policies in an Auto Scaling Group?:: There are 4 types of polices: Target Tracking, Simple Scaling, Step Scaling and Scheduled
^1609851205223
- Can you use a launch configuration to provision capacity using Spot instances and  On-Demand Instances?:: No, you cannot use a launch configuration to provision capacity across multiple instance types using both On-Demand Instances and Spot Instances
^1649189294102
- If I have sever-bound licenses (like Windows Server) how can I use them in AWS?:: The only option that supports sever-bound licenses Dedicated Hosts to launch Amazon EC2 instances on physical servers
^1649194823782
