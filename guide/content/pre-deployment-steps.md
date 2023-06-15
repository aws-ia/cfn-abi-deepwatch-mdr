---
weight: 7
title: Predeployment options
description: Predeployment options
---

Before deploying this ABI package, complete the following steps:

* Subscribe to the partner's product from AWS Marketplace using <AWS Marketplace Listing>.
* Be a DeepWatch MDR customer.
* If you don’t already have an AWS organization, create one. For more information, refer to [Tutorial: Creating and configuring an organization](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_tutorials_basic.html).
* To create an organization trail and enable GuardDuty, ensure that your IAM user has sufficient permissions for the user or role in your management account.
* Enable trusted access with AWS Organizations. For more information, refer to [Activate trusted access with AWS Organizations](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stacksets-orgs-activate-trusted-access.html). Otherwise, because this is a multiaccount deployment, AWS CloudFormation won’t run.
* If you don’t already have them, create separate security tooling and log archive accounts for your AWS organization.
* Ensure that GuardDuty has not been enabled by the security tooling account (that is, the delegated administrator). For more information, refer to [Managing GuardDuty accounts with AWS Organizations](https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_organizations.html).
* Review [Additional resources](https://link), later in this guide.

**Next:** [Deployment Steps](/deployment-steps/index.html)