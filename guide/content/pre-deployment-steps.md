---
weight: 7
title: PreDeployment Options
description: Pre Deployment Options
---

Before deploying this ABI package, complete the following steps:

* Subscribe to partner product from AWS Marketplace using <AWS Marketplace Listing>
* Be a Deepwatch MDR customer
* If you don’t already have an AWS organization, create one. For more information, refer to Tutorial: Creating and configuring an organization.
* Ensure that your IAM user has sufficient permissions for the IAM user or role in your organization management account to create an organization trail and enable GuardDuty.
* Enable trusted access with AWS Organizations. For more information, refer to Enable trusted access with AWS Organizations. Otherwise, since this is a multi-account deployment, AWS CloudFormation won’t run.
* If you don’t already have them, create separate security tooling and log archive accounts in your AWS organization.
* Ensure that GuardDuty has not been enabled by the security tooling account (delegated administrator). For more information, refer to Managing GuardDuty accounts with AWS Organizations.
* Become familiar with the [additional resources](https://link), later in this guide.

**Next:** Choose **[Deployment Steps](/deployment-steps/index.html)** to get started.