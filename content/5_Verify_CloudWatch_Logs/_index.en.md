---
title: "Module 3 - Verify results in AWS"
chapter: true
weight: 50
---

## Verify CloudWatch Logs 
In this section, you'll verify that the action taken upon execution of **Custom skill in Action** in previous module actually  invocked the **Amazon Bedrock API** calling **Anthropic Claude Sonnet 3**.

---
1. [Click here](https://console.aws.amazon.com/cloudwatch/home) or within the **Search bar** at the top of the AWS Console, type **"Cloudwatch"** and click on **CloudWatch** from the dropdown.

2. In the left navigation menu, click **Log groups**.
![log-groups](/images/cw-log-groups.png)

3. Within the **Search bar** type the log-group name **bedrock-models** and click on the name. 
![log-group-name](/images/cw-log-group-name.png)

4. Click on the **Log Stream** named **aws/bedrock/modelinvocations**
![log-stream-name](/images/cw-log-stream-name.png)

5. Expand the **Log events** and you should see the **Model Invocation Log**. Verify the following values,
- **modelId** : **anthropic.claude-3-sonnet-20240229-v1:0**
- In the **messages->content-text** the prompt that was sent from ServiceNow thru our custom skill

![bedrock-api-invocation-log](/images/cw-bedrock-api-invocation.png)

5. That completes the verification of the invocation of **Amazon Bedrock API** calling the **Anthropic's Claude Sonnet 3 model** from **Custom skill set** we build using ServiceNow's **NOW Assist Skill Kit**.