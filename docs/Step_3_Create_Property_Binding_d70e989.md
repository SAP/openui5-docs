<!-- loiod70e9894c09b4c27a98d4850d4e90f2c -->

| loio |
| -----|
| d70e9894c09b4c27a98d4850d4e90f2c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/d70e9894c09b4c27a98d4850d4e90f2c) | [demo kit latest release](https://sdk.openui5.org/topic/d70e9894c09b4c27a98d4850d4e90f2c)</div>

## Step 3: Create Property Binding

Although there is no visible difference, the text on the screen is now derived from model data.

***

### Preview

   
  
<a name="loiod70e9894c09b4c27a98d4850d4e90f2c__fig_r1j_pst_mr"/>Screen with text derived from various sources \(No visual changes to last step\)

 ![](images/loio6d391d527601499fbeb3734246b2c067_HiRes.png "Screen with text derived from various sources (No visual changes to last
					step)") 

***

### Coding

You can view and download all files in the Demo Kit at [Data Binding - Step 3](https://sdk.openui5.org/entity/sap.ui.core.tutorial.databinding/sample/sap.ui.core.tutorial.databinding.03).

***

### webapp/index.js

```js
sap.ui.require([
	"sap/m/Text",
	"sap/ui/model/json/JSONModel"
], function (Text, JSONModel) {
	"use strict";

	// Attach an anonymous function to the SAPUI5 'init' event
	sap.ui.getCore().attachInit(function () {
		// Create a JSON model from an object literal
		var oModel = new JSONModel({
			greetingText: "Hi, my name is Harry Hawk"
		});
		// Assign the model object to the SAPUI5 core
		sap.ui.getCore().setModel(oModel);

		// Display a text element whose text is derived
		// from the model object

		new Text({text: "{/greetingText}"}).placeAt("content");
	});
});

```

The `text` property of the `sap.m.Text` control is set to the value `{/greetingText}`. The curly brackets enclosing a binding path \(binding syntax\) are automatically interpreted as a binding. These binding instances are called `PropertyBindings`. In this case, the control's `text` property is bound to the `greetingText` property at the root of the default model, as the slash \(`/`\) at the beginning of the binding path denotes an absolute binding path.

**Parent topic:** [Data Binding](Data_Binding_e531093.md "In this tutorial, we will explain the concepts of data binding in OpenUI5.")

**Next:** [Step 2: Creating a Model](Step_2_Creating_a_Model_5278bfd.md "In this step, we create a model as container for the data on which your application operates.")

**Previous:** [Step 4: Two-Way Data Binding](Step_4_Two_Way_Data_Binding_c72b922.md "In the examples used so far, we have used a read-only field to display the value of a model property. We will now change the user interface so that the first and last name fields are displayed using sap.m.Input fields and an additional check box control is used to enable or disable both input fields. This arrangement illustrates a feature known as &quot;two-way data binding&quot;. Now that the view contains more controls, we will also move the view definition into an XML file.")

**Related Information**  


[Binding Types](Binding_Types_91f0d8a.md "Depending on the different use cases, you can use different binding types: Propety binding, context binding, and list binding.")

[Property Binding](Property_Binding_91f0652.md "With property binding, you can initialize properties of a control automatically and update them based on the data of the model.")

