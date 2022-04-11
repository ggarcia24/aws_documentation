---
updated: '2021-01-05'
cards-deck: AWS::Analytics::Amazon Redshift
---

# Amazon Redshift

## Features

- 10 times better performance than other data warehouses
- Scales to PBs of data
- Columnar storage of data
- Visualize data through [[Quicksight]] or Tableau
- Data sources
    - [[S3]]
    - [[DynamoDB]]
    - [[DMS]]
- Nodes
    - Leader Node: query planning, result aggregation
    - Compute Node: performing the queries
- Redshift Spectrum
    - query [[S3]] directly (without loading)
- Supports [[VPC#Endpoints]]
- Audit Logging
    - Get information about the connection, queries and user activity
- Amazon Redshift Enhanced VPC Routing
    - Enable use of [[VPC]] features ([[VPC]] Flow Logs, [[VPC#Network ACLs]], [[VPC#Security Groups]], [[VPC#Endpoints]] and endpoints policies, [[VPC#Internet Gateways]], and DNS)
    - Force all COPY and UNLOAD traffic to your VPC

## Security

## Notes

## Questions / Flashcards

- How can I monitor all the COPY and UNLOAD traffic in a Redshift cluster?:: You can enable Enhanced VPC Routing to enable Flow Logs, NACLs, Security Groups, VPC endpoints and endpoints policies, internet gateways, and DNS support through the VPC configuration
^1609852663701
- How can I reference historical data stored in S3 from Redshift?:: You can use Redshift Spectrum to query S3 data without loading it.
^1649200136728
