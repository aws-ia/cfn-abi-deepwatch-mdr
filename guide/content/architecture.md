---
weight: 5
title: Architecture
description: Solution architecture
---

Deploying this ABI package with default parameters builds the following architecture:

![Architecture diagram](/images/overview-architecture.jpg)

As shown in the diagram, this solution sets up AWS CloudFormation to deploy three solutions as one:

* Solution A: An AWS CloudFormation nested stack creates an AWS Organizations management account that is encrypted using a customer managed AWS KMS key. The KMS key is managed by an audit account, and logs are delivered to a log archive account. CloudTrail logs all events for all AWS accounts within AWS Organizations.

* Solution B: An AWS CloudFormation nested stack enables Amazon GuardDuty for all existing accounts within AWS Organizations and turns on the auto-enable feature for future accounts. This solution allows you to choose the Regions in which to enable GuardDuty, and it delegates the GuardDuty administrator role to the audit account. It creates an S3 bucket in the logging account to collect aggregated findings and assigns a lifecycle policy to transition data to Amazon S3 Glacier for storage after 365 days. By default, this solution enables protections for GuardDuty, S3 buckets, and EKS.

* Solution C: A stack set in the logging account stores logs and sets up the required resources to ingest logs to the DeepWatch managed-detection-and-response platform. This includes all necessary Lambda functions, SNS topics, SQS queues, S3 Event Notifications, and IAM roles.

**Next:** [Deployment options](/deployment-options/index.html)