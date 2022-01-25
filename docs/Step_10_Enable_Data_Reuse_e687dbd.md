<!-- loioe687dbdc4c064ba3a3ce3942288e8f74 -->

| loio |
| -----|
| e687dbdc4c064ba3a3ce3942288e8f74 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/e687dbdc4c064ba3a3ce3942288e8f74) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/e687dbdc4c064ba3a3ce3942288e8f74)</div>

## Step 10: Enable Data Reuse

In this step we avoid unnecessary back-end requests by preventing the destruction of data shown in the detail area when sorting or filtering the list.

***

<a name="loioe687dbdc4c064ba3a3ce3942288e8f74__section_bt4_fxc_z1b"/>

### Preview

   
  
<a name="loioe687dbdc4c064ba3a3ce3942288e8f74__fig_ybl_pdx_4cb"/>No visual change compared to the last step

 ![A list of users with an added detail area](loio6e9025bc4522494c97d1b60a3f8eec31_LowRes.png "No visual change compared to the last step") 

***

<a name="loioe687dbdc4c064ba3a3ce3942288e8f74__section_tsr_gxc_z1b"/>

### Coding

You can view and download all files at [OData V4 - Step 10](https://openui5.hana.ondemand.com/#/entity/sap.ui.core.tutorial.odatav4/sample/sap.ui.core.tutorial.odatav4.10/code).

***

<a name="loioe687dbdc4c064ba3a3ce3942288e8f74__section_pvc_fyc_z1b"/>

### webapp/controller/App.controller.js

``` js
...
		onMessageBindingChange : function (oEvent) {
			...
		},

		onSelectionChange : function (oEvent) {
			var oDetailArea = this.byId("detailArea"),
				oLayout = this.byId("defaultLayout"),
				oUserContext = oEvent.getParameters().listItem.getBindingContext();
*HIGHLIGHT START*				oOldContext = oDetailArea.getBindingContext(),
				oSearchField = this.byId("searchField"),


			// remove keepAlive from old context
			if (oOldContext) {
				oOldContext.setKeepAlive(false);
			}
*HIGHLIGHT END*
			// set binding
			oDetailArea.setBindingContext(oUserContext);
*HIGHLIGHT START*			// set keepAlive for new context
			oUserContext.setKeepAlive(true, function () {
				// hides detail area when context is destroyed
				oLayout.setSize("100%");
				oLayout.setResizable(false);
				oDetailArea.setVisible(false);
				oSearchField.setWidth("20%");
			});
*HIGHLIGHT END*
			// resize view
			oDetailArea.setVisible(true);
			oLayout.setSize("60%");
			oLayout.setResizable(true);
*HIGHLIGHT START*			oSearchField.setWidth("40%");*HIGHLIGHT END*
		},

...
```

We extend the logic of the `onSelectionChange` function. First, we check if there's an "old" binding context in the detail area. If so, the `keepAlive` for the old context is set to `false`.

After the new binding context is added to the detail area, we set `keepAlive` to `true` and add an `onBeforeDestroy` function to it, which hides the detail area when the user linked to it is deleted.

You can use the `Context#setKeepAlive` method to prevent the destruction of information shown in the detail area when the selected user is no longer part of the list from which the information was selected. This could otherwise happen if you filter or sort the list.

**Parent topic:** [OData V4](OData_V4_bcdbde6.md "In this tutorial, we explore how features of OData V4 can be used in OpenUI5. We write a small app that consumes data from an OData V4 service to understand how to access, modify, aggregate, and filter data in an OData V4 model.")

**Next:** [Step 9: List-Detail Scenario](Step_9_List_Detail_Scenario_ec44581.md "In this step we add a detail area with additional information.")

**Previous:** [Step 11: Add Table with :n Navigation to Detail Area](Step_11_Add_Table_with_n_Navigation_to_Detail_Area_19cc773.md "In this step we add a table with additional information to the detail area.")

**Related Information**  


[Extending the Lifetime of a Context that is not Used Exclusively by a Table Collection](Data_Reuse_648e360.md#loio648e360fa22d46248ca783dc6eb44531__section_ELC)

