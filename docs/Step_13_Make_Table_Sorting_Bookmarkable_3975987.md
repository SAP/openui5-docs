<!-- loio39759878ae4f48dcad0cf34da1d299f0 -->

| loio |
| -----|
| 39759878ae4f48dcad0cf34da1d299f0 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/39759878ae4f48dcad0cf34da1d299f0) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/39759878ae4f48dcad0cf34da1d299f0)</div>

## Step 13: Make Table Sorting Bookmarkable

In this step, we will create a button at the top of the table which will change the sorting of the table. When the current sorting state of the table is changed, the sorting state will be reflected in the URL. This illustrates how to make the table sorting bookmarkable.

***

### Preview

   
  
Bookmarkable search and sorting<a name="loio39759878ae4f48dcad0cf34da1d299f0__fig_r1j_pst_mr"/>

 ![](loio7ec54ef9b041497aaa70694e80016a9c_LowRes.png "Bookmarkable search and sorting") 

***

### Coding

You can view and download all files in the *Samples* in the Demo Kit at [Routing and Navigation - Step 13](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.tutorial.navigation.13/preview).

***

### webapp/controller/employee/overview/EmployeeOverviewContent.controller.js

``` js
sap.ui.define([
	"sap/ui/demo/nav/controller/BaseController",
	"sap/ui/model/Filter",
	"sap/ui/model/FilterOperator",
	"sap/ui/model/Sorter",
	"sap/m/ViewSettingsDialog",
	"sap/m/ViewSettingsItem"
], function(
	BaseController,
	Filter,
	FilterOperator,
	Sorter,
	ViewSettingsDialog,
	ViewSettingsItem
) {
	"use strict";
	return BaseController.extend("sap.ui.demo.nav.controller.employee.overview.EmployeeOverviewContent", {
		onInit: function () {
			...
		},
		_onRouteMatched : function (oEvent) {
			// save the current query state
			this._oRouterArgs = oEvent.getParameter("arguments");
			this._oRouterArgs.query = this._oRouterArgs["?query"] || {};
			delete this._oRouterArgs["?query"];
			if (this._oRouterArgs.query) {
				// search/filter via URL hash
				this._applySearchFilter(this._oRouterArgs.query.search);
				*HIGHLIGHT START*// sorting via URL hash
				this._applySorter(this._oRouterArgs.query.sortField, this._oRouterArgs.query.sortDescending);*HIGHLIGHT END*
			}
		},
		...
		_initViewSettingsDialog : function () {
			var oRouter = this.getRouter();
			this._oVSD = new sap.m.ViewSettingsDialog("vsd", {
				confirm: function (oEvent) {
					var oSortItem = oEvent.getParameter("sortItem");
					*HIGHLIGHT START*this._oRouterArgs.query.sortField = oSortItem.getKey();
					this._oRouterArgs.query.sortDescending = oEvent.getParameter("sortDescending");
					oRouter.navTo("employeeOverview",this._oRouterArgs, true /*without history*/);*HIGHLIGHT END*
				}.bind(this) 
			});
			...
		},
		...
	});
});
```

We enhance the `EmployeeOverviewContent` controller further to add support for bookmarking the table’s sorting options. We expect two query parameters `sortField` and `sortDescending` from the URL for configuring the sorting of the table. In the matched handler of the route `employeeOverview` we add an additional call to `this._applySorter(this._oRouterArgs.query.sortField, this._oRouterArgs.query.sortDescending)`. This triggers the sorting action based on the two query parameters `sortField` and `sortDescending` from the URL.

Next we change the `confirm` event handlers of our `ViewSettingsDialog`. The `confirm` handler updates the current router arguments with the parameters from the event accordingly. Then we call `oRouter.navTo("employeeOverview",this._oRouterArgs, true)` with the updated router arguments to persist the new sorting parameters in the URL. Both the previous arguments \(i.e. `search`\) and the new arguments for the sorting will then be handled by the matched event handler for the `employeeOverview` route.

Congratulations! Even the sorting options of the table can now be bookmarked. Try to access the following pages:

-   `webapp/index.html#/employees/overview?sortField=EmployeeID&sortDescending=true`

-   `webapp/index.html#/employees/overview?search=an&sortField=EmployeeID&sortDescending=true`


When changing the table’s sorting options, you will see that the hash updates accordingly.

