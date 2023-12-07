---
weight: 99
title: Cleanup instructions
description: Instructions to clean up the resources created by the AWS Built-in solution
---
After trying this AWS Built-in solution, you may want to redeploy or remove it completely. In either case, this solution leaves certain resources as-is when you delete the stacks that are deployed. This behavior is working as designed to avoid deleting the history of data collections in your accounts.

You can clean up resources created this AWS Built-in solution to avoid incurring charges for resources created and avoid conflicts while redeploying the stack.

This section provides instructions to clean up the resources created by the AWS Built-in package.

## 1. Delete the CloudFormation stack

1. Navigate to the [AWS CloudFormation console](https://console.aws.amazon.com/cloudformation#/stacks/).
2. Choose the stack created by the AWS Built-in solution and delete it.
3. Wait for the **DELETE_COMPLETE** status to confirm the stack deletion.

## 2. Delete resources created by the AWS Built-in solution

### Automated cleanup (PLEASE REVIEW the manual cleanup steps below for resources that deleted by the automated cleanup)

Establish a session to the management account and run the following command:

```bash
cd ${REPO_ROOT}/scripts
python3 cleanup_config.py -C cleanup_config.json
```

**Note-1:** The automated cleanup script will not delete all the stacks. You still need to delete the stacks `*CloudTrailStack*` and `*GuardDutyStack*` manually (if exists).

**Note-2:** If you choose `pDisableGuardDuty` as `No` (default) during the installation of the solution, you need to [delete the  guardduty detector](https://docs.aws.amazon.com/cli/latest/reference/guardduty/delete-detector.html) in all regions.

### Manual cleanup.

#### In the management account:

1. [Delete the following Amazon S3 buckets](https://docs.aws.amazon.com/AmazonS3/latest/userguide/delete-bucket.html).

- sra-gd-staging-`<account-id>`-`<region>`
- sra-cloudtrail-staging-`<account-id>`-`<region>`
- sra-helper-`<account-id>`-`<region>`
- sra-staging-`<account-id>`-`<regions>` # Repeat for all regions where the solution is deployed.

2. [Delete Systems Manager parameters](https://docs.aws.amazon.com/systems-manager/latest/userguide/deleting-parameters.html) that start with below prefixes. Repeat for all active regions.

- `/sra/regions/`
- `/sra/control-tower/`
- `/sra/staging-s3-bucket-name`

3. [Delete the AWS CloudWatch log groups](https://docs.aws.amazon.com/solutions/latest/research-service-workbench-on-aws/deleting-the-aws-cloudwatch-logs.html) that start with the following prefixes:

- `/sra/sra-org-trail`
- `/aws/lambda/sra-codebuild-project-lambda`
- `/aws/lambda/sra-guardduty-codebuild-project-lambda`

4. [Delete a build project in AWS CodeBuild](https://docs.aws.amazon.com/codebuild/latest/userguide/delete-project.html) that start with the following prefixes.

- `sra-codebuild-project`

5. [Delete AWS IAM roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_manage_delete.html) that are listed below.

- `sra-execution`

6. [Delete a stack set](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stacksets-delete.html) with name `sra-stackset-execution-role`.

7. [Delete a stack](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stacks.html) with follwing stack names: 

- `sra-common-prerequisites-staging-s3-bucket`
- `*CloudTrailStack*`
- `*GuardDutyStack*`

8. [Delete GuardDuty detectors](https://docs.aws.amazon.com/cli/latest/reference/guardduty/delete-detector.html) in all regions (Only if you choose `pDisableGuardDuty` as `No` during the installation of the solution).

#### In the log archive account:

1. [Delete the following Amazon S3 buckets](https://docs.aws.amazon.com/AmazonS3/latest/userguide/delete-bucket.html).

- sra-guardduty-org-delivery-`<account-id>`-`<region>`
- sra-org-trail-logs-`<account-id>`-`<region>`

2. [Delete Systems Manager parameters](https://docs.aws.amazon.com/systems-manager/latest/userguide/deleting-parameters.html) that start with below prefixes. Repeat for all active regions.

- `/sra/regions/`
- `/sra/control-tower/`

3. [Delete the AWS CloudWatch log groups](https://docs.aws.amazon.com/solutions/latest/research-service-workbench-on-aws/deleting-the-aws-cloudwatch-logs.html) that start with the following prefixes:

- `/aws/lambda/sra-ct-s3`
- `/aws/lambda/sra-gd-s3`
- `/sra/gd/`

4. [Delete AWS IAM roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_manage_delete.html) that are listed below.

- `sra-execution`

#### In the audit account:

1. [Delete AWS IAM roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_manage_delete.html) that are listed below.
- `sra-execution`

