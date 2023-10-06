---
weight: 5
title: Architecture
description: ABI Solution architecture
---

Deploying this ABI package with default parameters builds the following architecture:

![Architecture diagram](/images/overview-architecture.jpg)

As shown in the diagram, this solution sets up the following:

#### Enable organization level CloudTrail
    * [Creates a trail for the organization](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/creating-trail-organization.html) in the management account.
    * Customer managed KMS key for the AWS Organizations CloudTrail logs and S3 server-side encryption created in the audit account.
    * AWS Secrets Manager secret containing the customer managed KMS key ARN in the audit account.
    * S3 bucket where the Organization CloudTrail logs are sent for all accounts in the AWS Organization

#### Enable Amazon GuardDuty at organization level

* Enables GuardDuty for all AWS accounts that are current members of the target organization in AWS Organizations
* Turns on the Auto-Enable feature in GuardDuty, which automatically enables GuardDuty for any accounts that are added to the target organization in the future
* Uses the organization’s Audit account as the GuardDuty delegated administrator
* Creates an Amazon Simple Storage Service (Amazon S3) bucket in the logging account and configures GuardDuty to publish the aggregated findings from all accounts in this bucket
* Assigns a life-cycle policy that transitions findings from the S3 bucket to Amazon S3 Glacier Flexible Retrieval storage after 365 days, by default
* Enables GuardDuty S3 protection by default, with the option to enable EKS and Malware protection.

#### Deepwatch Managed Detection and Response (MDR) Integration

* A stack set on the management account that creates the following resources in the Log Archive account:
    * Create event notifications  and queuing mechanism on CloudTrail and GuardDuty logging buckets to forward the events to the Deepwatch MDR platform. This includes all necessary Lambda functions, SNS topics, SQS queues, S3 Event Notifications, and IAM roles.

**Next:** [Deployment options](/deployment-options/index.html)