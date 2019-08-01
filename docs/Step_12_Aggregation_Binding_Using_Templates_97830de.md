<!-- loio97830de2d7314e93b5c1ee3878a17be9 -->

| loio |
| -----|
| 97830de2d7314e93b5c1ee3878a17be9 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/97830de2d7314e93b5c1ee3878a17be9) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/97830de2d7314e93b5c1ee3878a17be9)</div>

## Step 12: Aggregation Binding Using Templates

Aggregation binding \(or "list binding"\) allows a control to be bound to a list within the model data and allows relative binding to the list entries by its child controls.

It will automatically create as many child controls as are needed to display the data in the model using one of the following two approaches:

-   Use template control that is cloned as many times as needed to display the data.

-   Use a factory function to generate the correct control per bound list entry based on the data received at runtime.


***

### Preview

   
  
List with aggregation binding<a name="loio97830de2d7314e93b5c1ee3878a17be9__fig_r1j_pst_mr"/>

 ![](loio16424336ab62402e8c27d5d7dac069b1_HiRes.png "List with aggregation binding") 

***

### Coding

You can view and download all files in the Demo Kit at [Data Binding - Step 12](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.tutorial.databinding.12/preview).

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
*HIGHLIGHT START*		var oProductModel = new JSONModel();
		oProductModel.loadData("./model/Products.json");
		sap.ui.getCore().setModel(oProductModel, "products");
*HIGHLIGHT END*

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
		var oView = new XMLView({
			viewName: "sap.ui.demo.db.view.App"
		}).placeAt("content");

		// Register the view with the message manager
		sap.ui.getCore().getMessageManager().registerObject(oView, true);

		// Insert the view into the DOM
		oView.placeAt("content");
	});
});

```

***

### webapp/view/App.view.xml

``` xml
...
					<Input width="200px" enabled="{/enabled}" description="{/currencyCode}"
						value="{
							parts: [
								{path: '/salesToDate'},
								{path: '/currencyCode'}
							],
							type: 'sap.ui.model.type.Currency',
							formatOptions: {showMeasure: false}
						}"/>
				</l:VerticalLayout>
			</l:HorizontalLayout>
		</content>
	</Panel>
*HIGHLIGHT START*	<Panel headerText="{i18n>panel3HeaderText}" class="sapUiResponsiveMargin" width="auto">
		<content>
			<List headerText="{i18n>productListTitle}" items="{products>/Products}">
				<items>
					<ObjectListItem title="{products>ProductName}"
						number="{
							parts: [
								{path: 'products>UnitPrice'},
								{path: '/currencyCode'}
							],
							type: 'sap.ui.model.type.Currency',
							formatOptions: { showMeasure: false }
						}"
						numberUnit="{/currencyCode}">
						<attributes>
							<ObjectAttribute text="{products>QuantityPerUnit}"/>
							<ObjectAttribute title="{i18n>stockValue}"
								text="{
									parts: [
										{path: 'products>UnitPrice'},
										{path: 'products>UnitsInStock'},
										{path: '/currencyCode'}
									],
									formatter: '.formatStockValue'
								}"/>
						</attributes>
					</ObjectListItem>
				</items>
			</List>
		</content>
	</Panel>*HIGHLIGHT END*
...
```

We add a new panel to the view.

***

### webapp/controller/App.controller.js

``` js
sap.ui.define([
	"sap/ui/core/mvc/Controller",
*HIGHLIGHT START*	"sap/m/library",
	"sap/ui/core/Locale",
	"sap/ui/core/LocaleData",
	"sap/ui/model/type/Currency"
*HIGHLIGHT END*
], function (Controller, mobileLibrary*HIGHLIGHT START*, Locale, LocaleData, Currency*HIGHLIGHT END*) {
	"use strict";
	return Controller.extend("sap.ui.demo.db.controller.App", {
		formatMail: function(sFirstName, sLastName) {
			var oBundle = this.getView().getModel("i18n").getResourceBundle();
			return mobileLibrary.URLHelper.normalizeEmail(
				sFirstName + "." + sLastName + "@example.com",
				oBundle.getText("mailSubject", [sFirstName]),
				oBundle.getText("mailBody"));
		}*HIGHLIGHT START*,
		formatStockValue: function(fUnitPrice, iStockLevel, sCurrCode) {
			var sBrowserLocale = sap.ui.getCore().getConfiguration().getLanguage();
			var oLocale = new Locale(sBrowserLocale);
			var oLocaleData = new LocaleData(oLocale);
			var oCurrency = new Currency(oLocaleData.mData.currencyFormat);
			return oCurrency.formatValue([fUnitPrice * iStockLevel, sCurrCode], "string");
*HIGHLIGHT END*
		}
	});
});

