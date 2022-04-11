---
updated: '2021-01-05'
cards-deck: AWS::Management & Governance::CloudTrail
---

# CloudTrail

AWS CloudTrail is a service that enables governance, compliance, operational auditing, and risk auditing of your AWS account. With CloudTrail, you can log, continuously monitor, and retain account activity related to actions across your AWS infrastructure.

CloudTrail provides event history of your AWS account activity, including actions taken through the AWS Management Console, AWS SDKs, command line tools, API calls, and other AWS services. This event history simplifies security analysis, resource change tracking, and troubleshooting.

Reference:
- [Cloudtrail Documentation][1]

## Features

- Enabled by default
- Allows you to monitor AWS Services API/CLI/Console calls for auditing and compliance
- Can be applied to all regions or a single region
- Can put logs to [[CloudWatch]]

## Security

## Notes

## Questions / Flashcards

- How can I monitor all the activity made to AWS resources in all regions?:: You can create a CloudTrail that applies to all regions.
^1609853290448
- How can I monitor all API calls made to a Redshift instance for auditing and compliance?:: With CloudTrail you can log, continuously monitor, and retain account activity related to actions across your AWS infrastructure.
^1609852039992

[1]: https://aws.amazon.com/cloudtrail/
