---
updated: '2021-01-08'
cards-deck: AWS::Networking & Content Delivery::Global Accelerator
---

# Global Accelerator

AWS Global Accelerator is a networking service that helps you improve the availability and performance of the applications that you offer to your global users. AWS Global Accelerator is easy to set up, configure, and manage. It provides static IP addresses that provide a fixed entry point to your applications and eliminate the complexity of managing specific IP addresses for different AWS Regions and Availability Zones. AWS Global Accelerator always routes user traffic to the optimal endpoint based on performance, reacting instantly to changes in application health, your user’s location, and policies that you configure. Global Accelerator is a good fit for non-HTTP use cases, such as gaming (UDP), IoT (MQTT), or Voice over IP

With AWS Global Accelerator, you can shift traffic gradually or all at once between the blue and the green environment and vice-versa without being subject to DNS caching on client devices and internet resolvers, traffic dials and endpoint weights changes are effective within seconds.

## Features

- Use ANYCAST to route the requests to the closest EDGE location
- Offers consistent performance
- Leverage the AWS internal network to route the request to the application from the EDGE location
- Supports
    - [[VPC#Elastic IPs]]
    - [[EC2]] Instances
    - [[EC2#Application Load Balancers]]
    - [[EC2#Network Load Balancers]]
    - public or private
- Perform Health Checks to failover to other regions in less than 1min

## Security

- DDoS protection through [[AWS Shield]]

## Notes

## Questions / Flashcards

- In Global Accelerator, how much time do I need to wait before fails over to a different region in case of Health Check failures?:: You need to wait 1 min
^1610114378408
- How can I redirect traffic instantly in a blue/green deployment?::  With AWS Global Accelerator, you can shift traffic gradually or all at once between the blue and the green environment and vice-versa without being subject to DNS caching on client devices and internet resolvers
^1649200660563
