---
title: Module 1 - Setting Up the ServiceNow Now Assist
description: Configure the ServiceNow app to integrate with Amazon Bedrock and begin the modernization workflow.
weight: 30
---

# Set Up the ServiceNow Now Assist App

Now that you’ve enabled the required Amazon Bedrock models, it’s time to configure the ServiceNow application that interacts with Bedrock.

This section walks you through setting up the **ServiceNow NOW Assist platform** and securely configuring it to call Amazon Bedrock APIs.

---

## Lab Structure

In this lab, we’ll use the **NOW Assist Skill Kit (NASK)** to build, deploy, and activate a custom Generative AI skill that automatically categorizes knowledge articles.

**What is NASK?**  
NASK helps you define input data, process it using AI tools, and deploy the resulting custom skills through UI Actions—soon also available in the Now Assist Panel.

We’ll follow these 9 steps:

1. **Phase 1** – Review the knowledge base and gather categories for the Now LLM to use when classifying KCS KB article text.
2. **Phase 2** – Identify and review a specific KCS KB article to use as a test record.
3. **Phase 3** – Build a Subflow to gather category data automatically.
4. **Phase 4** – Create the custom skill using NASK.
5. **Phase 5** – Test the custom skill.
6. **Phase 6** – Deploy the custom skill.
7. **Phase 7** – Activate the custom skill.
8. **Phase 8** – Run the skill on a single KCS KB article.
9. **Phase 9** – Run the skill on a list of KCS KB articles.

---

## Log In to ServiceNow

Follow the steps below to access your ServiceNow instance:

1. Navigate to your ServiceNow instance in your browser.  
![Login Page](/images/servicenow/now-login.png)

2. Enter your **User name** and **Password**.

3. Click the **Log in** button.

4. After logging in successfully, you should see the **ServiceNow Home Dashboard**.  
![ServiceNow Home](/images/servicenow/now-home.png)