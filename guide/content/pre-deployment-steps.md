---
weight: 7
title: Predeployment options
description: Predeployment options
---

Before deploying this ABI package, complete the following steps:
1. **Subscribe or Have an Agreement**: Start by subscribing to the [Deepwatch Managed Security Services](https://aws.amazon.com/marketplace/pp/prodview-7xr5ppn2unxfe) AWS Marketplace Listing. Alternatively, if you already have an existing customer agreement signed with Deepwatch, you can proceed.

2. **Create your AWS Organization using AWS Control Tower [Recommended]**: If you haven't already, create an AWS organization using AWS Control Tower. Detailed instructions can be found in the [Tutorial: AWS Control Tower quick start guide](https://docs.aws.amazon.com/controltower/latest/userguide/quick-start.html). **[Update]** As of Jan 2024, you can deploy this ABI package in an AWS Organization without AWS Control Tower setup as well.

3. **IAM User Permissions**: To create an organization trail and enable GuardDuty, ensure that your IAM user has the necessary permissions for the user or role in your management account.

4. **Activate Trusted Access**: Enable trusted access with AWS Organizations. This step is crucial for multi-account deployments. For detailed guidance, please refer to [Activate trusted access with AWS Organizations](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stacksets-orgs-activate-trusted-access.html). Without this, AWS CloudFormation won't run.

5. **Check GuardDuty Status**: Confirm that GuardDuty was not enabled individually or using delegated admin in any of the accounts with in the organizations. More information on this can be found in [Managing multiple accounts in Amazon GuardDuty](https://docs.aws.amazon.com/guardduty/latest/ug/guardduty_accounts.html).

6. **Explore Additional Resources**: As you proceed, be sure to familiarize yourself with the [additional resources](/additional-resources/index.html) available later in this guide.

**Next:** [Deployment Steps](/deployment-steps/index.html)