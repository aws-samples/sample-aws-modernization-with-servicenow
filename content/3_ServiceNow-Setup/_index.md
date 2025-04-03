---
title: Module 1 - Setting Up the ServiceNow Now Assist
description: Configure the ServiceNow app to integrate with Amazon Bedrock and begin the modernization workflow.
weight: 20
---

# Set Up the ServiceNow Now Assist App

Now that you’ve enabled the required Amazon Bedrock models, it’s time to configure the ServiceNow application that interacts with Bedrock.

This section walks you through setting up the ServiceNow NOW Assist platform and securely configuring it to call Amazon Bedrock APIs.

## Lab Structure ##
These are the steps we will follow to build, deploy and activate a custom skill with NOW Assist Skill Kit (NASK) to implement custom Generative AI action that will automatically categorize the knowledge article.  <br>
NASK has been designed to easily manage and integrate new skills into the ServiceNow platform via a UI Action and soon into the Now Assist Panel. With NASK you define the input data, leverage tools to process the data, activate the new skill, and deploy it to the platform

<ul>
    <li> Phase 1 – Review knowledge base and gather which categories we want the Now LLM to use to categorize KCS KB article text.  </li>
    <li> Phase 2 – Identify and review a specific KCS KB article that we can use as a test record for the custom skill.  </li>
    <li> Phase 3 – Using data from Phase 1, build a Subflow that automatically gathers the categories we want the Now LLM to use.  </li>
    <li> Phase 4 – Build the custom skill using NASK. </li>
    <li> Phase 5 – Testing the custom skill. </li>
    <li> Phase 6 – Deploying the custom skill. </li>
    <li> Phase 7 – Activating the custom skill. </li>
    <li> Phase 8 – See custom skill in action, on a single KCS KB article. </li>
    <li> Phase 9 – See custom skill in action, on a list of KCS KB article. </li>
</ul>

Navigate to your ServiceNow instance, 
![My Logo](/images/servicenow/now-login.png)
enter "User name" and "Password" and click the <b> "Log in" </b> button

![My Logo](/images/servicenow/now-home.png)