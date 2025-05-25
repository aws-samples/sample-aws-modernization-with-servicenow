---
title: "Enhancing enterprise workflows with ServiceNow and Amazon Bedrock" # MODIFY THIS TITLE IF APPLICABLE
chapter: true
weight: 3
---

# WELCOME! <!-- MODIFY THIS HEADING -->

## Enhancing enterprise workflows with ServiceNow and Amazon Bedrock <!-- MODIFY THIS SUBHEADING -->

In this workshop, you'll learn how to leverage ServiceNow's NOW Assist Skill Kit (NASK) to process unstructured Knowledge KB article data and allowing the Amazon Bedrock (NOVA model) to intelligently categorize the content by selecting from predefined categories within our Knowledge Base…effectively automating the categorization of KB articles at massive scale

---------------------------------------------------------------------

## Workshop structure Agenda <!-- MODIFY THIS SUBHEADING -->
This workshop is divided into sections listed below. Plan on 3 hours to complete the full workshop. <br>

1. **Introduction – (10 minutes)**
2. **Prerequisites – (20 minutes)**
3. **Enable Bedrock model and cloudwatch logging – (20 minutes)**
4. **Configure ServiceNow Gen AI Controller – (30 minutes)**
5. **Build subflow – (30 minutes)**
6. **Build NOW Assist custom skill – (30 minutes)**
7. **Deploy and Activate custom skill – (10 minutes)**
8. **Testing & Verification – (20 minutes)**
9. **CleanUp – (30 minutes)**

---------------------------------------------------------------------

## Learning Objectives <!-- MODIFY THIS SUBHEADING -->
- Learn how ServiceNow workflows can pass contextual data to Bedrock LLMs, which generate outputs—such as summaries, insights, and recommended actions—that are directly actionable within the ServiceNow platform.
- Custom AI skills built with the Now Assist Skill Kit integrate natively into ServiceNow applications, such as Virtual Agent, IT Service Management, and Customer Service Management, delivering a unified and intuitive user experience.
- Using the Now Assist Skill Kit, developers can easily integrate Amazon Bedrock’s large language models (LLMs) into their workflows. 

---------------------------------------------------------------------

## Who should attend <!-- MODIFY THIS SUBHEADING -->
- Solutions Architects
- ServiceNow practioners
- Enterprise Cloud Architects
- AI Technologists
- Developers
- Technical leaders
- Program Managers
- Business Analysts

---------------------------------------------------------------------

## Background Knowledge for the Workshop <!-- MODIFY THIS SUBHEADING -->
- Basic knowledge on AWS
- Generative AI concepts
- Basic Gen AI Prompting knowledge
- ServiceNow knowledge on building Subflows
- ServiceNow NOW Assist Skill kits knowledge

---------------------------------------------------------------------
{{% notice warning %}}
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various AWS services can be architected to build a solution while demonstrating best practices along the way. These examples are not intended for use in production environments.
{{% /notice %}}

---------------------------------------------------------------------
### Introduction <!-- MODIFY THIS HEADING -->
Before we dive in, let's go through a refresher on the core concepts explored in this workshop.