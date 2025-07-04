---
title: "Select a LLM model"
chapter: true
weight: 33
---

# Configure LLM Model from Amazon Bedrock

In this section, you’ll configure which **LLM model** to use with Amazon Bedrock for your custom skills.

You may have multiple models available in your Amazon Bedrock account.  
By default, the integration uses Amazon’s **Titan model**, but you can configure the **spoke** to use a different model by updating the **Generative AI Model Config** record.

---

## Create a New Model Configuration

Follow the steps below to register a new model:

1. In the **Filter Navigator**, enter:

```bash
sys_generative_ai_model_config.list
```

![Model Config List](/images/servicenow/now_model_config_list.png)

2. Click the **New** button.

![New Model Configuration](/images/servicenow/now_model_configuration.png)

3. Enter the following values:
- Select the checkbox for **Active**
- Set **Model** value to **anthropic.claude-3-sonnet-20240229-v1:0** _(This is the ID for Claude 3 Sonnet by Anthropic. You can find model IDs under **Amazon Bedrock > Base Models**.)_
- Set **Provider** value by selecting **Amazon Bedrock**
- Set **Max Tokens** value to **32768**
- Set **Connection and Credential Alias** value by selecting **sn_amz_bedrock_spk.Amazon_Bedrock** created in previous step.

4. Click **Submit** to save the record.

![Updated Model Config List](/images/servicenow/now_updated_model_config_list.png)

✅ Your instance is now configured to use **Claude 3 Sonnet** as the default model for Bedrock-based AI tasks.

---

## 🔁 Map the Model to a Custom Skill

> 📝 **Note:** Complete this step *after* you've built the custom skill.

1. In the **Filter Navigator**, enter:

```bash
sys_generative_ai_config.list
```

2. Locate and open the record for your custom skill that uses **Amazon Bedrock** as the provider.

3. Confirm the **Definition** field is set to the appropriate **OneExtend Capability Definition**.

4. In the **Model** field, select or enter the same model ID used earlier:

```bash
anthropic.claude-3-sonnet-20240229-v1:0
```

🎉 Done! Your skill is now powered by **Claude 3 Sonnet** via Amazon Bedrock.

---

## Pro Tips

- You can test and compare multiple models by creating additional entries in the **Model Config** table.
- Don’t forget to monitor token usage, especially with larger models.
- If something isn’t working, double-check the connection alias and model ID spelling.

Need help? Check out the [Amazon Bedrock documentation](https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html) for model details.
