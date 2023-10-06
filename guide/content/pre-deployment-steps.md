---
weight: 7
title: Predeployment options
description: Predeployment options
---

Before deploying this ABI package, complete the following steps:

1. Subscribe to the [deepwatch Managed Security Services](https://aws.amazon.com/marketplace/pp/prodview-7xr5ppn2unxfe) AWS Marketplace Listing.
2. Have an existing customer agreement signed with Deepwatch.
3. If you don’t already have an AWS organization, create one. For more information, refer to [Tutorial: Creating and configuring an organization](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_tutorials_basic.html).
4. To create an organization trail and enable GuardDuty, ensure that your IAM user has sufficient permissions for the user or role in your management account.
5. Enable trusted access with AWS Organizations. For more information, refer to [Activate trusted access with AWS Organizations](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stacksets-orgs-activate-trusted-access.html). Otherwise, because this is a multi-account deployment, AWS CloudFormation won’t run.
6. Ensure that GuardDuty has not been enabled in the security tooling account (that is, the delegated administrator) already. For more information, refer to [Managing GuardDuty accounts with AWS Organizations](https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_organizations.html).
7. Become familiar with the [additional resources](/additional-resources/index.html) later in this guide.

**Next:** [Deployment Steps](/deployment-steps/index.html)