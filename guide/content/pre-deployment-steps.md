---
weight: 7
title: Predeployment options
description: Predeployment options
---

Before deploying this ABI package, complete the following steps:
1. **Subscribe or Have an Agreement**: Start by subscribing to the [Deepwatch Managed Security Services](https://aws.amazon.com/marketplace/pp/prodview-7xr5ppn2unxfe) AWS Marketplace Listing. Alternatively, if you already have an existing customer agreement signed with Deepwatch, you can proceed.

2. **Create your AWS Organization using Control Tower**: If you haven't already, create an AWS organization. Detailed instructions can be found in the [Tutorial: Creating and configuring an organization](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_tutorials_basic.html).

3. **IAM User Permissions**: To create an organization trail and enable GuardDuty, ensure that your IAM user has the necessary permissions for the user or role in your management account.

4. **Activate Trusted Access**: Enable trusted access with AWS Organizations. This step is crucial for multi-account deployments. For detailed guidance, please refer to [Activate trusted access with AWS Organizations](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stacksets-orgs-activate-trusted-access.html). Without this, AWS CloudFormation won't run.

5. **Check GuardDuty Status**: Confirm that GuardDuty has not already been enabled in the security tooling account (i.e., the delegated administrator). More information on this can be found in [Managing GuardDuty accounts with AWS Organizations](https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_organizations.html).

6. **Explore Additional Resources**: As you proceed, be sure to familiarize yourself with the [additional resources](/additional-resources/index.html) available later in this guide.

**Next:** [Deployment Steps](/deployment-steps/index.html)