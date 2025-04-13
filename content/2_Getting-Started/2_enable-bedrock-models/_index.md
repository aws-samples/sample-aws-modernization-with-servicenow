---
title: Enable Amazon Bedrock in the Console
description: Enable access to Amazon Bedrock foundation models using the AWS Management Console.
weight: 3
---

# Enable Amazon Bedrock Models in the AWS Console

Before we interact with Amazon Bedrock through the ServiceNow application, we need to enable access to the foundation models (FMs) you'd like to use.

> 📍 **Prerequisite:** You should have already deployed the CloudFormation template and obtained your IAM credentials. If not, go back to the [Getting Started](/content/2_Getting-Started/) section.

---

## Step 1: Sign in to the AWS Console


2. Make sure you're in the **N. Virginia (us-east-1)** region — this is where Amazon Bedrock is fully supported.

---

## Step 2: Open Amazon Bedrock

1. [Click here](https://console.aws.amazon.com/bedrock/home) or within the **Search bar** at the top of the AWS Console, type **"Bedrock"** and click on **Amazon Bedrock** from the dropdown.

2. If prompted to enable the service, click **Enable access**.

---

## Step 3: Enable Foundation Model Access

1. In the left navigation menu, click **Model access**.

![model-access](/images/model-access.png)

2. Click the **Manage model access** button.
3. Select the following models (these are required for this workshop):
   - **Anthropic Claude 3**
   - **Anthropic Claude 3 Sonnet**
   - **Amazon Titan Text G1**
   - **AI21 Labs Jurassic-2**
   - **Mistral 7B**
   - **Amazon Nova**

4. Click **Next**, then **Submit** to confirm model access.
5. Wait for the access to be granted — this may take a few minutes.

---

## Step 4: Verify Access

After a few minutes, return to the **Model access** page and ensure the status for each selected model says **Access granted**.

## Step 5: Setup Cloudwatch Access for Model invocations

1. Make sure to create a log group by navigating to **Amazon CloudWatch -> Log Groups -> Create Log Group**
![cloudwatch-settings](/images/create-cw-settings.png)  

2. In the left navigation menu of **Amazon Bedrock**, click **Settings**

![model-settings](/images/model-settings.png)

3. Toggle to enable the **Model invocation logging** button.
4. Select the following values as shown below:
   - Enable the radio button **Cloudwatch Logs only**
   - Enter value for **Log group name** (in our case we use **bedrock-models**)
   - Enable the radio button **Create and use a new role** 
   - Enter **bedrock-cw-logging-role** as value for **Service role name**

![model-settings](/images/model-cw-settings.png)  

5. Click **Save settings** to enable cloudwatch logging for model invocations.
---

## ✅ You're Ready!

You’ve now enabled the Bedrock models required for the rest of the workshop.

➡️ Continue to [Setting Up the ServiceNow Application](../4_ServiceNow-Setup/) 

