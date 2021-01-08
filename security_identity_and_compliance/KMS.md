---
updated: '2020-12-29'
cards-deck: AWS::Security, Identity, & Compliance::KMS

---

# KMS

Key Management Service 

## Features

## Security

**AWS Key Management Service (AWS KMS)** is a managed service that makes it easy for you to create and control the encryption keys used to encrypt your data. The master keys that you create in AWS KMS are protected by FIPS 140-2 validated cryptographic modules. AWS KMS is integrated with most other AWS services that encrypt your data with encryption keys that you manage. AWS KMS is also integrated with AWS CloudTrail to provide encryption key usage logs to help meet your auditing, regulatory and compliance needs.

![](https://docs.aws.amazon.com/kms/latest/developerguide/images/encrypt-with-data-key.png)

It is stated in the scenario that you have to encrypt the data **before** writing it to disk for storage. What this means is that you will have to temporarily store the data in **memory** and not persist it on the disk, then encrypt it on the fly before finally storing it. The end result would be an encrypted data in your EBS volume.

You cannot directly enable EBS encryption in an existing unencrypted EBS volume. You can encrypt them by creating either a volume or a snapshot. If you enabled encryption by default, Amazon EBS encrypts the resulting new volume or snapshot using your default key for EBS encryption. Even if you have not enabled encryption by default, you can enable encryption when you create an individual volume or snapshot. Whether you enable encryption by default or in individual creation operations, you can override the default key for EBS encryption and select a symmetric customer-managed CMK. Amazon EBS does not support asymmetric CMKs.

You can configure your application to use the KMS API to encrypt all data before saving it to disk. By using AWS KMS, you gain more control over access to data that you encrypt. You can use the key management and cryptographic features directly in your applications or through AWS services that are integrated with AWS KMS. Whether you are writing applications for AWS or using AWS services, AWS KMS enables you to maintain control over who can use your customer master keys and gain access to your encrypted data.

## Notes

## Questions / Flashcards
