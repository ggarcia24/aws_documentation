---
updated: '2021-01-08'
cards-deck: AWS::Networking & Content Delivery::Global Accelerator
---

# Global Accelerator

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
