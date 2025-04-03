---
title: "Custom Skills using NASK"
chapter: true
weight: 43
---

# Module 2.3: Custom Skills using NASK 🧩

In this section, you'll create **custom skills** using the **NOW Assist Skill Kit (NASK)** that connect to **Amazon Bedrock**, enabling your workflows and Virtual Agent Designer topics to generate intelligent responses using LLMs.

To proceed, ensure your API credentials have been configured in the earlier **Getting Started** module.

---

## 🔐 Configure Amazon Bedrock Connection

Before building custom skills, you must have an **active connection** to Amazon Bedrock.

### Step 1: Open the Connections & Credential Aliases Page

#### Navigate to:

`All > Connections & Credentials > Connections & Credential Aliases`


![Connection & Credential Aliases](/images/servicenow/now-connection-credentials.png)

---

### Step 2: Open the Amazon Bedrock Record

Select the record for **Amazon Bedrock**.

![Select Bedrock Record](/images/servicenow/now-select-bedrock-connection.png)

---

### Step 3: Create a New Connection & Credential

Click the **Create New Connection & Credential** related link.

![Create New Connection](/images/servicenow/now-create-connection-credential.png)

---

### Step 4: Enter Your AWS Credentials

Fill in the required fields:

- **Region**: e.g., `us-east-1`
- **Access Key ID**
- **Secret Access Key**

Click **Create** to finalize the connection.

![Enter Credentials](/images/servicenow/now-enter-credentials.png)

---

### Step 5: Confirm Successful Configuration

Once completed, you’ll see a success screen like the one below:

![Completed Connection](/images/servicenow/now-completed-connection-credentials.png)

---

## ✅ What’s Next?

You’re now ready to build **custom skills** using NASK that call Amazon Bedrock models. These skills can be used in:

- 🤖 **Virtual Agent Designer** – to power dynamic conversations
- 🧩 **Flow Designer** – for decision trees and business logic
- ✍️ **Custom scripts** – to extend behavior using JavaScript logic

This sets the foundation for a smart, generative AI–driven ServiceNow experience!