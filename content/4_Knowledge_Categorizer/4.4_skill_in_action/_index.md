---
title: "See Custom Skill in Action"
chapter: true
weight: 45
---

# Module 2.4: See Custom Skill in Action 🎯

## 🧪 Run the Skill on a Single Knowledge Base (KB) Article

In this section, you'll run your **custom skill** on a single KB article using the **Amazon Bedrock integration**.

---

## 🧠 Reconfirm Model Configuration (If Needed)

You may have multiple models available through Amazon Bedrock. By default, the spoke uses Amazon’s **Titan model**, but you can configure it to use **Anthropic Claude 3 Sonnet** instead.

---

## ⚙️ Update the Model Configuration

### Step 1: Open the Model Config Table

Enter the following in the navigation search bar:

```bash
sys_generative_ai_model_config.list
```

![Model Config List](/images/servicenow/now_model_config_list.png)

---

### Step 2: Create a New Model Configuration

Click the **New** button.

![New Model Configuration](/images/servicenow/now_model_configuration.png)

---

### Step 3: Enter the Configuration Details

#### Model:

  ```bash
  anthropic.claude-3-sonnet-20240229-v1:0
  ```

  _(Model ID for Claude 3 Sonnet. You can find others under **Amazon Bedrock > Base Models**.)_

#### Provider:

```bash
Amazon Bedrock
```

### Connection and Credential Alias:

Select the alias from the previous step  
_(e.g., `sn_amz_bedrock_spk.Amazon_Bedrock`)_

### Max Tokens:

```bash
32768
```

Click **Submit** to save the configuration.

![Updated Model Config](/images/servicenow/now_updated_model_config_list.png)

---

✅ The Amazon Bedrock spoke is now configured to use **Claude 3 Sonnet by Anthropic**.

---

## 🔁 Map the Model to Your Custom Skill

> 📝 **Note for Sunil:** Complete this step *after* building the skill.

### Step 1: Open the Generative AI Config Table

Enter the following in the navigation bar:

```bash
sys_generative_ai_config.list
```


### Step 2: Map the Model

- Search for your **custom skill** that uses Amazon Bedrock as the provider
- Open the skill record
- Set the **Definition** field to your **OneExtend Capability Definition** (e.g., skill name)
- In the **Model** field, enter the same model ID used earlier:  

 ```bash
anthropic.claude-3-sonnet-20240229-v1:0
```

---

🚀 Your custom skill is now ready to run on a **single KB article**. In the next module, you'll see how to scale this to **multiple articles at once**.