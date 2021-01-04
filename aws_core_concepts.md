# AWS Core Concepts
[[AWS]] is a [Cloud Provider][0], that means that it offers many services to help different organizations with their [it infrastructure][1] or [processes][2].

This services are built inside [datacenters][3] connected by [computer network][4] it means that the services that you access in [[AWS]] will be bound to a certain location, because in the end this services require some [infrastructure][1] that needs to be [deployed][4][^1] and physically "living" somewhere.

Services in [[AWS]] are offered depending on:
- Global availability: Service is available without restrictions across all [AWS Regions](#AWS-Regions)
- Regional availability: Service is available in an specific [AWS Regions](#AWS-Regions)
- Edge availability: Service is available in a specific location close to user network location


## AWS Regions
[[AWS]] calls region to a group of availability zones hosted in a geographical area. Availability zones (AZ for short) are isolated locations, meaning that are [datacenters][3] where the actual service is running. Some times you also have Local zones, which allows you to place resources in multiple locations close to your users.

Here's a list of the AWS Regions available in June 2020:

[![aws regions](img/aws_regions.png)][6]

Services and Resources **are not replicated across AWS Regions unless you specifically do it so** this means that if one of the AZ where your application is running has a failure, you application will run into failure, that's why [[AWS]] suggest that services that need to be [highly available][7] to be deployed in more than one (and at minimum 3) AZ.

For this types of changes, it usually means that you need to make changes and to adapt for that in your [application architecture][8], and apply some common [design patterns][9].

There's more information about this topic in the [Relational Database Service][10] (RDS for short) [user guide][11] that I suggest you to read in case you need more information.

# Amazon Resource Name (ARN)
Amazon Resource Names (ARNs) uniquely identify AWS resources, it's a string that contains the following:

```text
arn:partition:service:region:account-id:resource-id
arn:partition:service:region:account-id:resource-type/resource-id
arn:partition:service:region:account-id:resource-type:resource-id
```

* `arn`: All ARNs start with the string "arn"
* `partition`: The partition in which the resource is located. A partition is a group of AWS Regions. Each AWS account is scoped to one partition. The following are the supported partitions:
	*	aws - AWS Regions
	* aws-cn - AWS China Regions
	* aws-us-gov - AWS GovCloud (US) Regions
* service: The service namespace that identifies the AWS product. For example, s3 for Amazon S3 resources.
* region: The Region. For example, us-east-2 for US East (Ohio).
* account-id: The ID of the AWS account that owns the resource, without the hyphens. For example, 123456789012.
* resource-id: The resource identifier. This part of the ARN can be the name or ID of the resource or a resource path. For example, user/Bob for an [IAM][13] user or instance/i-1234567890abcdef0 for an EC2 instance. Some resource identifiers include a parent resource (sub-resource-type/parent-resource/sub-resource) or a qualifier such as a version (resource-type:resource-name:qualifier).



https://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html

# What's next
Head over to [aws core services][12]

[0]: basic_concepts/cloud/index.md
[1]: basic_concepts/infrastructure.md
[2]: basic_concepts/it_processes.md
[3]: basic_concepts/datacenters.md
[4]: basic_concepts/network/index.md
[5]: basic_concepts/deployment.md
[6]: https://aws.amazon.com/about-aws/global-infrastructure/
[7]: basic_concepts/high_availability.md
[8]: basic_concepts/architecture.md
[9]: basic_concepts/design_patterns.md
[10]: database/RDS.md
[11]: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.RegionsAndAvailabilityZones.html
[12]: aws_core_services.md
[13]: security_identity_and_compliance/IAM.md
[^1]: This deployments and infrastructure will be handled by [[AWS]], as part of their service offering, that means that a lot of the costs, and time required will be offloaded from the people using the service, hence being able to focus exclusively on the actual application/service that they are developing.
