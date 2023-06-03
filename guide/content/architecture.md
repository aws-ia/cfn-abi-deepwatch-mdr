---
weight: 5
title: Architecture
description: Solution architecture.
---

Deploying this ABI package with default parameters builds the following architecture.

![Architecture diagram](/images/overview-architecture.jpg)

As shown in the diagram, the Quick Start sets up the following:

This solution utilizes CloudFormation to deploy three solutions as one:

* Solution A: A CloudFormation Nested Stack that deploys an Organization CloudTrail solution that will create an Organization CloudTrail within the Organization Management Account that is encrypted with a Customer Managed KMS Key managed in the Audit Account and logs delivered to the Log Archive Account. An Organization CloudTrail logs all events for all AWS accounts in the AWS Organization.

* Solution B: A CloudFormation Nested Stack that enables GuardDuty for all existing AWS accounts in an AWS Organization and turns on the Auto-Enable feature for future accounts. The solution allows you to choose the regions in which to enable GuardDuty and delegates the GuardDuty administrator role to the organization's Audit account. It creates an S3 bucket in the logging account to collect aggregated findings from all accounts and assigns a lifecycle policy to transition data to Glacier storage after 365 days. The solution also enables GuardDuty S3 and EKS protection by default. 

* Solution C: A StackSet in the logging account account where the previous solutions were configured to store logs to and sets ups all of the resources required to begin ingesting those logs to the Deepwatch Managed Detection & Response platform, including all necessary Lambdas, SNS Topics, SQS Queues, S3 Event Notifications, and IAM Roles & Policies. The outputs of this StackSet are all that is needed to finish setting up ingestion of your organizations CloudTrail and GuardDuty logs.


**Next:** Choose [Deployment Options](/deployment-options/index.html) to get started.