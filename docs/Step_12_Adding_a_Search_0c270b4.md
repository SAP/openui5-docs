<!-- loio0c270b45dd904429ba634656e3a37a73 -->

| loio |
| -----|
| 0c270b45dd904429ba634656e3a37a73 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/0c270b45dd904429ba634656e3a37a73) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/0c270b45dd904429ba634656e3a37a73)</div>

## Step 12: Adding a Search

We now add a search field to our bulletin board and define a filter that represents the search term. This is done similarly as in step 24 of the Walkthrough tutorial.

***

### Preview

   
  
Search field<a name="loio0c270b45dd904429ba634656e3a37a73__fig_k3l_yjj_sx"/>

 ![](loiob012fdf751b947f08cf77cf124334c9f_LowRes.png "Search field") 

***

### Coding

You can view and download all files in the *Samples* in the Demo Kit at [Testing - Step 12](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.testing.12/preview).

***

### webapp/view/Worklist.view.xml

``` xml
...
         <Table
               id="table"
               width="auto"
               class="sapUiResponsiveMargin"
               growing="true"
               items="{
               path: '/Posts',
               sorter: {
                  path: 'Title',
                  descending: false
                  }
               }"
               busyIndicatorDelay="{worklistView>/tableBusyDelay}"
               updateFinished=".onUpdateFinished">
            <headerToolbar>
               <Toolbar>
                  <Label id="tableHeader" text="{worklistView>/worklistTableTitle}"/>
                  *HIGHLIGHT START*<ToolbarSpacer />
                  <SearchField id="searchField" width="auto" search=".onFilterPosts" />*HIGHLIGHT END*
               </Toolbar>
            </headerToolbar>
...
```

We add a `ToolbarSpacer` and a `SearchField` to the `headerToolbar` of our table.

***

### webapp/controller/Worklist.controller.js

``` js
sap.ui.define([
	'./BaseController',
	'sap/ui/model/json/JSONModel',
	'../model/formatter',
	'../model/FlaggedType',
*HIGHLIGHT START*	"sap/ui/model/Filter",
	"sap/ui/model/FilterOperator",
*HIGHLIGHT END*
	'sap/m/library'
], function (BaseController, JSONModel, formatter, FlaggedType*HIGHLIGHT START*, Filter, FilterOperator*HIGHLIGHT END*, mobileLibrary) {
	"use strict";
...
		onUpdateFinished: function (oEvent) {
			// update the worklist's object counter after the table update
			var sTitle,
				oTable = oEvent.getSource(),
				iTotalItems = oEvent.getParameter("total");
			// only update the counter if the length is final and
			// the table is not empty
			if (iTotalItems && oTable.getBinding("items").isLengthFinal()) {
				sTitle = this.getResourceBundle().getText("worklistTableTitleCount", [iTotalItems]);
			} else {
				sTitle = this.getResourceBundle().getText("worklistTableTitle");
			}
			this.getModel("worklistView").setProperty("/worklistTableTitle", sTitle);
		},

		*HIGHLIGHT START*onFilterPosts: function (oEvent) {

			// build filter array
			var aFilter = [];
			var sQuery = oEvent.getParameter("query");
			if (sQuery) {
				aFilter.push(new Filter("Title", FilterOperator.Contains, sQuery));
			}

			// filter binding
			var oTable = this.byId("table");
			var oBinding = oTable.getBinding("items");
			oBinding.filter(aFilter);
		},
*HIGHLIGHT END*
...
```

To enable filtering, we extend the controller with a method that applies the search term entered in the search field to the list binding, similarly as we did for `InvoiceList.controller.js` in step 24 of the Walkthrough tutorial.

**Related information**  


[Step 42 of Walkthrough: Filtering](Step_24_Filtering_5295470.md)

