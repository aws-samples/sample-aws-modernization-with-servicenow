---
title: "See Custom Skill in Action"
chapter: true
weight: 48
---

# See Custom Skill in Action 

## Run the custom skill on a Single Knowledge Base (KB) Article

In this section, you'll run your **custom skill** on a single KB article using the **Amazon Bedrock integration**.

---
1. Type kb_knowledge.list into the filter navigator. Find the knowledge article you wish to run your custom skill on and open the record. In our case we open this article KB0010005. Notice the **Category** field is empty.
![KB article](/images/servicenow/skill_action/kb_nav_knowledge_article.png)

2. Click the UI Action **IT Knowledge Categorizer** we created – you may have named it something else. 

3. Woohoo! Your KB article should be automatically categorized! 

![KB action](/images/servicenow/skill_action/kb_knowledge_article_updated.png)

4. Navigate to the article KB0010005 and verify the **Category**, it should have been changed to "Mac OS X"
![KB category updated](/images/servicenow/skill_action/kb_knowledge_article_updated_value.png)

## Run the custom skill on a list of Knowledge Base (KB) Article

In this section, you'll run your **custom skill** on a list of KB article using the **Amazon Bedrock integration**.

---
1. Type kb_knowledge.list into the filter navigator. 

2. Using the list filter, select **Category (kb_category)** and leave the value blank. Then click Run to get a list of only KB articles which has **(empty)** value in the **Category**. 
![KB list](/images/servicenow/skill_action/kb_knowledge_article_list_null_category.png)

3. Select the articles you wish to run the custom skill on. Click the UI action **IT Knowledge Categorizer** we just created. 
![KB list selected](/images/servicenow/skill_action/kb_knowledge_article_list_null_category_selected.png)

4. Congrats! Your list of KCS KB articles should be automatically categorized! 
![KB list updated](/images/servicenow/skill_action/kb_knowledge_article_list_null_category_updated.png)