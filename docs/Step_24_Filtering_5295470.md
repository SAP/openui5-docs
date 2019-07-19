<!-- loio5295470d7eee46c1898ee46c1b9ad763 -->

| loio |
| -----|
| 5295470d7eee46c1898ee46c1b9ad763 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/5295470d7eee46c1898ee46c1b9ad763) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/5295470d7eee46c1898ee46c1b9ad763)</div>

## Step 24: Filtering

In this step, we add a search field for our product list and define a filter that represents the search term. When searching, the list is automatically updated to show only the items that match the search term.

***

### Preview

   
  
A search field is displayed above the list<a name="loio5295470d7eee46c1898ee46c1b9ad763__fig_r1j_pst_mr"/>

 ![](loiob59b3ed9928549d4bf7e4d0f9f5b5dc8_HiRes.png "A search field is displayed above the list") 

***

<a name="loio5295470d7eee46c1898ee46c1b9ad763__section_qx5_wch_ycb"/>

### Coding

You can view and download all files at [Walkthrough - Step 24](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.24/preview).

***

<a name="loio5295470d7eee46c1898ee46c1b9ad763__section_rx5_wch_ycb"/>

### webapp/view/InvoiceList.view.xml

``` xml
<mvc:View
   controllerName="sap.ui.demo.walkthrough.controller.InvoiceList"
   xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc">
   <List
      *HIGHLIGHT START*id="invoiceList"*HIGHLIGHT END*
      class="sapUiResponsiveMargin"
      width="auto"
      items="{invoice>/Invoices}" >
      *HIGHLIGHT START*<headerToolbar>
         <Toolbar>
            <Title text="{i18n>invoiceListTitle}"/>
            <ToolbarSpacer/>
            <SearchField width="50%" search=".onFilterInvoices"/>
         </Toolbar>
      </headerToolbar>*HIGHLIGHT END*
      <items>
         <ObjectListItem>
		…
         </ObjectListItem/>
      </items>
   </List>
</mvc:View>
```

The view is extended by a search control that we add to the list of invoices. We also need to specify an ID `invoiceList` for the list control to be able to identify the list from the event handler function `onFilterInvoices` that we add to the search field. In addition, the search field is part of the list header and therefore, each change on the list binding will trigger a rerendering of the whole list, including the search field.

The `headerToolbar` aggregation replaces the simple `title` property that we used before for our list header. A toolbar control is way more flexible and can be adjusted as you like. We are now displaying the title on the left side with a `sap.m.Title` control, a spacer, and the `sap.m.SearchField` on the right.

***

### webapp/controller/InvoiceList.controller.js

``` js
sap.ui.define([
	"sap/ui/core/mvc/Controller",
	"sap/ui/model/json/JSONModel",
	"../model/formatter"*HIGHLIGHT START*,
	"sap/ui/model/Filter",
	"sap/ui/model/FilterOperator"*HIGHLIGHT END*
], function (Controller, JSONModel, formatter*HIGHLIGHT START*, Filter, FilterOperator*HIGHLIGHT END*) {
	"use strict";
	return Controller.extend("sap.ui.demo.walkthrough.controller.InvoiceList", {
		formatter: formatter, 
		onInit : function () {
			var oViewModel = new JSONModel({
				currency: "EUR"
			});
			this.getView().setModel(oViewModel, "view");
		}*HIGHLIGHT START*,
		onFilterInvoices : function (oEvent) {

			// build filter array
			var aFilter = [];
			var sQuery = oEvent.getParameter("query");
			if (sQuery) {
				aFilter.push(new Filter("ProductName", FilterOperator.Contains, sQuery));
			}

			// filter binding
			var oList = this.byId("invoiceList");
			var oBinding = oList.getBinding("items");
			oBinding.filter(aFilter);
		}*HIGHLIGHT END*
	});
});
```

We load two new dependencies for the filtering. The filter object will hold our configuration for the filter action and the `FilterOperator` is a helper type that we need in order to specify the filter.

In the `onFilterInvoices` function we construct a filter object from the search string that the user has typed in the search field. Event handlers always receive an event argument that can be used to access the parameters that the event provides. In our case the search field defines a parameter `query` that we access by calling `getParameter(“query”)` on the `oEvent` parameter.

If the query is not empty, we add a new filter object to the still empty array of filters. However, if the query is empty, we filter the binding with an empty array. This makes sure that we see all list elements again. We could also add more filters to the array, if we wanted to search more than one data field. In our example, we just search in the `ProductName` path and specify a filter operator that will search for the given query string.

The list is accessed with the ID that we have specified in the view, because the control is automatically prefixed by the view ID, we need to ask the view for the control with the helper function `byId`. On the list control we access the binding of the aggregation `items` to filter it with our newly constructed filter object. This will automatically filter the list by our search string so that only the matching items are shown when the search is triggered. The filter operator `FilterOperator.Contains` is **not** case-sensitive.

**Related information**  


[API Reference: `sap.ui.model.Filter`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.Filter.html)

[API Reference: `sap.ui.model.FilterOperator`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.FilterOperator.html)

[API Reference: `sap.m.SearchField`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.m.SearchField.html)

