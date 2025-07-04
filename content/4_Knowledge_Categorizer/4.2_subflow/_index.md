---
title: "Build Subflow for Knowledge Categories"
chapter: true
weight: 42
---

## Build a Subflow to collect relevant Knowledge Base categories 

In this section, you’ll build a **Subflow** that gathers knowledge categories used to classify KB articles.

---
1. Navigate to **All > Workflow Studio**
![KB Subflow](/images/servicenow/subflow/kb_nav_workflow_editor.png)

2. Click **New > Subflow**
![KB Subflow](/images/servicenow/subflow/kb_new_subflow.png)

3. Set values: **Subflow name**: 'Retrieve Knowledge Base Categories'. Set the **Application** to: 'Global'. Click, **Build subflow** 
![KB Subflow](/images/servicenow/subflow/kb_build_subflow.png)

4. Click **Select to create the inputs & outputs of your Subflow** under **INPUTS & OUTPUTS** section. Click the plus **(+)** icon next to **Outputs**
![KB Subflow](/images/servicenow/subflow/kb_subflow_output.png)

5. Set the **Label** of your output as **Compiled IT KB Categories** value, then click **Done**
![KB Subflow](/images/servicenow/subflow/kb_subflow_set_output.png)

6. Open the More Actions menu in the upper right corner of the screen as denoted by the three dots **(…)**, then click **Flow Variables**
![KB Subflow](/images/servicenow/subflow/kb_subflow_flow_variables.png)

7. Click the plus **(+)** icon to add a new flow variable. Set the **Label** to **Compiled IT KB Categories** as a Type of **String**, then click **Save**
![KB Subflow](/images/servicenow/subflow/kb_subflow_set_flow_variables.png)

8. Next under **ACTIONS** section, click **Add an Action, Flow Logic, or Subflow** and select **Action**. Then type **Look up records** in the search bar and click on **ServiceNow Core -> Look Up Records** action. 
![KB Subflow](/images/servicenow/subflow/kb_subflow_action_lookup_records.png)

9. Populate the **Action Inputs** as seen below, and click **Done** (we are populating with the Parent ID’s we collected in **Module 4.1**): 
<ul>
  <li>Table: Knowledge Category [kb_category]</li>
  <li>Conditions: Parent ID is a7e8a78bff0221009b20ffffffffff17` OR Parent ID is `9d4737cbff0221009b20ffffffffff33`.</li>
</ul>

![KB Subflow](/images/servicenow/subflow/kb_subflow_add_action_lookup_records.png)

10. Next under **ACTIONS** section, click on **Flow Logic**, then select **For Each**. 
![KB Subflow](/images/servicenow/subflow/kb_subflow_flow_logic_foreach.png)

11. Drag and drop the **Knowledge Category Records** data pill (from right panel) into the **Items** field, then click **Done**. 
![KB Subflow](/images/servicenow/subflow/kb_subflow_flow_logic_category_records.png)

12. Click the small plus **(+)** icon under the **For Each item in** loop and select **Flow Logic** again. This time, click **Set Flow Variables**. 
![KB Subflow](/images/servicenow/subflow/kb_subflow_flow_logic_flow_variables.png)

13. Click the plus **(+)** icon, then set the flow variable **Name** to **Compiled IT KB Categories** from the dropdown list. Click the script icon next to the text box **Scripted (Exapnd to edit)** that appears to make a script field appear. Copy and paste the below code into this script area: 

```
var result = fd_data.flow_var.compiled_it_kb_categories  

+ fd_data._2__for_each.item.label 

+ "\n";  

return result;
```
![KB Subflow](/images/servicenow/subflow/kb_subflow_flow_logic_flow_variables_script.png)

14. Click **Done** 

15. Next under **ACTIONS** section, add another **Flow Logic** item, and click **Assign Subflow Outputs** 
![KB Subflow](/images/servicenow/subflow/kb_subflow_flow_logic_select_subflow_output.png)

16. Click the plus **(+)** icon, then Set the Subflow output variable **Name** to be **Compiled IT KB Categories** from dropdown list. Drag and drop the **flow variable** with the same name ((from right panel)) into the **Data** field. Click **Done**.
![KB Subflow](/images/servicenow/subflow/kb_subflow_flow_logic_set_subflow_output.png)

17. Click **Save** 
18. Next, click **Test** and in the module that appears next, click **Run Test** again.
![KB Subflow](/images/servicenow/subflow/kb_subflow_flow_test.png)

![KB Subflow](/images/servicenow/subflow/kb_subflow_flow_run_test.png)

![KB Subflow](/images/servicenow/subflow/kb_subflow_flow_test_finished.png)

18. Once test finished. Click on the link **Your test has finished running. View the subflow execution details.**

18. Click on the **Subflow Inputs & Outputs** and then **Subflow Output** to review the action that took place. Check the **RUNTIME VALUE** to see the list of **IT Knowledge Base Categories** that were returned. 
![KB Subflow](/images/servicenow/subflow/kb_subflow_flow_runtime_value_it_categories.png)


19. Once you validate the categories returned by the Subflow test, return to your Subflow by clicking its name in the tabs at the top. Click **Publish** in the top right of the screen. If you get a message stating that **this is associated to 0 flows**, please ignore it and click **Publish** it anyway. 
![KB Subflow](/images/servicenow/subflow/kb_subflow_flow_click_publish.png)
![KB Subflow](/images/servicenow/subflow/kb_subflow_flow_published.png)
 

🎉 Congratulations! 🎉

We now have all the input data we need to run this custom skill. 