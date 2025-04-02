---
title: "Select a model for Amazon Bedrock"
chapter: true
weight: 12
---

## Select a model for Amazon Bedrock ##

In this section you are going to configure which LLM Model to use with Amazon Bedrock for custom skills. 
</br>

You may have multiple models configured to use with Amazon Bedrock. 

</br>
By default, the settings use Amazon's Titan model, but you can configure the spoke to use a different model by changing the Generative AI Model Config record.
</br>
</br>
In the filter navigator, navigate to the Generative AI Model Config table by entering "<b>sys_generative_ai_model_config.list</b>".

![My Logo](/images/servicenow/now_model_config_list.png)

Click <b>"New"</b> button
</br>
![My Logo](/images/servicenow/now_model_configuration.png)
</br>
Enter the following values
<ul>
<li>In the <b>Model</b> field, enter the ID of the model that you want to use. we are using <b>anthropic.claude-3-sonnet-20240229-v1:0</b> this value of anthropic claude sonnet model
You can find the model ID on the Foundation models > Base models page on Amazon Bedrock.</li>
<li>In the <b>Provider</b> field, select <b>Amazon Bedrock</b></li>
<li>In the <b>Connection And Credential Alias</b> field, select <b>Amazon Bedrock connection</b> we created in the previous step</li> Value should be something like this "sn_amz_bedrock_spk.Amazon_Bedrock"
<li>In the <b>Max Tokens</b> field, update the value to <b>32768</b> 
<li> Click the <b>"Submit"</b> button.
</ul>

![My Logo](/images/servicenow/now_updated_model_config_list.png)

</br>
Now, the Amazon Bedrock spoke is configured to use Claude 3 Sonnet by Anthropic.

### SUNIL :: Do this step after you build the skill to point to the model ### 

Map the chosen model to a custom skill.

In the filter navigator, go to the Generative AI Config table by entering sys_generative_ai_config.list.
Search for the custom skill you've created that uses Amazon Bedrock as the service provider, and open the record.
The Definition should be OneExtend Capability Definition: <Name of Skill>.
Set the Model field to the model ID you entered in step 3.