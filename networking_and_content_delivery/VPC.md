---
updated: '2020-12-30'
cards-deck: AWS::Networking & Content Delivery::VPC

---

# Amazon VPC

A Virtual Private Cloud (VPC) is the underlying networking component that allows for all of the other AWS services to be connected without the need of an Internet Connection.

https://docs.aws.amazon.com/vpc/index.html

![AWS VPC with most components connected](img/vpc_components.png)

## Features

- Allows you to expose a [[EC2#Network Load Balancer]] to thousands of VPCs in your account or in other accounts using VPC Endpoint Services (Private Link)
- You can connect multiple VPCs (even from different accounts) together using VPC Peering as long as there's no overlapping of the CIDR between any of them
- Flow Logs: log all the traffic to [[S3]] or [[CloudWatch]] ^2026c9
- Allows you to create Site-to-Site VPN connections (using internet) to connect a Private Datacenter to a VPC 
- By mindful about overlapping IP ranges, specially when connecting different networks with your VPC

### Subnets

- Subnets are tied to an specific Availability Zone
- You can edit your Subnets CIDR blocks after creating your VPC
- Private Subnets can connect to the Internet by using either NAT Instances or NAT Gateways (preferred)

### Route Tables

### Internet Gateways

- Must be created separately from VPC
- It scales horizontally and is HA and redundant
- It's also a NAT for the instances that have public IP address

### Elastic IPs

### Endpoints

- Provide private access to AWS Services

### Service Endpoints

- You could use [[IAM]] Policies in VPC Endpoints to add an extra level of control access to this endpoint

### NAT Gateways

- Managed and redundant
- Linked to an specific Availability Zone
- Are created in the Public Subnet
- Requires configuring the Route Table in the Private Subnet
- Doesn't support port forwarding
- Cannot have security groups

### NAT Instances

- Can be used as a bastion host
- Can have a security group
- Supports port forwarding

### Network ACLs

### Security Groups

- Can act as firewalls outside [[EC2]] instances an other services
- Can be attached to multiple [[EC2]] instances and [[EC2]] instances can have multiple SGs
- Can reference other security groups
- Outbound rules are stateful meaning that it will work even if there's a denying rule as long as it part of an incoming rule 
- By default all traffic inbound is denied and all traffic outbound is allowed

### Virtual Private Gateways

### Site-to-Site VPN Connections

### Transit Gateways

- Can be used to simplify network topologies
- Is a Star Connection to have transitive peering between thousands of VPCs and on-premises
- hub-and-spoke connection
- can be shared cross-account using [[RAM]]
- You can peer Transit Gateways across regions

### Traffic Mirroring

## Security

- https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Security.html

## Notes

## Questions / Flashcards

- How many VPCs are allowed in your account?:: There is a soft limit of 5 VPCs per region
^1609849371304
- How many CIDR blocks can be inside a VPC?:: There is a maximum of 5 CIDR blocks per VPC
^1609849371308
- What are the CIDR size constrains in a VPC?:: The minimum size for a CIDR block is /28 (16 IPs) and the maximum is /16 (65536 IPs)
^1609849371311
- What are the IP ranges allowed in a VPC?:: VPCs only support using private IP ranges 10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16
^1609849371314
- How many IP addresses are reserved in a Subnet?:: Each subnet will reserve 5 IPs first 4 and last one for example in 10.0.0.0/24: 10.0.0.0 is Network Address, 10.0.0.1 is VPC router, 10.0.0.2 is DNS, 10.0.0.3 is reserved, 10.0.0.255 is broadcast
^1609849371318
- How many Internet Gateways can you connect to a VPC?:: You can only have a single IGW connected to a VPC
^1609849371321
- How can I avoid losing internet access in all my private networks instances if I create a NAT Gateway was created in a single Availability Zone?:: Create a NAT gateway in each Availability Zone and configure your private subnet routing to ensure use of the NAT gateway in the same Availability Zone.
^1609856422873
- Are VPC Peering connections transitive?:: No, if you want to connect 3 VPCs with VPC Peering you'll need to create all peering connections in between them (A<->B, B<->C, C<->A)
^1609849371325
- Besides the VPC Peering configuration, what else is required to connect 2 VPCs together?:: You must update each of the VPCs routing table to ensure instances can communicate
^1609849371328
- Can I use Egress Only Internet Gateway to route IPv4 traffic?:: No, they are only for IPv6 as IPv6 are public address
^1609849371332
- For example in a security event, how can you control the traffic that reaches your VPC?:: To control the inbound/outbound traffic of a VPC, you can use NACLs. It is an optional layer of security for your VPC that acts as a firewall for controlling traffic in and out of one or more subnets. This is the best solution among other options as you can easily add and remove the restriction in a matter of minutes.
^1609849371335
- How can you make sure in a security group to allow traffic coming only from a VPC Peering?:: you can reference Peered VPCs (even from an another account) in the SG configuration 
^1609849371338
- What could it be if an EC2 Instance in a private subnet without internet access could not connect to a Gateway VPC Endpoint i.e S3?:: Take into account that VPC Endpoints have their regions "hardcoded" that means that you are required to specify the region when interacting using API/CLI
^1609849371341
- Can you attach a security group to a NAT Gateway?:: No, only NAT Instances support having a security group attached
^1649190364806
- Can you use a NAT Gateway as a Bastion Host?:: No, only NAT Instances can be used as a Bastion Host
^1649190364811
- Can you configure port forwarding in a NAT Gateway?:: No only NAT Instances support port forwarding
^1649190364813
