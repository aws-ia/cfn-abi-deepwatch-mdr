---
weight: 10
title: Test the deployment
description: Test the deployment
---

After the deployment completes, in the Control Tower Manager account you should see the root stack and all nested stacks successfully deployed.
![Control Tower Manager Account Stacks](/images/test-deployment.png)

If you log in to the Control Tower log archive account, you will see similar, take note of the output values of the "StackSet-deepwatch-logging-resource-configuration-*uuid*" stack. Your Deepwatch engineer will need these values to finish setting up ingestion.
![Control Tower Log Archive Account Stacks](/images/test-deployment2.png)


**Next:** Choose [Additonal Resources](/additional-resources/index.html) to get started.