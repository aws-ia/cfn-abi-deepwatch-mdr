---
weight: 10
title: Test the deployment
description: Test the deployment
---

After the deployment completes, you will see the root stack and nested stacks in the AWS Control Tower management account.
![Control Tower Manager Account Stacks](/images/test-deployment.png)

If you log in to the Control Tower log archive account, you will see something similar. Take note of the output values of the `StackSet-deepwatch-logging-resource-configuration-*uuid*` stack. Your DeepWatch engineer needs these values to finish setting up ingestion.
![Control Tower log archive account stacks](/images/test-deployment2.png)


**Next:** [Additonal resources](/additional-resources/index.html)