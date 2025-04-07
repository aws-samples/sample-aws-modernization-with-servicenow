---
title: "See Custom Skill in Action"
chapter: true
weight: 48
---

# 🎯 See Custom Skill in Action 

## 🧪 Run the Skill on a Single Knowledge Base (KB) Article

In this section, you'll run your **custom skill** on a single KB article using the **Amazon Bedrock integration**.

---
1. Type kb_knowledge.list into the filter navigator. Find the knowledge article you wish to run your custom skill on and open the record. In our case we open this article KB0010005. Notice the **Category** field is empty.
![KB deply skill](/images/servicenow/skill_action/kb_nav_knowledge_article.png)

2. Click the UI Action **IT Knowledge Categorizer** we created – you may have named it something else. 

3. Woohoo! Your KB article should be automatically categorized! 

![KB deply skill](/images/servicenow/skill_action/kb_knowledge_article_updated.png)

4. Navigate to the article KB0010005 and verify the **Category**, it should have been changed to "Mac OS X"
![KB deply skill](/images/servicenow/skill_action/kb_knowledge_article_updated_value.png)