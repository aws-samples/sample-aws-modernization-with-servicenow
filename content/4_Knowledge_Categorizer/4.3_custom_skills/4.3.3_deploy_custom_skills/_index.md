---
title: "Deploy the Custom Skill"
chapter: true
weight: 46
---


## Deploying the Custom Skill

In this section, you'll deploy the **custom skill** within the **NOW Assist Skill Kit (NASK)** application that we created in the previous module.

---
1. Click on **Skill settings** at the top of the page. 
![KB deply skill](/images/servicenow/custom_skill/kb_nav_skill_settings.png)

2. Click on the option named Deployment Settings. 
 
3. Underneath the workflow header, set the value to Other, if not already selected. 

4. Tick the option marked UI Action and set the table to Knowledge (to do so, type in kb_knowledge and scroll down until you find it.) 
![KB deply skill](/images/servicenow/custom_skill/kb_set_deployment_settings.png)

5. Click Create UI Action, then Link to UI Action once it appears. 
![KB deply skill](/images/servicenow/custom_skill/kb_click_ui_action.png)

6. A new window containing your UI Action will appear. Change the value in the Name field to IT Knowledge Categorizer.
7. Additionally, check both the Form button and List banner buttons to have the UI action show up in both a form (i.e., a specific KCS KB article record) and list (i.e., a list of KCS KB article records).   
![KB deply skill](/images/servicenow/custom_skill/kb_ui_action_form.png)

8. In the script field, replace everything from the try statement and below with the code provided below.
![KB deply skill](/images/servicenow/custom_skill/kb_script_field.png)

        try { 

            // Capture the original category 
            
            var originalCategoryGR = new GlideRecord('kb_category'); 

            originalCategoryGR.get(current.kb_category);  // Fetch the current category record 

            var originalCategory = originalCategoryGR.getValue('label');  // Store the original category label 

            // Execute the request and get the skill's response 

            var output = sn_one_extend.OneExtendUtil.execute(request)['capabilities'][request.executionRequests[0].capabilityId]['response']; 

            var categorySysId = getCategorySysIdFromModelOutput(output); // custom function to resolve category from output 

            if (categorySysId) { 

                current.kb_category = categorySysId;  // Set the category to the resolved sys_id 

                current.update();  // Save the changes to the KB article 

                // Inform the user of the original category and the updated category with the record number 

                gs.addInfoMessage("The category of record " + current.getValue('number') + " has been updated from '" + originalCategory + "' to '" + output + "'. Please review the update for accuracy."); 

            } else { 
                gs.addErrorMessage('No matching category found for the model output for record ' + current.getValue('number') + '. Please review the output or adjust manually.'); 
            }  

        } catch(e) { 
            gs.error(e); 
            
            gs.addErrorMessage('Something went wrong while executing the skill for record ' + current.getValue('number') + '. Please try again.' + e); 
        } 

        // Custom function to get the sys_id of the category from the model output 

        function getCategorySysIdFromModelOutput(modelOutput) { 

            // Assuming the model output contains the name or label of the category 

            var categoryName = modelOutput.trim();  // Adjust based on actual model output structure, trim to remove extra spaces  

            // Query the KB Category table (kb_category) to get the sys_id of the matching category 

            var kbCategoryGR = new GlideRecord('kb_category'); 

            kbCategoryGR.addQuery('label', categoryName); 

            kbCategoryGR.query(); 

            if (kbCategoryGR.next()) { 

                return kbCategoryGR.getValue('sys_id'); 

            } else { 

                return null; // Return null if no match is found 

            } 
        }

9. Click Update to save the record. 

10. Return to your skill within Now Assist Skill Kit.  

11. In the module that opens, tick the box containing your finalized prompt, then click Publish.
![KB deply skill](/images/servicenow/custom_skill/kb_skill_publish.png)

12. In the dialog window that opens, select the checkbox **Prompt name (v1)** and click Publish
![KB deply skill](/images/servicenow/custom_skill/kb_skill_publish_bedrock.png)
