---
title: "Custom Skills using NASK"
chapter: true
weight: 43
---

# 🧩 Custom Skills using NASK 

## Build the custom skill using NOW Assist Skill Kit

In this section, you'll create **custom skills** using the **NOW Assist Skill Kit (NASK)** that connect to **Amazon Bedrock**, enabling your workflows and Virtual Agent Designer topics to generate intelligent responses using LLMs.

---
1. Navigate to All > Now Assist Skill Kit > Home from the filter navigator. 
![KB Subflow](/images/servicenow/custom_skill/kb_nav_nask_home.png)

2. Click Create new skill. 
![KB Subflow](/images/servicenow/custom_skill/kb_nask_home.png)

3. Name the skill IT Knowledge Categorizer. In this lab, we will be using the Amazon Bedrock service using Anthropic Claude LLM to complete our task, so ensure the Default provider and Provider API values are both set to Amazon Bedrock. Click **Create skill and go to prompt editor**. This will create the skill.

![KB Subflow](/images/servicenow/custom_skill/kb_create_skill.png)

4. Click on **Skill inputs** tab and add a new skill input by clicking the **plus icon** next to it. This is where we add the reference to a knowledge article to use within the prompt.  
![KB Subflow](/images/servicenow/custom_skill/kb_skill_input.png)

5. Populate the skill input form with (screenshot below): 
<ul>
    <li>Datatype: Record</li>  
    <li>Table name: kb_knowledge</li>
    <li>Name: Knowledge</li>
    <li>Choose test record: KB0010005 (the number of the knowledge article we took note of in phase 2).</li>
</ul>
Once complete, click Add skill input.

![KB Subflow](/images/servicenow/custom_skill/kb_fill_skill_input.png)

6. Click on **Tool editor** tab and click the plus icon to add the tool node.
![KB Subflow](/images/servicenow/custom_skill/kb_nav_tool_editor.png)

7. Select the **Tool node** and click the **Add** button
![KB Subflow](/images/servicenow/custom_skill/kb_tool_editor_add_node.png)

8. Populate the form as seen below. Note the lack of spaces in the Name, and the resource is the name of our published Subflow, i.e., Retrieve Knowledge Base Categories. Scroll down and click the **Add** button
![KB Subflow](/images/servicenow/custom_skill/kb_tool_editor_fill_subflow.png)
![KB Subflow](/images/servicenow/custom_skill/kb_tool_editor_add_subflow.png)

9. Click on **Prompt editor** tab and optionally click the Pencil Icon next to the prompt name to rename the prompt. 
In the prompt field, copy and paste the text below: 

        You are tasked with classifying input text into one of the following categories:  

        Each category represents a distinct type of content. Based on the content of the input text, 
        identify which category best describes it. Ensure that the categorization is based on clear 
        patterns or keywords in the text that match the defining characteristics of each category. 

        Instructions:
        Review the input text. Choose the category that best matches the content. If the input text 
        could fit into more than one category, choose the most appropriate one based on the primary 
        theme. 

        Example Inputs:
        Input: "Title: Can't login to my windows laptop." 
        Category: Windows

        Input: "Issue: Zoom keeps crashing when I start a meeting"
        Category: Zoom 

        Now, classify the following Knowledge Base Article:

        Title: 
        Short Description:
        Article Body:

        Return only the category. No other text. 
        
10. Click in the prompt field after the string “...one of the following categories:”. Click on Insert inputs, RetrieveKnowledgeBaseCategories > Compiled IT KB Categories. 
![KB Subflow](/images/servicenow/custom_skill/kb_prompt_editor_fill_kbcategories.png)

11. Repeat the above insert inputs process to add corresponding text fields to the following fields defined in the prompt:
- Short Description:
- Article Body:

Note: because we are using Knowledge Articles, when inserting inputs, ensure you select Kknowledge > short description and so on. 

12. The completed process prompt should look like the screenshot below. Notice that the Knowledge Base article Short Description field is inserted into the Title section: 

        You are tasked with classifying input text into one of the following categories:  {{RetrieveKnowledgeBaseCategories.compiled_it_kb_categories}} 

        Each category represents a distinct type of content. Based on the content of the input text, 
        identify which category best describes it. Ensure that the categorization is based on clear 
        patterns or keywords in the text that match the defining characteristics of each category. 

        Instructions:
        Review the input text. Choose the category that best matches the content. If the input text 
        could fit into more than one category, choose the most appropriate one based on the primary 
        theme. 

        Example Inputs:
        Input: "Title: Can't login to my windows laptop." 
        Category: Windows

        Input: "Issue: Zoom keeps crashing when I start a meeting"
        Category: Zoom 

        Now, classify the following Knowledge Base Article:

        Title:  {{knowledge.short_description}} 
        Short Description: {{knowledge.short_description}} 
        Article Body: {{knowledge.text}} 

        Return only the category. No other text. 

13. Click save.

