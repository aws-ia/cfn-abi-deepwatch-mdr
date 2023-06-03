---
weight: 9
title: PostDeployment Options
description: Post deployment options
---

## Verifying the solution functionality
Wait for the stack to finish deploying. You can check the status of the deployment by running the following command:

   ```
   aws cloudformation describe-stacks --stack-name <YOUR_STACK_NAME>
   ```

   The stack status will be returned in the output.

Once the stack has finished deploying, you can access the resources created by the stack via the AWS Management Console or the AWS CLI.

Following the deployment of the solution, please provide your Deepwatch engineer with the following outputs from the Deepwatch template:

- `oCloudTrailQueueArn`
- `oGuardDutyQueueArn`
- `oDeepwatchRoleArn`


**Next:** Choose [Test the Deployment](/test-deployment/index.html) to get started.