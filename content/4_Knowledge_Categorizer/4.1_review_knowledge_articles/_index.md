---
title: "Review Knowledge Articles"
chapter: true
weight: 41
---

# 🔍 Review Knowledge Articles

## 🔐 Configure API Credentials for Amazon Bedrock

In this section, you'll configure the **API credentials** you created in the **Getting Started** section to enable Amazon Bedrock integration in your custom workflows and Virtual Agent Designer topics.

To use Amazon Bedrock as the LLM provider for **Generative AI Controller** features, an active connection must be configured within your ServiceNow environment.

---

## Step-by-Step Setup

### 1. Open the Connections Page

#### Click on:

`All > Connections & Credentials > Connections & Credential Aliases`

![Connections & Credential Aliases](/images/servicenow/now-connection-credentials.png)

---

### 2. Open the Amazon Bedrock Record

Locate and click on the record for **Amazon Bedrock**.

![Amazon Bedrock Record](/images/servicenow/now-select-bedrock-connection.png)

---

### 3. Create a New Connection

Click the **Create New Connection & Credential** related link.

![Create New Connection](/images/servicenow/now-create-connection-credential.png)

---

### 4. Enter Your AWS Details

Provide the following values:

- **Region**: e.g., `us-east-1`
- **AWS AccessKeyId**
- **AWS SecretAccessKey**

Then click **Create**.

![Enter AWS Credentials](/images/servicenow/now-enter-credentials.png)

---

### 5. Verify Success

After successful setup, you’ll see the confirmation screen:

![Connection Complete](/images/servicenow/now-completed-connection-credentials.png)

---

## ✅ What’s Next?

You're now ready to use **Amazon Bedrock** as your LLM provider for:

- **Flow Designer**
- **Virtual Agent Designer**
- **Custom scripts**

This enables you to build powerful generative AI workflows directly in ServiceNow.
