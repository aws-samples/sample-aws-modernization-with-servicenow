---
title: "Build Subflow for Knowledge Categories"
chapter: true
weight: 42
---

# Module 2.1: Build Subflow to Retrieve Knowledge Categories 🛠️

In this section, you’ll build a **Subflow** that gathers knowledge categories used to classify KB articles — powered by a Large Language Model (LLM) via **Amazon Bedrock**.

---

## 🧠 Configure the Model for Article Categorization

You may have multiple models available through Amazon Bedrock. By default, the spoke uses Amazon’s **Titan** model, but we’ll configure it to use **Anthropic Claude 3 Sonnet** instead.

---

## 🔧 Create a New Generative AI Model Config Record

### Step 1: Open the Generative AI Model Config Table

In the ServiceNow navigation bar, enter:

```bash
sys_generative_ai_model_config.list
```

![Model Config Table](/images/servicenow/now_model_config_list.png)

---

### Step 2: Create a New Configuration

Click the **New** button.

![New Configuration](/images/servicenow/now_model_configuration.png)

---

### Step 3: Fill in the Configuration Fields

#### Model:

```bash
anthropic.claude-3-sonnet-20240229-v1:0
```

_(You can find the model ID under **Amazon Bedrock > Base Models**.)_

#### Provider:
  
  ```bash
  Amazon Bedrock
  ```

#### Connection and Credential Alias:

Select the alias created in the previous step.
(Example: `sn_amz_bedrock_spk.Amazon_Bedrock`)

#### Max Tokens:

```bash
32768
```

Click **Submit** to save the model config.

![Updated Model Config](/images/servicenow/now_updated_model_config_list.png)

---

✅ The Amazon Bedrock spoke is now configured to use **Claude 3 Sonnet** for LLM interactions.

---

## 🔁 Map the Model to a Custom Skill

> 📝 **Note for Sunil**: Complete this step after the custom skill is built.

### Step 1: Open the Generative AI Config Table

In the navigation bar, enter:

```bash
sys_generative_ai_config.list
```

### Step 2: Map the Model

- Search for the skill you created that uses **Amazon Bedrock**.
- Open the skill record.
- Ensure the **Definition** field points to the correct **OneExtend Capability Definition** (e.g., the name of your skill).
- Set the **Model** field to:

  ```bash
  anthropic.claude-3-sonnet-20240229-v1:0
  ```

---

🎉 You’ve now linked your Subflow and custom skill to a specific Bedrock model. This step enables accurate, automated knowledge categorization with generative AI.
