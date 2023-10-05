---
weight: 8
title: Deployment steps
description: Deployment steps
---



## Launch the CloudFormation template in the AWS Organizations management account {#launch-cfn}

This option creates all of the necessary resources for ingestion of AWS security logs into the DeepWatch MDR platform. During the deployment, you can choose which options to enable for the individual services.

1. Download the [CloudFormation template](https://raw.githubusercontent.com/aws-ia/cfn-abi-deepwatch-mdr/main/templates/deepwatch-root-stack.yaml)
2. Launch the CloudFormation template from your [AWS Control Tower home Region](https://docs.aws.amazon.com/controltower/latest/userguide/region-how.html).
    * Stack name: `template-deepwatch-enable-integrations`
    * List parameters with [call out default values and update below example as needed]
        * **pDeepwatchRoleName**: `deepwatch-mdr-role`
        * **pSraTestingFlag**: `false`
        * **pSRASolutionName**: `sra-guardduty-org`
        * **pAutoEnableMalwareProtection**: `false`
        * **pAutoEnableK8sLogs**: `false`
        * **pAutoEnableS3Logs**: `true`
        * **pSRAS3BucketRegion**: `true`
        * **pSRASourceS3BucketName**: `aws-abi`
        * **pSRAStagingS3KeyPrefix**: `cfn-abi-deepwatch-mdr`

3. To launch the stack, choose the **Capabilities** and then **Submit**.

    [] I acknowledge that AWS CloudFormation might create IAM resources with custom names.

    [] I acknowledge that AWS CloudFormation might require the following capability: CAPABILITY_AUTO_EXPAND    

Wait for the CloudFormation status to change to `CREATE_COMPLETE`.


## Launch using Customizations for Control Tower {#launch-cfct}


[Customizations for AWS Control Tower](https://aws.amazon.com/solutions/implementations/customizations-for-aws-control-tower/) combines AWS Control Tower and other highly available, trusted AWS services to help customers set up a secure, multiaccount AWS environment according to AWS best practices. You can add customizations to your AWS Control Tower landing zone using an AWS CloudFormation template and service control policies (SCPs). You can deploy the custom template and policies to individual accounts and organizational units (OUs) within your organization.

CfCT also integrates with AWS Control Tower lifecycle events to hlep ensure that resource deployments stay in sync with your landing zone. For example, when you create a new account using AWS Control Tower account factory, CfCT deploys all of the resources that are attached to the account.

The templates provided by this ABI package are deployable through CfCT.

#### Prerequisites

The CfCT solution can't launch resources in the management account, so you must manually create a role in that account that has necessary permissions.

#### How it works

To deploy this sample partner integration page using CfCT, add the following blurb to the `manifest.yaml` file from your CfCT solution and update the account names as needed.

```yaml
resources:
  - name: deepwatch-logging-top-level
    resource_file: https://aws-abi.s3.us-east-1.amazonaws.com/cfn-abi-deepwatch-mdr/templates/deepwatch-root-stack.yaml
    deploy_method: stack_set
    parameters:
      - parameter_key: pSRASourceS3BucketName
        parameter_value: aws-abi
      - parameter_key: pSRAS3BucketRegion
        parameter_value: us-east-1
      - parameter_key: pAutoEnableS3Logs
        parameter_value: 'true'
      - parameter_key: pAutoEnableK8sLogs
        parameter_value: 'false'
      - parameter_key: pAutoEnableMalwareProtection
        parameter_value: 'false'
      - parameter_key: pDeepwatchRoleName
        parameter_value: 'deepwatch-mdr-role'
      - parameter_key: pEnableLambdaDataEvents
        parameter_value: 'false'
      - parameter_key: pEnableS3DataEvents
        parameter_value: 'true'
    deployment_targets:
      accounts:
        - [[MANAGEMENT-AWS-ACCOUNT-ID]]
```


**Next:** [Postdeployment options](/post-deployment-steps/index.html)