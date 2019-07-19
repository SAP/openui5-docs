<!-- loio2366345a94f64ec1a80f9d9ce50a59ef -->

| loio |
| -----|
| 2366345a94f64ec1a80f9d9ce50a59ef |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/2366345a94f64ec1a80f9d9ce50a59ef) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/2366345a94f64ec1a80f9d9ce50a59ef)</div>

## Step 32: Routing with Parameters

We can now navigate between the overview and the detail page, but the actual item that we selected in the overview is not displayed on the detail page yet. A typical use case for our app is to show additional information for the selected item on the detail page.

To make this work, we have to pass over the information which item has been selected to the detail page and show the details for the item there.

***

### Preview

   
  
The selected invoice details are now shown in the details page<a name="loio2366345a94f64ec1a80f9d9ce50a59ef__fig_r1j_pst_mr"/>

 ![](loio3a961735fdea4598a24c0ca1a3b7a5b2_HiRes.png "The selected invoice details are now shown in the details page") 

***

### Coding

You can view and download all files at [Walkthrough - Step 32](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.32/preview).

``` js
{
  "_version": "1.12.0",
  …
  "sap.ui5": {
	…
	"routing": {
	  "config": {
		"routerClass": "sap.m.routing.Router",
		"viewType": "XML",
		"viewPath": "sap.ui.demo.walkthrough.view",
		"controlId": "app",
		"controlAggregation": "pages",
		"async": true
	  },
	  "routes": [
		{
		  "pattern": "",
		  "name": "overview",
		  "target": "overview"
		},
		{
		  "pattern": "detail*HIGHLIGHT START*/{invoicePath}*HIGHLIGHT END*",
		  "name": "detail",
		  "target": "detail"
		}
	  ],
		  "targets": {
		"overview": {
		  "viewID": "overview"
		  "viewName": "Overview"
		},
		"detail": {
		  "viewId": "detail"
		  "viewName": "Detail"
		}
	  }
	}
  }
}
```

We now add a navigation parameter `invoicePath` to the detail route so that we can hand over the information for the selected item to the detail page. Mandatory navigation parameters are defined with curly brackets.

***

### webapp/view/Detail.view.xml

``` xml
<mvc:View
	*HIGHLIGHT START*controllerName="sap.ui.demo.walkthrough.controller.Detail"*HIGHLIGHT END*
	xmlns="sap.m"
	xmlns:mvc="sap.ui.core.mvc">
	<Page
		title="{i18n>detailPageTitle}">
		<ObjectHeader
			*HIGHLIGHT START*intro="{invoice>ShipperName}"
			title="{invoice>ProductName}"/>*HIGHLIGHT END*
	</Page>
</mvc:View>
```

We add a controller that will take care of setting the item's context on the view and bind some properties of the `ObjectHeader` to the fields of our `invoice` model. We could add more detailed information from the `invoice` object here, but for simplicity reasons we just display two fields for now.

***

### webapp/controller/InvoiceList.controller.js

``` js
sap.ui.define([
	"sap/ui/core/mvc/Controller",
	"sap/ui/model/json/JSONModel",
	"../model/formatter",
	"sap/ui/model/Filter",
	"sap/ui/model/FilterOperator"
], function (Controller, JSONModel, formatter, Filter, FilterOperator) {
	"use strict";
	return Controller.extend("sap.ui.demo.walkthrough.controller.InvoiceList", {
		…

		onPress: function (oEvent) {
			*HIGHLIGHT START*var oItem = oEvent.getSource();*HIGHLIGHT END*
			var oRouter = sap.ui.core.UIComponent.getRouterFor(this);
			oRouter.navTo("detail"*HIGHLIGHT START*, {
				invoicePath: oItem.getBindingContext("invoice").getPath().substr(1)
			}*HIGHLIGHT END*);
		}
	});
});
```

The control instance that has been interacted with can be accessed by the `getSource` method that is available for all OpenUI5 events. It will return the `ObjectListItem` that has been clicked in our case. We will use it to pass the information of the clicked item to the detail page so that the same item can be displayed there.

In the `navTo` method we now add a configuration object to fill the navigation parameter `invoicePath` with the current information of the item. This will update the URL and navigate to the detail view at the same time. On the detail page, we can access this `context` information again and display the corresponding item.

To identify the object that we selected, we would typically use the key of the item in the back-end system because it is short and precise. For our invoice items however, we do not have a simple key and directly use the binding path to keep the example short and simple. The path to the item is part of the binding context which is a helper object of OpenUI5 to manage the binding information for controls. The binding context can be accessed by calling the `getBindingContext` method with the model name on any bound OpenUI5 control. We need to remove the first `/` from the binding path by calling `.substr(1)` on the string because this is a special character in URLs and is not allowed, we will add it again on the detail page.

***

### webapp/controller/Detail.controller.js \(New\)

``` js
*HIGHLIGHT START*sap.ui.define([
	"sap/ui/core/mvc/Controller",
	"sap/ui/core/UIComponent"
], function (Controller, UIComponent) {
	"use strict";
	return Controller.extend("sap.ui.demo.walkthrough.controller.Detail", {
		onInit: function () {
			var oRouter = sap.ui.core.UIComponent.getRouterFor(this);
			oRouter.getRoute("detail").attachPatternMatched(this._onObjectMatched, this);
		},
		_onObjectMatched: function (oEvent) {
			this.getView().bindElement({
				path: "/" + oEvent.getParameter("arguments").invoicePath,
				model: "invoice"
			});
		}
	});
});*HIGHLIGHT END*
```

Our last piece to fit the puzzle together is the detail controller. It needs to set the context that we passed in with the URL parameter `invoicePath` on the view, so that the item that has been selected in the list of invoices is actually displayed, otherwise, the view would simply stay empty.

In the `onInit` method of the controller we fetch the instance of our app router and attach to the detail route by calling the method `attachPatternMatched` on the route that we accessed by its name. We register an internal callback function `_onObjectMatched` that will be executed when the route is hit, either by clicking on the item or by calling the app with a URL for the detail page.

In the `_onObjectMatched` method that is triggered by the router we receive an event that we can use to access the URL and navigation parameters. The `arguments` parameter will return an object that corresponds to our navigation parameters from the route pattern. We access the `invoicePath` that we set in the invoice list controller and call the `bindElement` function on the view to set the context. We have to add the root `/` in front of the path again that was removed for passing on the path as a URL parameter.

The `bindElement` function is creating a binding context for a OpenUI5 control and receives the model name as well as the path to an item in a configuration object. This will trigger an update of the UI controls that we connected with fields of the invoice model. You should now see the invoice details on a separate page when you click on an item in the list of invoices.

***

### Conventions

-   Define the routing configuration in the `AppDescriptor`


**Related information**  


[Routing and Navigation](Routing_and_Navigation_3d18f20.md)

[Tutorial: Navigation and Routing](Navigation_and_Routing_1b6dcd3.md)

[API Reference: `sap.m.routing.Router`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.m.routing.Router.html)

[Samples: `sap.m.routing.Router` ](https://openui5.hana.ondemand.com/explored.html#/entity/sap.m.routing.Router/samples)

