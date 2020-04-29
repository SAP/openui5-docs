<!-- loiob8c4e534cdb440e9a5bbff86f9572bd6 -->

| loio |
| -----|
| b8c4e534cdb440e9a5bbff86f9572bd6 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/b8c4e534cdb440e9a5bbff86f9572bd6) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/b8c4e534cdb440e9a5bbff86f9572bd6)</div>

## Step 11: Validation Using the Message Manager

So far, we have created a currency field that can format itself correctly. The currency data type also has the ability to validate that user input adheres to to the requirements of a currency; however, data type validation functions are managed by OpenUI5, which of itself has no mechanism for reporting error messages back to the UI; therefore, we need a mechanism for reporting error messages raised by validation functions back to the user. In this step, we will connect the entire view to a feature known as the "Message Manager". Once this connection is established, any validation error messages generated based on the user input will be passed to the message manager which in turn will connect them to the appropriate view and control that caused the error.

***

### Preview

   
  
A message appears<a name="loiob8c4e534cdb440e9a5bbff86f9572bd6__fig_r1j_pst_mr"/>

 ![](loio418c4f74dae54878bda198882046a455_HiRes.png "A message appears") 

***

### Coding

You can view and download all files in the Demo Kit at [Data Binding - Step 11](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.tutorial.databinding.11/preview).

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
		var oModel = new JSONModel({
			firstName: "Harry",
			lastName: "Hawk",
			enabled: true,
			address: {
				street: "Dietmar-Hopp-Allee 16",
				city: "Walldorf",
				zip: "69190",
				country: "Germany"
			},
			"salesToDate": 12345.6789,
			"currencyCode": "EUR"
		});

		// Assign the model object to the SAPUI5 core
		sap.ui.getCore().setModel(oModel);

		var oResourceBundle = new ResourceModel({
			bundleName: "sap.ui.demo.db.i18n.i18n"
		});

		sap.ui.getCore().setModel(oResourceBundle, "i18n");

		// Display the XML view called "App"
*HIGHLIGHT START*		var oView *HIGHLIGHT END*= new XMLView({
			viewName: "sap.ui.demo.db.view.App"
		}).placeAt("content");

*HIGHLIGHT START*		// Register the view with the message manager
		sap.ui.getCore().getMessageManager().registerObject(oView, true);
*HIGHLIGHT END*

		// Insert the view into the DOM
		*HIGHLIGHT START*oView*HIGHLIGHT END*.placeAt("content");
	});
});

```

The changes to the coding are minimal:

-   The XML view is now created as a named object called `oView`.

-   The view object `oView` is registered with the `MessageManager`.

-   Once registered, the XML view is then inserted into the DOM as before.


You can now enter a non-numeric value into the *Sales To Date* field and either press *Enter* or move the focus to a different UI control. This action triggers either the `onenter` or `onchange` event and then OpenUI5 executes the validation function belonging to the `sap.ui.model.type.Currency` data type.

Now that the view has been registered with the `MessageManager`, any validation error messages will be picked up by the `MessageManager`, which in turn checks its list of registered objects and then passes the error message back to the correct view for display.

Note that the field in error has a red border: ![](loio44db88e92bc445b2b00e1b8e53b5ca9a_HiRes.png) 

However, the error message itself will only be displayed when that particular field has focus: ![](loioe67207b43d08410e82e74ad57ffbc022_HiRes.png)

**Related information**  


[Error, Warning, and Info Messages](Error,_Warning,_and_Info_Messages_62b1481.md)

