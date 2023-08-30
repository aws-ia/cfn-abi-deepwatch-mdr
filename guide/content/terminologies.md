---
weight: 3
title: Terminology
description: Terms used in this guide
---

* **ABI:** AWS Built-In.
* **ABI modules:** This GitHub repository is based on AWS SRA, which provide templates for enabling AWS foundational services like CloudTrail, GuardDuty, SecurityHub, and other security services.
* **ABI projects:** This GitHub repository is built by partners in collaboration with AWS. While building these projects, partners use ABI modules to enable necessary AWS services before creating partner-specific assets. The project contains 1\ IaC templates to automate enablement of both AWS and Partner services, 2\ Wrappers for most common formats like the CfCT manifest, SC baselines, and more so customers can pick and choose available services. For this pilot, the package includes only the CfCT manifest file.
* **Deepwatch MDR:** DeepWatch managed-detection-and-response service. This applies only to DeepWatch customers that use this service.
* **Deepwatch MDR AWS account:** The AWS account that uses the DeepWatch MDR service where the required resources are hosted. This account is referenced in the accompanying architecture diagrams.
* **Customer AWS resources:** The resources deployed in the DeepWatch customer's AWS account to facilitate log ingestion. This includes all of the necessary Lambdas, SNS topics, SQS queues, S3 Event Notifications, and IAM roles and policies.

**Next:** [Costs and licenses](/costandlicenses/index.html)
