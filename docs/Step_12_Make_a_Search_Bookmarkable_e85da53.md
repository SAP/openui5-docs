<!-- loioe85da535ea19430a90c381f3c2bd748e -->

| loio |
| -----|
| e85da535ea19430a90c381f3c2bd748e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/e85da535ea19430a90c381f3c2bd748e) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/e85da535ea19430a90c381f3c2bd748e)</div>

## Step 12: Make a Search Bookmarkable

In this step we will make the search bookmarkable. This allows users to search for employees in the *Employees* table and they can bookmark their search query or share the URL.

***

### Preview

   
  
<a name="loioe85da535ea19430a90c381f3c2bd748e__fig_r1j_pst_mr"/>Search and sorting bookmarkable

 ![](loiofeb2ddddf2e347e9893512419fe11355_LowRes.png "Search and sorting bookmarkable") 

***

### Coding

You can view and download all files in the *Samples* in the Demo Kit at [Routing and Navigation - Step 12](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.tutorial.navigation.12/preview) .

***

### webapp/manifest.json

``` js
{
	"_version": "1.12.0",
	"sap.app": {
		...
	},
	"sap.ui": {
		...
	},
	"sap.ui5": {
		...
		"routing": {
			"config": {
				"routerClass": "sap.m.routing.Router",
				"type": "View",
				"viewType": "XML",
				"path": "sap.ui.demo.nav.view",
				"controlId": "app",
				"controlAggregation": "pages",
				"transition": "slide",
				"bypassed": {
					"target": "notFound"
				}
			},
			"routes": [{
				"pattern": "",
				"name": "appHome",
				"target": "home"
			}, {
				"pattern": "employees",
				"name": "employeeList",
				"target": "employees"
			}, {
				"pattern": "employees/overview*HIGHLIGHT START*:?query:*HIGHLIGHT END*",
				"name": "employeeOverview",
				"target": ["employeeOverviewTop", "employeeOverviewContent"]

			}, {
				"pattern": "employees/{employeeId}",
				"name": "employee",
				"target": "employee"
			}, {
				"pattern": "employees/{employeeId}/resume:?query:",
				"name": "employeeResume",
				"target": "employeeResume"
			}],
			"targets": {
				...
			}
		}
	}
}
```

In order to make the search bookmarkable we have to think about how the pattern of the corresponding route should match the bookmark. We decide to allow `/#/employees/overview?search=mySearchQueryString` in order to bookmark a search. Therefore, we simply extend our routing configuration a little. We add the optional `:?query:` parameter to the route `employeeOverview`. We keep in mind that we want to use `search` as the URL parameter for the search term that was entered in the search field.

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
*HIGHLIGHT START*			var oRouter = this.getRouter();*HIGHLIGHT END*

			this._oTable = this.byId("employeesTable");
			this._oVSD = null;
			this._sSortField = null;
			this._bSortDescending = false;
			this._aValidSortFields = ["EmployeeID", "FirstName", "LastName"];
			this._sSearchQuery = null;
*HIGHLIGHT START*			this._oRouterArgs = null;
*HIGHLIGHT END*

			this._initViewSettingsDialog();

*HIGHLIGHT START*			// make the search bookmarkable
			oRouter.getRoute("employeeOverview").attachMatched(this._onRouteMatched, this);*HIGHLIGHT END*

		},

*HIGHLIGHT START*		_onRouteMatched: function (oEvent) {
			// save the current query state
			this._oRouterArgs = oEvent.getParameter("arguments");
			this._oRouterArgs["?query"] = this._oRouterArgs["?query"] || {};

			// search/filter via URL hash
			this._applySearchFilter(this._oRouterArgs["?query"].search);
		},
*HIGHLIGHT END*

		onSortButtonPressed : function (oEvent) {
			this._oVSD.open();
		},

		onSearchEmployeesTable : function (oEvent) {
*HIGHLIGHT START*			var oRouter = this.getRouter();
			// update the hash with the current search term
			this._oRouterArgs["?query"].search = oEvent.getSource().getValue();
			oRouter.navTo("employeeOverview", this._oRouterArgs, true /*no history*/);*HIGHLIGHT END*
		},
		...
	});
});
```

Now we handle the optional query parameter from the `employeeOverview` route in our `EmployeeOverviewContent` controller. First we change the `onInit` function by adding an event listener for the matched event of the `employeeOverview` route. Then we buffer the current router arguments as received from the event. If a query is available, the result from `oEvent.getParameter("arguments")` will contain a `?query` property with an object of all URL parameters specified, otherwise it is undefined. If no query parameter is defined, we always initialize the query and save it to `this._oRouterArgs["?query"]`. If we have a search term query at the `search` key we continue and call `this._applySearchFilter(this._oRouterArgs["?query"].search)` to trigger a search based on the search query parameter from the URL.

Storing the `arguments` objects internally in the controller is important, because we will use the current arguments when calling `navTo()` in the search event handler `onSearchEmployeesTable` and pass on the arguments with the updated search term. We keep the URL and the UI in sync by navigating to the current target again with the current value of the search field from the event’s source. The search value is stored in `this._oRouterArgs["?query"].search` together with the other query parameters and it is passed directly to the router again

That’s it, now our search is bookmarkable and reflected in the URL. Try to access the following pages in your browser:

-   `webapp/index.html#/employees/overview`

-   `webapp/index.html#/employees/overview?search=`

-   `webapp/index.html#/employees/overview?search=an`


When you change the value in the search field, you see that the hash updates accordingly.

**Parent topic:** [Navigation and Routing](Navigation_and_Routing_1b6dcd3.md "OpenUI5 comes with a powerful routing API that helps you control the state of your application efficiently. This tutorial will illustrate all major features and APIs related to navigation and routing in OpenUI5 apps by creating a simple and easy to understand mobile app. It represents a set of best practices for applying the navigation and routing features of OpenUI5 to your applications.")

**Next:** [Step 11: Assign Multiple Targets](Step_11_Assign_Multiple_Targets_b01840e.md "In this step, we will add a new button to the home page to illustrate the usage of multiple targets for a route. When the button is pressed, a new page opens that contains two parts: a header part at the top and a content part. The content part displays a table of employees that can be sorted and searched. We will use the array notation in the routing configuration to assign multiple targets to a route - a feature that we have not yet introduced.")

**Previous:** [Step 13: Make Table Sorting Bookmarkable](Step_13_Make_Table_Sorting_Bookmarkable_3975987.md "In this step, we will create a button at the top of the table which will change the sorting of the table. When the current sorting state of the table is changed, the sorting state will be reflected in the URL. This illustrates how to make the table sorting bookmarkable.")

