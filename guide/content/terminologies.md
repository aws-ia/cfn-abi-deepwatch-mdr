---
weight: 3
title: Terminologies
description: Terminolgies used in this guide.
---

* **ABI :**   AWS Built In (ABI)  as explained above.
* **ABI Modules :** The GitHub repositories based of AWS SRA, which provide templates for enabling AWS foundational services like CloudTrail, GuardDuty, SecurityHub and more security services.
* **ABI Projects :** The GitHub repositories built by Partners in partnership with AWS. While building these projects, partners leverage ABI Modules provided to enable AWS services as needed before creating partner specific assets. The project contains 1\ IaC templates to automate enablement of both AWS and Partner services, 2\ Wrappers for most common formats like CfCT manifest, SC Baselines and more to allow customers to easily pick and choose from the services available. For Pilot, we will focus only on including CfCT manifest file in the package.
* **Deepwatch MDR :** The Deepwatch Managed Detection & Response service. This solution is applicable only for Deepwatch customers that have this service.
* **Deepwatch MDR AWS Account :** The AWS account that the Deepwatch MDR service, and requisite resources are hosted in. This account will be referenced in various architectures and diagrams located throughout.
* **Customer AWS Resources :** The resources deployed in the Deepwatch customer's AWS account to facilitate log-ingestion, including all necessary Lambdas, SNS Topics, SQS Queues, S3 Event Notifications, and IAM Roles & Policies.

**Next:** Choose [Cost and licenses](/costandlicenses/index.html) to get started.
