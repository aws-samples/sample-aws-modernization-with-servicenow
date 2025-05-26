---
title: "NOW Assist Skill kit" # MODIFY THIS TITLE
chapter: true
weight: 2 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES IF APPLICABLE
---

# NOW Assist skill kit workflow <!-- MODIFY THIS HEADING TO REFLECT THE PROBLEM THE WORKSHOP IS ADDRESSING -->

ServiceNow is a platform and hosts number of integrations with external systems. Today we are going to talk about the integration with Bedrock that was launched last year and how it helps drive gen ai use cases. 

![NOW Assist skill kit diagram](/images/servicenow/now-how-genai-works-at-now.png)

Here, the first thing you need to understand is where you are going to collect data from, that could be from the ServiceNow workflows, or Records within ServiceNow itself, or Integrations that you have out to external systems, or directly from the CMDB or providing some contextual information from the code. 

Next, you build some tools to provide additional context data for the use case, it could be Subflow or Flow Action, web search or any other means which collects data for the use case. 

Once, you have the data collected, you write out a prompt in NOW Assist skill kit to combine the inputs you collected. This is nothing but a set of instructions you have to tell a LLM as to what you have to be done with this data, like passing in a series of log messages and asking LLM to go out analyze this log data to discover any trends that I should be aware of or any anomalies that I should be aware of, 
Or passing in a survey result and asking the LLM to determine what the sentiment of the user was when they filled out the survey.

Once you have the data then you send that off to the LLM (in this case Amazon Bedrock and the LLM you selected) to have it perform the required action. So once LLM returns the response back to your ServiceNow workflow, then you can take action on this data and display the results as applicable to your use case. 

---------------------------------------------------------------------
Here you can see the guidance to work with NOW Assist Skill kit, which we are going to walk-thru in this workshop in following sections.

![NOW Assist skill kit diagram](/images/servicenow/now-assist-skill-kit-intro.png)

---------------------------------------------------------------------

## Now, we'll finally go to our first Lab and put some of the knowledge we've seen here into practice
