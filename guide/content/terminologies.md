---
weight: 3
title: Terminology
description: Terms used in this guide
---

* **ABI:** AWS Built-In.
* **ABI modules:** These are modules in the [AWS Security Reference Architecture](https://github.com/aws-samples/aws-security-reference-architecture-examples/tree/main/aws_sra_examples/modules) repository. This provide templates for enabling AWS foundational services like CloudTrail, GuardDuty, SecurityHub, and other security services.
* **ABI projects:** This GitHub repository is built by partners in collaboration with AWS. While building these projects, partners use ABI modules to enable necessary AWS services before creating partner-specific assets. The project contains:

1. IaC templates to automate the enablement of both AWS and Partner services.
2. Wrappers for most common formats like the CfCT manifest, AWS Service Catalog baselines, and more so customers can pick and choose available services.

In the current release, the package includes only the CfCT manifest file, in addition to the IaC templates.
* **Deepwatch MDR:** Deepwatch managed-detection-and-response service. This applies only to Deepwatch customers that use this service.
* **Deepwatch MDR AWS account:** The AWS account that uses the Deepwatch MDR service where the required resources are hosted. This account is referenced in the accompanying architecture diagrams.
* **Customer AWS resources:** The resources deployed in the Deepwatch customer's AWS account to facilitate log ingestion. This includes all of the necessary Lambdas, SNS topics, SQS queues, S3 Event Notifications, and IAM roles and policies.

**Next:** [Costs and licenses](/costandlicenses/index.html)
