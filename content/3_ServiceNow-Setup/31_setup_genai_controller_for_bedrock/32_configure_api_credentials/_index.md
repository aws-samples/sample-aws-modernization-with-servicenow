---
title: "Setup API Credentials"
chapter: true
weight: 32
---

# Configure API Credentials for Amazon Bedrock in ServiceNow

In this section, you will configure your API credentials (created in the **Getting Started** section) to enable the use of **Amazon Bedrock** in custom workflows and Virtual Agent Designer topics.

To use Amazon Bedrock as your LLM provider for Generative AI Controller capabilities, you must have an **active connection** configured.

---

## Steps

1. In your ServiceNow instance, navigate to:  
   **All > Connections & Credentials > Connections & Credential Aliases**

   ![Navigation to Connection & Credentials](/images/servicenow/now-connection-credentials.png)

2. Open the record for **Amazon Bedrock**.

   ![Select Bedrock Connection](/images/servicenow/now-select-bedrock-connection.png)

3. Click the **Create New Connection & Credential** related link.

   ![Create New Connection](/images/servicenow/now-create-connection-credential.png)

4. Fill in the required fields:
   - **Region** (e.g., `us-east-1`)
   - **AWS AccessKeyId** (value copied from Prerequisites section)
   - **AWS SecretAccessKey** (value copied from Prerequisites section)

   Then click **Create**.

   ![Enter Bedrock Credentials](/images/servicenow/now-enter-credentials.png)

5. After successful completion, you should see a confirmation screen like this:

   ![Connection Complete](/images/servicenow/now-completed-connection-credentials.png)

---

You’re now ready to use **Amazon Bedrock** as the LLM provider for the Generative AI Controller within:

- **Flow Designer**
- **Virtual Agent Designer**
- **Custom scripts**

This enables powerful generative AI experiences within your ServiceNow workflows.