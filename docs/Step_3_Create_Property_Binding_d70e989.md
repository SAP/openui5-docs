<!-- loiod70e9894c09b4c27a98d4850d4e90f2c -->

| loio |
| -----|
| d70e9894c09b4c27a98d4850d4e90f2c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/d70e9894c09b4c27a98d4850d4e90f2c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/d70e9894c09b4c27a98d4850d4e90f2c)</div>

## Step 3: Create Property Binding

Although there is no visible difference, the text on the screen is now derived from model data.

***

### Preview

   
  
Screen with text derived from various sources \(No visual changes to last step\)<a name="loiod70e9894c09b4c27a98d4850d4e90f2c__fig_r1j_pst_mr"/>

 ![](loio6d391d527601499fbeb3734246b2c067_HiRes.png "Screen with text derived from various sources (No visual changes to last step)") 

***

### Coding

You can view and download all files in the Demo Kit at [Data Binding - Step 3](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.tutorial.databinding.03/preview).

***

### webapp/index.js

``` js
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

*HIGHLIGHT START*		// Display a text element whose text is derived
		// from the model object
*HIGHLIGHT END*
		new Text({text: "{*HIGHLIGHT START*/greetingText*HIGHLIGHT END*}"}).placeAt("content");
	});
});

```

The `text` property of the `sap.m.Text` control is set to the value `{/greetingText}`. The curly brackets enclosing a binding path \(binding syntax\) are automatically interpreted as a binding. These binding instances are called `PropertyBindings`. In this case, the control's `text` property is bound to the `greetingText` property at the root of the default model, as the slash \(`/`\) at the beginning of the binding path denotes an absolute binding path.

**Related information**  


[Binding Types](Binding_Types_91f0d8a.md)

[Property Binding](Property_Binding_91f0652.md)

