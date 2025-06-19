---
title: "Cleanup"
chapter: false
weight: 92
---

### Cleanup Instructions
In order to prevent charges to your account we recommend cleaning up the infrastructure that was created. If you plan to keep things running so you can examine the workshop a bit more please remember to do the cleanup when you are done. It is very easy to leave things running in an AWS account, forget about it, and then accrue charges. Run the command below to remove all of the resources created for this workshop. It may take a few minutes to complete.

Here are the instructions to delete the resources in the Hosted Event. This will clean up all the workshop resources.

```bash
# Delete CloudFormation Stacks
aws cloudformation delete-stack --stack-name $(aws cloudformation list-stacks --stack-status-filter CREATE_COMPLETE UPDATE_COMPLETE --query "StackSummaries[0].StackName" --output text)
```

If you have completed this workshop under your own account, you can follow these steps to remove all of the workshop resources:

```bash
# Delete CloudFormation Stacks
aws cloudformation delete-stack --stack-name servicenow 
```

Note: you can also head to [Cloudformation](https://console.aws.amazon.com/cloudformation/) and select the stack `servicenow` and click delete stack.
