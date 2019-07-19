<!-- loiodfe04650afc046e0802abb1a1a90d2d9 -->

| loio |
| -----|
| dfe04650afc046e0802abb1a1a90d2d9 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/dfe04650afc046e0802abb1a1a90d2d9) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/dfe04650afc046e0802abb1a1a90d2d9)</div>

## Step 21: Data Types

The list of invoices is already looking nice, but what is an invoice without a price assigned? Typically prices are stored in a technical format and with a '`.`' delimiter in the data model. For example, our invoice for pineapples has the calculated price `87.2` without a currency. We are going to use the OpenUI5 data types to format the price properly, with a locale-dependent decimal separator and two digits after the separator.

***

### Preview

   
  
The list of invoices with prices and number units<a name="loiodfe04650afc046e0802abb1a1a90d2d9__fig_r1j_pst_mr"/>

 ![](loioa8394701ac104827af7e2034cb527e1c_HiRes.png "The list of invoices with prices and number units") 

***

### Coding

You can view and download all files at [Walkthrough - Step 21](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.21/preview).

``` xml
<mvc:View
   *HIGHLIGHT START*controllerName="sap.ui.demo.walkthrough.controller.InvoiceList"*HIGHLIGHT END*
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
		*HIGHLIGHT START*number="{
			parts: [{path: 'invoice>ExtendedPrice'}, {path: 'view>/currency'}],
			type: 'sap.ui.model.type.Currency',
			formatOptions: {
				showMeasure: false
			}
		}"
		numberUnit="{view>/currency}"*HIGHLIGHT END*/>
	</items>
   </List>
</mvc:View>
```

We add a price to our invoices list in the view by adding the `number` and `numberUnit` attributes to the `ObjectListItem` control, then we apply the currency data type on the number by setting the `type` attribute of the binding syntax to `sap.ui.model.type.Currency`.

As you can see above, we are using a special binding syntax for the `number` property of the `ObjectListItem`. This binding syntax makes use of so-called "Calculated Fields", which allows the binding of multiple properties from different models to a single property of a control. The properties bound from different models are called “parts”. In the example above, the property of the control is `number` and the bound properties \(“parts”\) retrieved from two different models are `invoice>ExtendedPrice` and `view>/currency`.

We want to display the price in Euro, and typically the currency is part of our data model on the back end. In our case this is not the case, so we need to define it directly in the app. We therefore add a controller for the invoice list, and use the `currency` property as the second part of our binding syntax. The `Currency` type will handle the formatting of the price for us, based on the currency code. In our case, the price is displayed with 2 decimals.

Additionally, we set the formatting option `showMeasure` to `false`. This hides the currency code in the property `number`, because it is passed on to the `ObjectListItem` control as a separate property `numberUnit`.

***

### webapp/controller/InvoiceList.controller.js \(New\)

``` js
*HIGHLIGHT START*sap.ui.define([
	"sap/ui/core/mvc/Controller",
	"sap/ui/model/json/JSONModel"
], function (Controller, JSONModel) {
	"use strict";

	return Controller.extend("sap.ui.demo.walkthrough.controller.InvoiceList", {

		onInit : function () {
			var oViewModel = new JSONModel({
				currency: "EUR"
			});
			this.getView().setModel(oViewModel, "view");
		}

	});
});*HIGHLIGHT END*
```

To be able to access the currency code that is not part of our data model, we define a view model in the controller of the invoice list. It is a simple JSON model with just one key `currency` and the value `EUR`. This can be bound to the formatter of the number field. View models can hold any configuration options assigned to a control to bind properties such as the visibility.

***

### Conventions

-   Use data types instead of custom formatters whenever possible.


**Related information**  


[Composite Binding](Composite_Binding_a2fe8e7.md)

[Formatting, Parsing, and Validating Data](Formatting,_Parsing,_and_Validating_Data_07e4b92.md)

[API Reference: `sap.ui.model.type`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.type-1.html)

[API Reference: `sap.ui.model.type.Currency`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.type.Currency.html)

[Samples: `sap.ui.model.type.Currency` ](https://openui5.hana.ondemand.com/explored.html#/entity/sap.ui.model.type.Currency/samples)

