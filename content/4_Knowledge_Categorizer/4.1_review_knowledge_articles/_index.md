---
title: "Review Knowledge Articles"
chapter: true
weight: 41
---

# Review Knowledge Articles

## Review knowledge base and gather categories for use in NASK 
First, we need to identify, review, and collect information about 1) the knowledge base and 2) the categories contained in this knowledge base for NASK use. The purpose is to capture a finite list of categories that the Bedrock's Claude LLM can choose from given the text of a KCS knowledge base article. 

1. Type <b>kb_category.list</b> into the filter navigator.  

2. Identify and review which knowledge base you intend to use. For this demonstration we will use: <b>Knowledge Base: IT</b> in the Parent ID column. 

![KB List](/images/servicenow/knowledge_article/kb_category_it.png)


3. Identify which knowledge base you intend to use in the Parent ID column. For this demonstration I will use: <b>Knowledge Base: IT</b>. 
 
4. Next, right click on the <b>Knowledge Base IT</b> field of a record and click <b>Show Matching</b>. 

![KB List](/images/servicenow/knowledge_article/kb_category_matching.png)

5. Make note of the Parent ID (which should be a combination of characters and numbers) after clicking <b>Show Matching</b>. Using the lab example, the Parent ID for <b>Knowledge Base: IT</b> is <b>a7e8a78bff0221009b20ffffffffff17</b>. Store this ID for use later. 

![KB List](/images/servicenow/knowledge_article/kb_category_parent_id_it.png)

6. We also need to add the categories for another knowledge base. To do this, I go to the list of kb_category and repeat the above steps. For this lab, click Show Matching once more and note the Parent ID for <b>Knowledge Category: Operating Systems: 9d4737cbff0221009b20ffffffffff33</b>. Store this ID for use later. 

![KB List](/images/servicenow/knowledge_article/kb_category_parent_id_os.png)


## Identify and review KCS knowledge article for use in NASK

1. Type kb_knowledge.list into the filter navigator.  

2. Filter the list of knowledge articles so that <b>class</b> is <b>Knowledge</b>. 
![KB List](/images/servicenow/knowledge_article/kb_search_articles_for_testing.png)

3. Identify the knowledge article(s) you intend to use as test records for NASK.  The ideal candidate record should have Knowledge base as a required field. Additionally, Category should be (empty) or incorrect, and detailed text description in the field <b>Article body</b>:

4. Note down the number of the knowledge article you are using. For this demonstration, we are using KB0010005. Store this number for use later. 
![KB List](/images/servicenow/knowledge_article/kb_article_for_testing.png)