```

***

### webapp/model/Products.json \(New\)

``` js
*HIGHLIGHT START*{ "Products": [ {
     "ProductID": 1,
     "ProductName": "Chai",
     "SupplierID": 1,
     "CategoryID": 1,
     "QuantityPerUnit": "10 boxes x 20 bags",
     "UnitPrice": "18.0000",
     "UnitsInStock": 39,
     "UnitsOnOrder": 0,
     "ReorderLevel": 10,
     "Discontinued": false
    }, {
     "ProductID": 2,
     "ProductName": "Chang",
     "SupplierID": 1,
     "CategoryID": 1,
     "QuantityPerUnit": "24 - 12 oz bottles",
     "UnitPrice": "19.0000",
     "UnitsInStock": 17,
     "UnitsOnOrder": 40,
     "ReorderLevel": 25,
     "Discontinued": true
    }, {
     "ProductID": 3,
     "ProductName": "Aniseed Syrup",
     "SupplierID": 1,
     "CategoryID": 2,
     "QuantityPerUnit": "12 - 550 ml bottles",
     "UnitPrice": "10.0000",
     "UnitsInStock": 0,
     "UnitsOnOrder": 70,
     "ReorderLevel": 25,
     "Discontinued": false
    }, {
     "ProductID": 4,
     "ProductName": "Chef Anton's Cajun Seasoning",
     "SupplierID": 2,
     "CategoryID": 2,
     "QuantityPerUnit": "48 - 6 oz jars",
     "UnitPrice": "22.0000",
     "UnitsInStock": 53,
     "UnitsOnOrder": 0,
     "ReorderLevel": 0,
     "Discontinued": false
    }, {
     "ProductID": 5,
     "ProductName": "Chef Anton's Gumbo Mix",
     "SupplierID": 2,
     "CategoryID": 2,
     "QuantityPerUnit": "36 boxes",
     "UnitPrice": "21.3500",
     "UnitsInStock": 0,
     "UnitsOnOrder": 0,
     "ReorderLevel": 0,
     "Discontinued": true
    }]
  }*HIGHLIGHT END*
```

We now use a new JSON model file for product data.

***

### webapp/i18n/i18n.properties

``` prefs
... 
# Screen titles
panel1HeaderText=Data Binding Basics
panel2HeaderText=Address Details
*HIGHLIGHT START*panel3HeaderText=Aggregation Binding*HIGHLIGHT END*

# Invoice List
invoiceListTitle=Invoices
statusA=New
statusB=In Progress
statusC=Done

*HIGHLIGHT START*# Product list
productListTitle=Product List
stockValue=Current Stock Value*HIGHLIGHT END*
```

***

### webapp/i18n/i18n\_de.properties

``` prefs
...
# Screen titles
panel1HeaderText=Data Binding Basics
panel2HeaderText=Adressdetails
*HIGHLIGHT START*panel3HeaderText=Aggregation Binding*HIGHLIGHT END*

# Invoice List
invoiceListTitle=Rechnungen
statusA=Neu
statusB=Laufend
statusC=Abgeschlossen

*HIGHLIGHT START*# Product list
productListTitle=Artikelliste
stockValue=Lagerbestand Wert*HIGHLIGHT END*
```

We add the missing texts.

**Related information**  


[List Binding \(Aggregation Binding\)](List_Binding_(Aggregation_Binding)_91f0577.md)

