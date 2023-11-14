---
weight: 5
title: Architecture
description: ABI Solution architecture
---

Deploying this ABI package with default parameters builds the following architecture:

![Architecture diagram](/images/overview-architecture.jpg)

As shown in the diagram, this solution sets up the following:

#### Enable organization level CloudTrail

* [Creates an organizational trail for all accounts in the organization](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/creating-trail-organization.html) in the management account.
* A customer managed KMS key for the AWS Organizations CloudTrail logs and Amazon Simple Storage Service (Amazon S3) server-side encryption in the audit account.
* AWS Secrets Manager secret containing the customer managed KMS key ARN in the audit account.
* Amazon S3 bucket in the log archive account, where the organization CloudTrail logs are sent for all accounts in the AWS Organization.

#### Enable Amazon GuardDuty at organization level

* Enables GuardDuty for all AWS accounts that are current members of the target organization in AWS Organizations
* Turns on the Auto-Enable feature in GuardDuty, which automatically enables GuardDuty for any accounts that are added to the target organization in the future
* Uses the organization’s Audit account as the GuardDuty delegated administrator
* Creates an Amazon Simple Storage Service (Amazon S3) bucket in the logging account and configures GuardDuty to publish the aggregated findings from all accounts in this bucket
* Assigns a life-cycle policy that transitions findings from the S3 bucket to Amazon S3 Glacier Flexible Retrieval storage after 365 days, by default
* Enables GuardDuty S3 protection by default, with the option to enable EKS and Malware protection.

#### Deepwatch Managed Detection and Response (MDR) Integration

* Deploys a stack set from the management account that creates the following resources in the Log Archive account:
  * Event notification on S3 bucket where the organizational GuardDuty and CloudTrail logs are stored
  * SNS Topic and SQS queues to process the S3 event notifications
  * Lambda function for processing and filtering of messages in SQS queues
  * IAM Role for cross-account role assumption by Deepwatch MDR Platform

**Next:** [Deployment options](/deployment-options/index.html)