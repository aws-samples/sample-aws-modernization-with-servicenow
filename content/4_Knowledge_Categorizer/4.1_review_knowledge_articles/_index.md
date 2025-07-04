---
title: "Review Knowledge Articles"
chapter: true
weight: 41
---

## Review knowledge base and gather categories for use in NASK 
First, we need to identify, review, and collect information about 1) the knowledge base and 2) the categories contained in this knowledge base for NASK use. The purpose is to capture a finite list of categories that the Bedrock's Claude LLM can choose from given the text of a KCS knowledge base article. 

1. Type **kb_category.list** into the filter navigator.  

2. Identify which knowledge base category you intend to use from the Parent ID column. For this demonstration we will use: **Knowledge Base: IT** in the **Parent ID** column. 

![KB List](/images/servicenow/knowledge_article/kb_category_it.png) 
 
3. Next, right click on the **Knowledge Base IT** field of a record and click **Show Matching**. 

![KB List](/images/servicenow/knowledge_article/kb_category_matching.png)

4. Make note of the **Parent ID** (which should be a combination of characters and numbers) for **Knowledge Base: IT**. In this workshop the value is **a7e8a78bff0221009b20ffffffffff17**. Store this ID for use later. 

![KB List](/images/servicenow/knowledge_article/kb_category_parent_id_it.png)

5. We also need to add the categories for another knowledge base. To do this, navigate back to the **list of kb_category** and repeat the above steps. For this workshop, click Show Matching once more for **Knowledge Category: Operating Systems** and note the Parent ID : **9d4737cbff0221009b20ffffffffff33**. Store this ID for use later. 

![KB List](/images/servicenow/knowledge_article/kb_category_parent_id_os.png)


## Identify and review knowledge article for use in NASK
In this section we navigate to the knowledge article list to identify an article to use as a test record when we build a NOW Assist Skill kit

1. Type **kb_knowledge.list** into the filter navigator.  

2. Filter the list of knowledge articles so that **class** is **Knowledge**. 
![KB List](/images/servicenow/knowledge_article/kb_search_articles_for_testing.png)

3. Identify the knowledge article(s) you intend to use as test records for NASK.  The ideal candidate record should have **Knowledge base** as a required field. Additionally, Category should be (empty) or incorrect, and has detailed text description in the field **Article body**:

4. Note down the **Number** of the knowledge article you are going to use. For this demonstration, we are using **KB0010005**. Store this number for use later. 
![KB List](/images/servicenow/knowledge_article/kb_article_for_testing.png)