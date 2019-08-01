<!-- loio7f651316d396400d88835adb0d021532 -->

| loio |
| -----|
| 7f651316d396400d88835adb0d021532 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/7f651316d396400d88835adb0d021532) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/7f651316d396400d88835adb0d021532)</div>

## Step 7: Routing

In this step, we utilize the `sap.f.routing.Router`.

***

<a name="loio7f651316d396400d88835adb0d021532__section_rdb_5d1_12b"/>

### Preview

   
  
Changing layouts based on the `sap.f.routing.Router` \(no visual changes to last step\)<a name="loio7f651316d396400d88835adb0d021532__fig_r1j_pst_mr"/>

 ![](loio24122e039ed14a7a874ec26d0cf51614_HiRes.png "Changing layouts based on the sap.f.routing.Router (no
					visual changes to last step)") 

***

<a name="loio7f651316d396400d88835adb0d021532__section_fd2_4dd_lbb"/>

### Coding

You can view and download all files at [SAP Fiori 2.0 App - Step 7](https://openui5.hana.ondemand.com/#/sample/sap.f.tutorial.fiori2.07/preview).

``` xml
<mvc:View
*HIGHLIGHT START*	controllerName="sap.ui.demo.fiori2.controller.App"*HIGHLIGHT END*
	displayBlock="true"
	height="100%"
	xmlns="sap.f"
	xmlns:mvc="sap.ui.core.mvc">
*HIGHLIGHT START*	<FlexibleColumnLayout
		id="flexibleColumnLayout"
		stateChange=".onStateChanged"
		backgroundDesign="Solid"
		layout="{/layout}"/>*HIGHLIGHT END*
</mvc:View>
```

We remove the hardcoded `beginColumnPages` and `endColumnPages` aggregations \(since the router will add them automatically from now on\), and we bind the `layout` property so that it can be changed easily from the controller.

``` js
*HIGHLIGHT START*sap.ui.define([
	"sap/ui/model/json/JSONModel",
	"sap/ui/core/mvc/Controller"
], function (JSONModel, Controller) {
	"use strict";

	return Controller.extend("sap.ui.demo.fiori2.controller.App", {
		onInit: function () {
			this.oOwnerComponent = this.getOwnerComponent();
			this.oRouter = this.oOwnerComponent.getRouter();
			this.oRouter.attachRouteMatched(this.onRouteMatched, this);
		},

		onRouteMatched: function (oEvent) {
			var sRouteName = oEvent.getParameter("name"),
				oArguments = oEvent.getParameter("arguments");

			// Save the current route name
			this.currentRouteName = sRouteName;
			this.currentProduct = oArguments.product;
		},

		onStateChanged: function (oEvent) {
			var bIsNavigationArrow = oEvent.getParameter("isNavigationArrow"),
				sLayout = oEvent.getParameter("layout");

			// Replace the URL with the new layout if a navigation arrow was used
			if (bIsNavigationArrow) {
				this.oRouter.navTo(this.currentRouteName, {layout: sLayout, product: this.currentProduct}, true);
			}
		},

		onExit: function () {
			this.oRouter.detachRouteMatched(this.onRouteMatched, this);
		}
	});
});*HIGHLIGHT END*
```

We access the router and bind to its `routeMatched` event. For more information, see [Router](Router_c6da1a5.md).

``` js
sap.ui.define([
	"sap/ui/model/json/JSONModel",
	"sap/ui/core/mvc/Controller",
	"sap/ui/model/Filter",
	"sap/ui/model/FilterOperator",
	'sap/ui/model/Sorter',
	'sap/m/MessageBox',
	'sap/f/library'
], function (JSONModel, Controller, Filter, FilterOperator, Sorter, MessageBox, fioriLibrary) {
	"use strict";

	return Controller.extend("sap.ui.demo.fiori2.controller.Master", {
		onInit: function () {
			this.oView = this.getView();
			this._bDescendingSort = false;
			this.oProductsTable = this.oView.byId("productsTable");
*HIGHLIGHT START*			this.oRouter = this.getOwnerComponent().getRouter();*HIGHLIGHT END*
		},

		onSearch: function (oEvent) {
			var oTableSearchState = [],
				sQuery = oEvent.getParameter("query");

			if (sQuery && sQuery.length > 0) {
				oTableSearchState = [new Filter("Name", FilterOperator.Contains, sQuery)];
			}

			this.oProductsTable.getBinding("items").filter(oTableSearchState, "Application");
		},

		onAdd: function () {
			MessageBox.show("This functionality is not ready yet.", {
				icon: MessageBox.Icon.INFORMATION,
				title: "Aw, Snap!",
				actions: [MessageBox.Action.OK]
			});
		},

		onSort: function () {
			this._bDescendingSort = !this._bDescendingSort;
			var oBinding = this.oProductsTable.getBinding("items"),
				oSorter = new Sorter("Name", this._bDescendingSort);

			oBinding.sort(oSorter);
		},

		onListItemPress: function (*HIGHLIGHT START*oEvent*HIGHLIGHT END*) {
*HIGHLIGHT START*			var productPath = oEvent.getSource().getBindingContext("products").getPath(),
				product = productPath.split("/").slice(-1).pop();*HIGHLIGHT END*

*HIGHLIGHT START*			this.oRouter.navTo("detail", {layout: fioriLibrary.LayoutType.TwoColumnsMidExpanded, product: product});*HIGHLIGHT END*
		}
	});
});
```

We change the event handler for pressing an item from the master view to use the router instead of manually manipulating the `FlexibleColumnLayout` instance. When we call the router's `navTo` method, the router itself will change the `layout` property of the `FlexibleColumnLayout`.

``` js
sap.ui.define([
	"sap/ui/core/mvc/Controller"
], function (Controller) {
	"use strict";

	return Controller.extend("sap.ui.demo.fiori2.controller.Detail", {
*HIGHLIGHT START*		onInit: function () {
			var oOwnerComponent = this.getOwnerComponent();

			this.oRouter = oOwnerComponent.getRouter();
			this.oModel = oOwnerComponent.getModel();

			this.oRouter.getRoute("master").attachPatternMatched(this._onProductMatched, this);
			this.oRouter.getRoute("detail").attachPatternMatched(this._onProductMatched, this);
		},

		_onProductMatched: function (oEvent) {
			this._product = oEvent.getParameter("arguments").product || this._product || "0";
			this.getView().bindElement({
				path: "/ProductCollection/" + this._product,
				model: "products"
			});
		},*HIGHLIGHT END*

		onEditToggleButtonPress: function() {
			var oObjectPage = this.getView().byId("ObjectPageLayout"),
				bCurrentShowFooterState = oObjectPage.getShowFooter();

			oObjectPage.setShowFooter(!bCurrentShowFooterState);
		}*HIGHLIGHT START*,

		onExit: function () {
			this.oRouter.getRoute("master").detachPatternMatched(this._onProductMatched, this);
			this.oRouter.getRoute("detail").detachPatternMatched(this._onProductMatched, this);
		}*HIGHLIGHT END*
	});
});
```

We bind the table in the detail view to reflect the currently selected product from the master view.

``` js
sap.ui.define([
	'sap/ui/core/UIComponent',
	'sap/ui/model/json/JSONModel'*HIGHLIGHT START*,
	'sap/f/library'*HIGHLIGHT END*
], function(UIComponent, JSONModel*HIGHLIGHT START*, fioriLibrary*HIGHLIGHT END*) {
	'use strict';

	return UIComponent.extend('sap.ui.demo.fiori2.Component', {

		metadata: {
			manifest: 'json'
		},

		init: function () {
*HIGHLIGHT START*			var oModel,
				oProductsModel,
				oRouter;*HIGHLIGHT END*

			UIComponent.prototype.init.apply(this, arguments);

*HIGHLIGHT START*			oModel = new JSONModel();
			this.setModel(oModel);*HIGHLIGHT END*

			// set products demo model on this sample
			oProductsModel = new JSONModel(sap.ui.require.toUrl('sap/ui/demo/mock') + '/products.json');
			oProductsModel.setSizeLimit(1000);
			this.setModel(oProductsModel, 'products');

*HIGHLIGHT START*			oRouter = this.getRouter();
			oRouter.attachBeforeRouteMatched(this._onBeforeRouteMatched, this);
			oRouter.initialize();
		},

		_onBeforeRouteMatched: function(oEvent) {
			var oModel = this.getModel(),
				sLayout = oEvent.getParameters().arguments.layout;

			// If there is no layout parameter, set a default layout (normally OneColumn)
			if (!sLayout) {
				sLayout = fioriLibrary.LayoutType.OneColumn;
			}

			oModel.setProperty("/layout", sLayout);*HIGHLIGHT END*
		}
	});
});
```

We initialize the router and bind to its `onBeforeRouteMatched` event, and we introduce a model, which will be used for the layout.

``` json
{
	"_version": "1.12.0",
	"sap.app": {
		"id": "sap.ui.demo.fiori2",
		"type": "application",
		"applicationVersion": {
			"version": "1.0.0"
		}
	},
	"sap.ui5": {
		"rootView": {
			"viewName": "sap.ui.demo.fiori2.view.App",
			"type": "XML",
			"async": true,
			"id": "fcl"
		},
		"dependencies": {
			"minUI5Version": "1.60.0",
			"libs": {
				"sap.ui.core": {},
				"sap.m": {},
				"sap.f": {},
				"sap.uxap": {}
			}
		},
		"config": {
			"fullWidth": true
		}*HIGHLIGHT START*,
		"routing": {
			"config": {
				"routerClass": "sap.f.routing.Router",
				"viewType": "XML",
				"viewPath": "sap.ui.demo.fiori2.view",
				"controlId": "flexibleColumnLayout",
				"transition": "slide",
				"bypassed": {
				},
				"async": true
			},
			"routes": [
				{
					"pattern": ":layout:",
					"name": "master",
					"target": [
						"master",
						"detail"
					]
				},
				{
					"pattern": "detail/{product}/{layout}",
					"name": "detail",
					"target": [
						"master",
						"detail"
					]
				}
			],
			"targets": {
				"master": {
					"viewName": "Master",
					"controlAggregation": "beginColumnPages"
				},
				"detail": {
					"viewName": "Detail",
					"controlAggregation": "midColumnPages"
				}
			}
		}*HIGHLIGHT END*
	}
}
```

Finally, we add the routing configuration in the `manifest.json`.

