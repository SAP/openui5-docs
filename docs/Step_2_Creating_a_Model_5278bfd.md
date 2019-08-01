<!-- loio5278bfd38f3940b192df0e39f2fb33b3 -->

| loio |
| -----|
| 5278bfd38f3940b192df0e39f2fb33b3 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/5278bfd38f3940b192df0e39f2fb33b3) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/5278bfd38f3940b192df0e39f2fb33b3)</div>

## Step 2: Creating a Model

In this step, we create a model as container for the data on which your application operates.

The business data within a model can be defined using various formats:

-   JavaScript Object Notation \(JSON\)

-   Extensible Markup Language \(XML\)

-   OData

-   Your own custom format \(not covered in this tutorial\)


> Note:
> There is also a special type of model called a "resource model". This model type is used as a wrapper object around a resource bundle file. The names of such files must end with `.properties` and are used typically for holding language-specific text.
> 
> We will use this in [Step 6: Resource Models](Step_6_Resource_Models_9790d9a.md).
> 
> 

When JSON, XML and resource models are created, the data they contain is loaded in a single request \(either from a file stored locally on the client or by requesting it from a Web server\). In other words, after the model's data has been requested, the entire model is known to the application. These models are known as client-side models and tasks such as filtering and sorting are performed locally on the client.

An OData model however, is a server-side model. This means that whenever an application needs data from the model, it must be requested from the server. Such a request will almost never return all the data in the model, typically because this would be far more data than is required by the client application. Consequently, tasks such as sorting and filtering should always be delegated to the server.

In this tutorial, we will focus on JSON models since they are the simplest ones to work with.

***

### Preview

   
  
Screen with text derived from a model object \(No visual changes to last step\)<a name="loio5278bfd38f3940b192df0e39f2fb33b3__fig_r1j_pst_mr"/>

 ![](loio6d391d527601499fbeb3734246b2c067_HiRes.png "Screen with text derived from a model object (No visual changes to last step)") 

***

### Coding

You can view and download all files in the Demo Kit at [Data Binding - Step 2](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.tutorial.databinding.02/preview).

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
*HIGHLIGHT START*		// Create a JSON model from an object literal
		var oModel = new JSONModel({
			greetingText: "Hi, my name is Harry Hawk"
		});

		// Assign the model object to the SAPUI5 core
		sap.ui.getCore().setModel(oModel);
*HIGHLIGHT END*

		// Create a text UI element that displays a hardcoded text string
		new Text({text: "Hi, my name is Harry Hawk"}).placeAt("content");
	});
});

```

Create a new JSON model passing the data as object literal and store the resulting model instance in a local variable called `oModel`.

Set `oModel` to be the default model within the entire OpenUI5 core.

This makes the model object globally available to all controls used within the application.

In this case we have bound the model object to the OpenUI5 core. This has been done for simplicity, but is not considered good practice. Generally speaking, a model object holding business data should be bound to the view that displays the data. We will correct this part of the code in the following steps.

> Note:
> Models can be set on every control by calling `setModel()`. The model is then propagated to all aggregated child controls \(and their children, and so on…\). All child control will then have access to that model
> 
> 

The text that is displayed on the UI is still hard-coded and not taken from the model - we will bind the property `greetingText` to our UI control in the next step.

**Related information**  


[Models](Models_e1b6259.md)

[JSON Model](JSON_Model_.md#loio96804e3315ff440aa0a50fd290805116)

