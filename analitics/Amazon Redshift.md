---
updated: '2021-01-05'
cards-deck: AWS::Analytics::Amazon Redshift
---

# Amazon Redshift

## Features

- Audit Logging
    - Get information about the connection, queries and user activity
- Amazon Redshift Enhanced VPC Routing
    - Enable use of [[VPC]] features ([[VPC#^2026c9]], [[VPC#Network ACLs]], [[VPC#Security Groups]], [[VPC#Endpoints]] and endpoints policies, [[VPC#Internet Gateways]], and DNS)
    - you can force all COPY and UNLOAD traffic to your VPC

## Security

## Notes

## Questions / Flashcards

- How can I monitor all the COPY and UNLOAD traffic in a Redshift cluster?:: You can enable Enhanced VPC Routing to enable Flow Logs, NACLs, Security Groups, VPC endpoints and endpoints policies, internet gateways, and DNS support through the VPC configuration
^1609852663701
