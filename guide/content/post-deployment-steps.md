---
weight: 9
title: Postdeployment options
description: Postdeployment options
---

## Verifying the solution's functionality

Wait for the stack to finish deploying. You can check the status of the deployment either via the AWS console or by running the following command:

   ```
   aws cloudformation describe-stacks --stack-name <YOUR_STACK_NAME>
   ```

   The stack status is returned in the output. Wait until the status is `CREATE_COMPLETE` before proceeding to the next step. When the stack finishes deploying, you can access the created resources via the AWS Management Console or AWS CLI.

After the deployment completes, you will see the root stack and nested stacks in the AWS Control Tower management account with status `CREATE_COMPLETE`.
![Control Tower Manager Account Stacks](/images/test-deployment.png)

After you deploy the solution, provide your Deepwatch security engineer expert the output values of the `StackSet-deepwatch-logging-resource-configuration-*uuid*` stack. These values will be needed to finish setting up ingestion:
- `oCloudTrailQueueArn`
- `oGuardDutyQueueArn`
- `oDeepwatchRoleArn`

![Control Tower log archive account stacks](/images/test-deployment2.png)

**Next:** [Additonal resources](/additional-resources/index.html)
