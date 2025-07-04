---
title: "Test the Custom Skills"
chapter: true
weight: 45
---


## Testing the custom skill

In this section, you'll test the **custom skills** within the **NOW Assist Skill Kit (NASK)** application that we created in the previous module.

---
1. Scroll down to the **Test prompt** section, and click **Run tests**. 
![KB Subflow](/images/servicenow/custom_skill/kb_test_custom_skill.png)

2. Verify that the Anthropic Claude LLM's response is correct. If you desire, you can iterate upon the provided prompt. However, for our purposes, the skill correctly categorizes the Knowledge article accurately.  
![KB Subflow](/images/servicenow/custom_skill/kb_test_verify_output.png)

3. To verify if information from your skill inputs is being brought in correctly, click on the tab named **Grounded prompt**. You will see the input that was delivered to the LLM, including the categories and knowledge article text. 
![KB Subflow](/images/servicenow/custom_skill/kb_test_verify_grounded_prompt.png)

4. Once content with the output of your skill, click **Finalize prompt**
![KB Subflow](/images/servicenow/custom_skill/kb_finalize_prompt.png)

