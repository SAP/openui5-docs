<!-- loio6c7c5c266b534e7ea9a28f861dc515f5 -->

| loio |
| -----|
| 6c7c5c266b534e7ea9a28f861dc515f5 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/6c7c5c266b534e7ea9a28f861dc515f5) | [demo kit latest release](https://sdk.openui5.org/topic/6c7c5c266b534e7ea9a28f861dc515f5)</div>

## Step 13: Element Binding

Now, let's do something with that newly generated list. Typically, you use a list to allow selection of an item and then display the details of that item elsewhere. To accomplish this, we use a form with relatively bound controls and bind it to the selected entity via element binding.

***

### Preview

  
  
**A fourth panel with details for a selected product is displayed**

![The graphic has an explanatory text](images/loio872d2ed3f9144fbfb82e028b17c52ce3_LowRes.png "A fourth panel with details for a selected product is displayed")

***

### Coding

You can view and download all files in the Demo Kit at [Data Binding - Step 13](https://sdk.openui5.org/entity/sap.ui.core.tutorial.databinding/sample/sap.ui.core.tutorial.databinding.13).

1.  In the `App.view.xml` file, add a `press` event handler to the items in the list. Below the panel with the list, add a new panel with an `sap.m.SimpleForm`. To populate the form with data, we bind the entire panel to the path of the element you clicked in the list.

    **webapp/view/App.view.xml**

    ```xml
    ...
      	<Panel headerText="{i18n>panel3HeaderText}" class="sapUiResponsiveMargin" width="auto">
    		<List headerText="{i18n>productListTitle}" items="{products>/Products}">
    			<items>
    				<ObjectListItem
    					press=".onItemSelected"
    					type="Active"
    					title="{products>ProductName}"
    					number="{
    						parts: [
    							{path: 'products>UnitPrice'},
    							{path: '/currencyCode'}
    						],
    						type: 'Currency',
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
    	</Panel>
    	<Panel id="productDetailsPanel" headerText="{i18n>panel4HeaderText}" class="sapUiResponsiveMargin" width="auto">
    		<form:SimpleForm editable="true" layout="ColumnLayout">
    			<Label text="{i18n>ProductID}"/>
    			<Input value="{products>ProductID}"/>
    
    			<Label text="{i18n>ProductName}"/>
    			<Input value="{products>ProductName}"/>
    
    			<Label text="{i18n>QuantityPerUnit}"/>
    			<Input value="{products>QuantityPerUnit}"/>
    
    			<Label text="{i18n>UnitPrice}"/>
    			<Input value="{products>UnitPrice}"/>
    
    			<Label text="{i18n>UnitsInStock}"/>
    			<Input value="{products>UnitsInStock}"/>
    
    			<Label text="{i18n>Discontinued}"/>
    			<CheckBox selected="{products>Discontinued}"/>
    		</form:SimpleForm>
    	</Panel>
    </mvc:View>
    ```

2.  In the controller, add a new function `onItemsSelected`, which binds the newly created panel to the correct item whenever it's pressed.

    **webapp/controller/App.controller.js**

    ```js
    sap.ui.define([
    	"sap/m/library",
    	"sap/ui/core/mvc/Controller",
    	"sap/ui/model/type/Currency"
    ], (mobileLibrary, Controller, Currency) => {
    	"use strict";
    
    	return Controller.extend("ui5.databinding.controller.App", {
    		formatMail(sFirstName, sLastName) {
    			const oBundle = this.getView().getModel("i18n").getResourceBundle();
    
    			return mobileLibrary.URLHelper.normalizeEmail(
    				sFirstName + "." + sLastName + "@example.com",
    				oBundle.getText("mailSubject", [sFirstName]),
    				oBundle.getText("mailBody"));
    		},
    
    		formatStockValue(fUnitPrice, iStockLevel, sCurrCode) {
    			const oCurrency = new Currency();
    			return oCurrency.formatValue([fUnitPrice * iStockLevel, sCurrCode], "string");
    		},
    
    		onItemSelected(oEvent) {
    			const oSelectedItem = oEvent.getSource();
    			const oContext = oSelectedItem.getBindingContext("products");
    			const sPath = oContext.getPath();
    			const oProductDetailPanel = this.byId("productDetailsPanel");
    			oProductDetailPanel.bindElement({ path: sPath, model: "products" });
    		}
    	});
    });
    ```

3.  Lastly, add the new texts to the `i18n.properties` and `i18n_de.properties` files.

    **webapp/i18n/i18n.properties**

    ```ini
    ...
    # Screen titles
    panel1HeaderText=Data Binding Basics
    panel2HeaderText=Address Details
    panel3HeaderText=Aggregation Binding
    panel4HeaderText=Product Details
    
    ...
    
    # Product Details
    ProductID=Product ID
    ProductName=Product Name
    QuantityPerUnit=Quantity per Unit
    UnitPrice=Unit Price
    UnitsInStock=Number of Units in Stock
    Discontinued=Discontinued
    
    ```

    **webapp/i18n/i18n\_de.properties**

    ```ini
    # Screen titles
    panel1HeaderText=Data Binding Grundlagen
    panel2HeaderText=Adressdetails
    panel3HeaderText=Aggregation Binding
    panel4HeaderText=Produktdetails
     
    ...
    
    # Product Details
    ProductID=Produkt-ID
    ProductName=Produktname
    QuantityPerUnit=Menge pro Einheit
    UnitPrice=Preis pro Einheit
    UnitsInStock=Lagerbestand
    Discontinued=Eingestellt
    ```


Now, you can click on an element in the list and view its details in the panel below. You can even edit these details, and the changes are directly reflected in the list because we use two-way binding.

> ### Note:  
> Element bindings can also be relative to their parent context.

**Parent topic:**[Data Binding Tutorial](Data_Binding_Tutorial_e531093.md "In this tutorial, we explain the concepts of data binding in OpenUI5.")

**Next:**[Step 12: Aggregation Binding Using Templates](Step_12_Aggregation_Binding_Using_Templates_97830de.md "Aggregation binding, also known as &quot;list binding&quot;, lets a control bind to a list within the model data. This binding allows relative binding to the list entries by its child controls.")

**Previous:**[Step 14: Expression Binding](Step_14_Expression_Binding_5cff8d1.md "An expression binding lets you display a calculated value on the screen, which is derived from values found in a model object. This feature allows you to insert simple formatting or calculations directly into the data binding string. In this example, we're changing the color of the price depending on whether it's above or below a certain threshold. The threshold value is stored in the JSON model.")

**Related Information**  


[Context Binding \(Element Binding\)](Context_Binding_Element_Binding_91f05e8.md "Context binding (or element binding) allows you to bind elements to a specific object in the model data, which will create a binding context and allow relative binding within the control and all of its children. This is especially helpful in list-detail scenarios.")

