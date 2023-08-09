---
weight: 9
title: Postdeployment options
description: Postdeployment options
---

## Verifying the solution's functionality
Wait for the stack to finish deploying, and then check the status of the deployment by running the following command:

   ```
   aws cloudformation describe-stacks --stack-name <YOUR_STACK_NAME>
   ```

   The stack status is returned in the output.

When the stack finishes deploying, you can access the created resources via the AWS Management Console or AWS CLI.

After you deploy the solution, provide your DeepWatch engineer with the following outputs from the DeepWatch template:

- `oCloudTrailQueueArn`
- `oGuardDutyQueueArn`
- `oDeepwatchRoleArn`

**Next:** [Test the Deployment](/test-deployment/index.html)