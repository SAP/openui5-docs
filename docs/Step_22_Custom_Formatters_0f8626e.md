<!-- loio0f8626ed7b7542ffaa44601828db20de -->

| loio |
| -----|
| 0f8626ed7b7542ffaa44601828db20de |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/0f8626ed7b7542ffaa44601828db20de) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/0f8626ed7b7542ffaa44601828db20de)</div>

## Step 22: Custom Formatters

If we want to do a more complex logic for formatting properties of our data model, we can also write a custom formatting function. We will now add a localized status with a custom formatter, because the status in our data model is in a rather technical format.

***

### Preview

   
  
<a name="loio0f8626ed7b7542ffaa44601828db20de__fig_r1j_pst_mr"/>A status is now displayed with a custom formatter

 ![](loio7e0112d9ffe54e568fa8ecc44a5af3bf_HiRes.png "A status is now displayed with a custom formatter") 

***

### Coding

You can view and download all files at [Walkthrough - Step 22](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.22/preview).

``` js
*HIGHLIGHT START*sap.ui.define([], function () {
	"use strict";
	return {
		statusText: function (sStatus) {
			var resourceBundle = this.getView().getModel("i18n").getResourceBundle();
			switch (sStatus) {
				case "A":
					return resourceBundle.getText("invoiceStatusA");
				case "B":
					return resourceBundle.getText("invoiceStatusB");
				case "C":
					return resourceBundle.getText("invoiceStatusC");
				default:
					return sStatus;
			}
		}
	};
});*HIGHLIGHT END*
```

We create a new folder `model` in our app project. The new `formatter` file is placed in the model folder of the app, because formatters are working on data properties and format them for display on the UI. So far we did not have any model-related artifacts, except for the `Invoices.json` file, we will now add the folder `webapp/model` to our app. This time we do not extend from any base object but just return a JavaScript object with our `formatter` functions inside the `sap.ui.define` call.

Function `statusText` gets the technical status from the data model as input parameter and returns a human-readable text that is read from the `resourceBundle` file.

***

### webapp/controller/InvoiceList.controller.js

``` js
sap.ui.define([
	"sap/ui/core/mvc/Controller",
	"sap/ui/model/json/JSONModel"*HIGHLIGHT START*,
	"../model/formatter"*HIGHLIGHT END*
], function (Controller, JSONModel, *HIGHLIGHT START*formatter*HIGHLIGHT END*) {
	"use strict";
	return Controller.extend("sap.ui.demo.walkthrough.controller.InvoiceList", {
		*HIGHLIGHT START*formatter: formatter,*HIGHLIGHT END*
		onInit : function () {
			var oViewModel = new JSONModel({
				currency: "EUR"
			});
			this.getView().setModel(oViewModel, "view");
		}
	});
});
```

To load our formatter functions, we have to add it to the `InvoiceList.controller.js`. In this controller, we first add a dependency to our custom `formatter` module. The controller simply stores the loaded formatter functions in the local property `formatter` to be able to access them in the view.

***

### webapp/view/InvoiceList.view.xml

``` xml
<mvc:View
	controllerName="sap.ui.demo.walkthrough.controller.InvoiceList"
	xmlns="sap.m"
	xmlns:mvc="sap.ui.core.mvc">
	<List
			headerText="{i18n>invoiceListTitle}"
		class="sapUiResponsiveMargin"
		width="auto"
		items="{invoice>/Invoices}">
		<items>
			<ObjectListItem
				title="{invoice>Quantity} x {invoice>ProductName}"
				number="{
					parts: [{path: 'invoice>ExtendedPrice'}, {path: 'view>/currency'}],
					type: 'sap.ui.model.type.Currency',
					formatOptions: {
						showMeasure: false
					}
				}"
				numberUnit="{view>/currency}"
				numberState="{=	${invoice>ExtendedPrice} > 50 ? 'Error' : 'Success' }"*HIGHLIGHT START*>
				<firstStatus>
					<ObjectStatus text="{
						path: 'invoice>Status',
						formatter: '.formatter.statusText'
					}"/>
				</firstStatus>
			</ObjectListItem>*HIGHLIGHT END*
		</items>
	</List>
</mvc:View>
```

We add a status using the `firstStatus` aggregation to our `ObjectListItem` that will display the status of our invoice. The custom formatter function is specified with the reserved property `formatter` of the binding syntax. A `"."` in front of the formatter name means that the function is looked up in the controller of the current view. There we defined a property `formatter` that holds our formatter functions, so we can access it by `.formatter.statusText`.

***

### webapp/i18n/i18n.properties

``` prefs
# App Descriptor
appTitle=Hello World
appDescription=A simple walkthrough app that explains the most important concepts of OpenUI5

# Hello Panel
showHelloButtonText=Say Hello
helloMsg=Hello {0}
homePageTitle=Walkthrough
helloPanelTitle=Hello World
openDialogButtonText=Say Hello With Dialog
dialogCloseButtonText=Ok

# Invoice List
invoiceListTitle=Invoices
*HIGHLIGHT START*invoiceStatusA=New
invoiceStatusB=In Progress
invoiceStatusC=Done*HIGHLIGHT END*
```

We add three new entries to the resource bundle that reflect our translated status texts. These texts are now displayed below the `number` attribute of the `ObjectListItem` dependent on the status of the invoice.

**Parent topic:** [Walkthrough](Walkthrough_3da5f4b.md "In this tutorial we will introduce you to all major development paradigms of OpenUI5.")

**Next:** [Step 21: Expression Binding](Step_21_Expression_Binding_c98d573.md "Sometimes the predefined types of OpenUI5 are not flexible enough and you want to do a simple calculation or formatting in the view - that is where expressions are really helpful. We use them to format our price according to the current number in the data model.")

**Previous:** [Step 23: Filtering](Step_23_Filtering_5295470.md "In this step, we add a search field for our product list and define a filter that represents the search term. When searching, the list is automatically updated to show only the items that match the search term.")

**Related Information**  


[Formatting, Parsing, and Validating Data](Formatting_Parsing_and_Validating_Data_07e4b92.md "Data that is presented on the UI often has to be converted so that is human readable and fits to the locale of the user. On the other hand, data entered by the user has to be parsed and validated to be understood by the data source. For this purpose, you use formatters and data types.")

