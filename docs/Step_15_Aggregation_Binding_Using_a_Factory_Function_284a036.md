<!-- loio284a036c8ff943238fb65bf5a2676fb7 -->

| loio |
| -----|
| 284a036c8ff943238fb65bf5a2676fb7 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/284a036c8ff943238fb65bf5a2676fb7) | [demo kit latest release](https://sdk.openui5.org/topic/284a036c8ff943238fb65bf5a2676fb7)</div>

## Step 15: Aggregation Binding Using a Factory Function

Instead of using a single hard-coded template control, we now opt for a factory function to generate different controls based on the data received at runtime. This approach is much more flexible and allows for the display of complex or heterogeneous data.

***

### Preview

  
  
**A different type of list item is displayed for a discontinued product**

![The graphic has an explanatory text](images/loiodb27ba88d80c4778809bdb9b971531f9_LowRes.png "A different type of list item is displayed for a discontinued product")

***

### Coding

You can view and download all files in the Demo Kit at [Data Binding - Step 15](https://sdk.openui5.org/entity/sap.ui.core.tutorial.databinding/sample/sap.ui.core.tutorial.databinding.15).

1.  Create a `ProductSimple.fragment.xml` file in the `view` folder. Here, define an `sap.m.StandardListItem` that is used when the stock level is zero and the product is discontinued. In this simple use case, you only need to define a warning icon and a "Product Discontinued" message in the `info` property.

    **webapp/view/ProductSimple.fragment.xml \(New\)**

    ```xml
    <core:FragmentDefinition
    	xmlns="sap.m"
    	xmlns:core="sap.ui.core">
    	<StandardListItem
    		id="productSimple"
    		icon="sap-icon://warning"
    		title="{products>ProductName} ({products>QuantityPerUnit})"
    		info="{i18n>Discontinued}"
    		type="Active"
    		infoState="Error"
    		press=".onItemSelected">
    	</StandardListItem>
    </core:FragmentDefinition>
    
    ```

2.  Create a new `ProductExtended.fragment.xml` file in the `view` folder. In this extended use case, you create an `ObjectListItem` to display more product details. The properties are bound to the fields of the current data binding context. This allows the use of types, formatters, and all handlers defined in the assigned controller. However, you can't define more complex logic declaratively in XML. Therefore, we add a single `sap.m.ObjectAttribute` in a factory function of the controller using JavaScript, which displays an "Out of Stock" message when the stock level is zero.

    **webapp/view/ProductExtended.fragment.xml \(New\)**

    ```xml
    <core:FragmentDefinition
    	xmlns="sap.m"
    	xmlns:core="sap.ui.core"
    	core:require="{Currency: 'sap/ui/model/type/Currency'}">
    	<ObjectListItem
    		id="productExtended"
    		title="{products>ProductName} ({products>QuantityPerUnit})"
    		number="{
    			parts: [
    				{path: 'products>UnitPrice'},
    				{path: '/currencyCode'}
    			],
    			type: 'Currency',
    			formatOptions : {
    				showMeasure : false
    			}
    		}"
    		type="Active"
    		numberUnit="{/currencyCode}"
    		press=".onItemSelected">
    	</ObjectListItem>
    </core:FragmentDefinition>
    ```

3.  In the `App.view.xml` file, add an XML namespace for `sap.ui.core`. Then, remove the `items` aggregation from the `sap.m.List` XML element. Add an `id` attribute to the `sap.m.List` and include the factory function in the items' binding definition. Lastly, add the two newly created fragments as dependents to the `sap.m.List`.

    **webapp/view/App.view.xml**

    ```xml
    <mvc:View
    	controllerName="ui5.databinding.controller.App"
    	xmlns="sap.m"
    	xmlns:core="sap.ui.core"
    	xmlns:form="sap.ui.layout.form"
    	xmlns:l="sap.ui.layout"
    	xmlns:mvc="sap.ui.core.mvc"
    	core:require="{Currency: 'sap/ui/model/type/Currency'}">
    ...
    	<Panel headerText="{i18n>panel3HeaderText}" class="sapUiResponsiveMargin" width="auto">
    		<List
    			id="ProductList"
    			headerText="{i18n>productListTitle}"
    			items="{
    				path: 'products>/Products',
    				factory: '.productListFactory'
    			}">
    			<dependents>
    				<core:Fragment fragmentName="ui5.databinding.view.ProductSimple" type="XML"/>
    				<core:Fragment fragmentName="ui5.databinding.view.ProductExtended" type="XML"/>
    			</dependents>
    		</List>
    	</Panel>
    ...
    </mvc:View>
    ```

    The `sap.m.List` that previously held the product list is now just a named, but otherwise empty placeholder. Without a factory function to populate it, this `List` would always remain empty. As the fragments are declared as dependents, they also inherit the controller of the view. This means that the `onItemSelect` function of the `App.controller.js` can still be used in the `ProductExtended.fragment.xml`.

4.  In the `App.controller.js` file, add a new import for the `sap.m.ObjectAttribute` class and create a new function called `productListFactory`. This factory function returns a control for the associated binding context, similar to the XML templates we've defined in the previous steps. The controls returned by this factory function must suit the items aggregation of the `sap.m.List` object. In this case, it returns either an `sap.m.StandardListItem` or an `sap.m.ObjectListItem` based on the data stored in the context of the item to be created.

    **webapp/controller/App.controller.js**

    ```js
    sap.ui.define([
    	"sap/m/library",
    	"sap/m/ObjectAttribute",
    	"sap/ui/core/mvc/Controller",
    	"sap/ui/model/type/Currency"
    ], (mobileLibrary, ObjectAttribute, Controller, Currency) => {
    	...
    		productListFactory(sId, oContext) {
    			let oUIControl;
    
    			// Decide based on the data which dependent to clone
    			if (oContext.getProperty("UnitsInStock") === 0 && oContext.getProperty("Discontinued")) {
    				// The item is discontinued, so use a StandardListItem
    				oUIControl = this.byId("productSimple").clone(sId);
    			} else {
    				// The item is available, so we will create an ObjectListItem
    				oUIControl = this.byId("productExtended").clone(sId);
    
    				// The item is temporarily out of stock, so we will add a status
    				if (oContext.getProperty("UnitsInStock") < 1) {
    					oUIControl.addAttribute(new ObjectAttribute({
    						text : {
    							path: "i18n>outOfStock"
    						}
    					}));
    				}
    			}
    
    			return oUIControl;
    		}
    
    	});
    });
    ```

    The function decides which type of control to return by checking the current stock level and whether the product is discontinued. For both options, it loads and clones the respective XML fragment, which allows the view logic to be defined dynamically. If the stock level is zero and the product is discontinued, the `ProductSimple` XML fragment is used. Otherwise, the `ProductExtended` XML fragment is used.

    For each item of the list, the corresponding control is cloned. This method creates a fresh copy of a control that can be bound to the context of the list item. Remember, in a factory function you are responsible for the life cycle of the control you create.

    If the product is not discontinued but the stock level is zero, we're temporarily out of stock. In this case, a single `sap.m.ObjectAttribute` is added to the cloned control. The "Out of Stock" message is bound to the `sap.m.ObjectAttribute`'s `text` property using JavaScript. Like declarative definitions in the XML view or fragments, you can bind properties using data binding syntax. Here, the text is bound to an entry in the resource bundle. Since the `sap.m.ObjectAttribute` is a child of the list item, it has access to all assigned models and the current binding context.

    Finally, the function returns the control that is then displayed inside the list.

5.  Lastly, add the new texts to the `i18n.properties` and `i18n_de.properties` files.

    **webapp/i18n/i18n.properties**

    ```ini
    ...
    # Product Details
    ...
    outOfStock=Out of Stock
    ```

    **webapp/i18n/i18n\_de.properties**

    ```ini
    ...
    # Product Details
    ...
    outOfStock=Nicht vorr\u00e4tig
    ```


Congratulations! You've completed the Data Binding tutorial.

**Parent topic:**[Data Binding Tutorial](Data_Binding_Tutorial_e531093.md "In this tutorial, we explain the concepts of data binding in OpenUI5.")

**Next:**[Step 14: Expression Binding](Step_14_Expression_Binding_5cff8d1.md "An expression binding lets you display a calculated value on the screen, which is derived from values found in a model object. This feature allows you to insert simple formatting or calculations directly into the data binding string. In this example, we're changing the color of the price depending on whether it's above or below a certain threshold. The threshold value is stored in the JSON model.")

**Related Information**  


[List Binding \(Aggregation Binding\)](List_Binding_Aggregation_Binding_91f0577.md "List binding (or aggregation binding) is used to automatically create child controls according to model data.")

[XML Fragments](XML_Fragments_2c677b5.md "XML fragments are similar to XML view, but have no <View> tag as root element. Instead, there is an OpenUI5 control.")

[Using Factory Functions](Using_Factory_Functions_335848a.md "")

