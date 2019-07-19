<!-- loiobf71375454654b44af01379a3c3a6273 -->

| loio |
| -----|
| bf71375454654b44af01379a3c3a6273 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/bf71375454654b44af01379a3c3a6273) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/bf71375454654b44af01379a3c3a6273)</div>

## Step 20: Aggregation Binding

Now that we have established a good structure for our app, it's time to add some more functionality. We start exploring more features of data binding by adding some invoice data in JSON format that we display in a list below the panel.

***

### Preview

   
  
A list of invoices is displayed below the panel<a name="loiobf71375454654b44af01379a3c3a6273__fig_r1j_pst_mr"/>

 ![](loioc694be7496f2477da923104e6a29e725_HiRes.png "A list of invoices is displayed below the panel") 

***

### Coding

You can view and download all files at [Walkthrough - Step 20](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.20/preview).

``` js
*HIGHLIGHT START*{
  "Invoices": [
	{
	  "ProductName": "Pineapple",
	  "Quantity": 21,
	  "ExtendedPrice": 87.2000,
	  "ShipperName": "Fun Inc.",
	  "ShippedDate": "2015-04-01T00:00:00",
	  "Status": "A"
	},
	{
	  "ProductName": "Milk",
	  "Quantity": 4,
	  "ExtendedPrice": 9.99999,
	  "ShipperName": "ACME",
	  "ShippedDate": "2015-02-18T00:00:00",
	  "Status": "B"
	},
	{
	  "ProductName": "Canned Beans",
	  "Quantity": 3,
	  "ExtendedPrice": 6.85000,
	  "ShipperName": "ACME",
	  "ShippedDate": "2015-03-02T00:00:00",
	  "Status": "B"
	},
	{
	  "ProductName": "Salad",
	  "Quantity": 2,
	  "ExtendedPrice": 8.8000,
	  "ShipperName": "ACME",
	  "ShippedDate": "2015-04-12T00:00:00",
	  "Status": "C"
	},
	{
	  "ProductName": "Bread",
	  "Quantity": 1,
	  "ExtendedPrice": 2.71212,
	  "ShipperName": "Fun Inc.",
	  "ShippedDate": "2015-01-27T00:00:00",
	  "Status": "A"
	}
  ]
}*HIGHLIGHT END*
```

The `invoices` file simply contains five invoices in a JSON format that we can use to bind controls against them in the app. JSON is a very lightweight format for storing data and can be directly used as a data source for OpenUI5 applications.

***

### webapp/manifest.json

``` js
{
…
  "sap.ui5": {
	"rootView": "sap.ui.demo.walkthrough.view.App",
[…]
	"models": {
	  "i18n": {
		"type": "sap.ui.model.resource.ResourceModel",
		"settings": {
		  "bundleName": "sap.ui.demo.walkthrough.i18n.i18n"
		}
	  }*HIGHLIGHT START*,
	  "invoice": {
		"type": "sap.ui.model.json.JSONModel",
		"uri": "Invoices.json"
	  }*HIGHLIGHT END*
	}
  }
}
```

We add a new model `invoice` to the `sap.ui5` section of the descriptor. This time we want a JSONModel, so we set the type to `sap.ui.model.json.JSONModel`. The `uri` key is the path to our test data relative to the component. With this little configuration our component will automatically instantiate a new `JSONModel` which loads the invoice data from the `Invoices.json` file. Finally, the instantiated `JSONModel` is put onto the component as a named model invoice. The named model is then visible throughout our app.

> Note:
> Automatic model instantiation is only available as of OpenUI5 version 1.30. If you are using an older version, you can manually instantiate the resource bundle and other models of the app in the `onInit` method of the `Component.js` file as we did for the resource bundle in [Step 9: Component Configuration](Step_9_Component_Configuration_4cfa608.md).
> 
> 

***

### webapp/view/App.view.xml

``` xml
<mvc:View
	controllerName="sap.ui.demo.walkthrough.controller.App"
	xmlns="sap.m"
	xmlns:mvc="sap.ui.core.mvc"
	displayBlock="true">
	<Shell>
		<App class="myAppDemoWT">
			<pages>
				<Page title="{i18n>homePageTitle}">
					<headerContent>
						<Button
							icon="sap-icon://hello-world"
							press=".onOpenDialog"/>
					</headerContent>
					<content>
						<mvc:XMLView viewName="sap.ui.demo.walkthrough.view.HelloPanel"/>
*HIGHLIGHT START*						<mvc:XMLView viewName="sap.ui.demo.walkthrough.view.InvoiceList"/>*HIGHLIGHT END*
					</content>
				</Page>
			</pages>
		</App>
	</Shell>
</mvc:View>

```

In the app view we add a second view to display our invoices below the panel.

***

### webapp/view/InvoiceList.view.xml \(New\)

``` xml
*HIGHLIGHT START*<mvc:View
   xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc">
   <List
      headerText="{i18n>invoiceListTitle}"
      class="sapUiResponsiveMargin"
      width="auto"
      items="{invoice>/Invoices}" >
      <items>
         <ObjectListItem
            title="{invoice>Quantity} x {invoice>ProductName}"/>
      </items>
   </List>
</mvc:View>*HIGHLIGHT END*
```

The new view is displaying a list control with a custom header text. The item aggregation of the list is bound to the root path `Invoices` of the JSON data. And since we defined a named model, we have to prefix each binding definition with the identifier `invoice>`.

In the `items` aggregation, we define the template for the list that will be automatically repeated for each invoice of our test data. More precisely, we use an `ObjectListItem` to create a control for each aggregated child of the `items` aggregation. The `title` property of the list item is bound to properties of a single invoice. This is achieved by defining a relative path \(without `/` in the beginning\). This works because we have bound the `items` aggregation via `items={invoice>/Invoices}` to the invoices.

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

*HIGHLIGHT START*# Invoice List
invoiceListTitle=Invoices*HIGHLIGHT END*
```

In the text bundle the title of the list is added.

**Related information**  


[Lists](Lists_1da1581.md)

[API Reference: `sap.m.List`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.m.List.html)

[Samples: `sap.m.List` ](https://openui5.hana.ondemand.com/explored.html#/entity/sap.m.List/samples)

[List Binding \(Aggregation Binding\)](List_Binding_(Aggregation_Binding)_91f0577.md)

