<!-- loio9790d9aa686e4f818f2ad99057adb7ee -->

| loio |
| -----|
| 9790d9aa686e4f818f2ad99057adb7ee |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/9790d9aa686e4f818f2ad99057adb7ee) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/9790d9aa686e4f818f2ad99057adb7ee)</div>

## Step 6: Resource Models

Business applications also require language-specific \(translatable\) texts used as labels and descriptions on the user interface.

The example we used at the start of this tutorial was overly simplistic as we stored language-specific text directly in a JSON model object. Generally speaking, unless language-specific text is derived directly from a back-end system, it is not considered good programming practice to place translatable texts directly into a model. So let's correct this situation by placing all translatable texts \(such as field labels\) into a resource bundle.

***

### Preview

   
  
Texts derived from the resource model \(No visual change to last step\)<a name="loio9790d9aa686e4f818f2ad99057adb7ee__fig_r1j_pst_mr"/>

 ![](loio61d68f167778425bbdd2abd7d550ae65_HiRes.png "Texts derived from the resource model (No visual change to last step)") 

***

### Coding

You can view and download all files in the Demo Kit at [Data Binding - Step 6](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.tutorial.databinding.06/preview).

***

### webapp/index.js

``` js
sap.ui.require([
	"sap/ui/model/json/JSONModel",
	"sap/ui/core/mvc/XMLView",
	"sap/ui/model/resource/ResourceModel"
], function (JSONModel, XMLView, ResourceModel) {
	"use strict";

	// Attach an anonymous function to the SAPUI5 'init' event
	sap.ui.getCore().attachInit(function () {
		// Create a JSON model from an object literal
		var oModel = new JSONModel({
			firstName: "Harry",
			lastName: "Hawk",
			enabled: true
		});

		// Assign the model object to the SAPUI5 core
		sap.ui.getCore().setModel(oModel);

		// Create a resource bundle for language specific texts
*HIGHLIGHT START*		var oResourceModel = new ResourceModel({
			bundleName: "sap.ui.demo.db.i18n.i18n"
		});

		// Assign the model object to the SAPUI5 core using the name "i18n"
		sap.ui.getCore().setModel(oResourceModel, "i18n");*HIGHLIGHT END*

		// Display the XML view called "App"
		new XMLView({
			viewName: "sap.ui.demo.db.view.App"
		}).placeAt("content");
	});
});

```

Since we are creating a resource model, the file name is assumed to have the extension `.properties`; this does not need to be stated explicitly. The resource model is set to the core using the model name `i18n`.

> Note:
> Remove `, panelHeaderText : "Data Binding Basics"` from the model definition in the `index.js` file. This text is now moved to the resource model.
> 
> 

***

### webapp/i18n/i18n.properties \(New\)

``` prefs
*HIGHLIGHT START*# Field labels
firstName=First Name
lastName=Last Name
enabled=Enabled

# Screen titles
panelHeaderText=Data Binding Basics*HIGHLIGHT END*
```

Create a new folder `i18n`, and a new file `i18n.properties` within and add the code above.

The `panelHeaderText` property has been moved from the JSON model into the `i18n` resource bundle, also the field labels are no longer hard coded in the XML view. This is because all of these text fields need to be translated.

Language-specific text stored in resource models obeys the Java convention for internationalization \(i18n\).

***

### webapp/view/App.view.xml

``` xml
<mvc:View
	xmlns="sap.m"
	xmlns:mvc="sap.ui.core.mvc">
	<Panel headerText="*HIGHLIGHT START*i18n>*HIGHLIGHT END*panelHeaderText}" class="sapUiResponsiveMargin" width="auto">
		<content>
			<Label text="*HIGHLIGHT START*{i18n>firstName}*HIGHLIGHT END*" class="sapUiSmallMargin"/>
			<Input value="{/firstName}" valueLiveUpdate="true" width="200px" enabled="{/enabled}"/>
			<Label text="*HIGHLIGHT START*{i18n>lastName}*HIGHLIGHT END*" class="sapUiSmallMargin"/>
			<Input value="{/lastName}" valueLiveUpdate="true" width="200px" enabled="{/enabled}"/>
			<CheckBox selected="{/enabled}" text="*HIGHLIGHT START*{i18n>enabled}*HIGHLIGHT END*"/>
		</content>
	</Panel>
</mvc:View>

```

Modify the data binding for the panel header and the labels in `App.view.xml` to include the model name. Notice that a "greater than" character separates the model name and the property name, and that i18n property names **must not** start with a slash character.

You could use multiple model instances by using different model names. The model name could be set as second parameter using the `setModel(oResourceModel,“i18n”)` method. The model is then propagated under this name to all aggregated child controls \(and their children, and so on…\). All these controls have access to this model under the name `i18n` as well as to the `JSONModel` \(default model, which has no name\).

**Related information**  


[Resource Model](Resource_Model_.md#loio91f122a36f4d1014b6dd926db0e91070)

