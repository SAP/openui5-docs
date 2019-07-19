<!-- loio0830bce271bf42d98c2740bed43d435d -->

| loio |
| -----|
| 0830bce271bf42d98c2740bed43d435d |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/0830bce271bf42d98c2740bed43d435d) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/0830bce271bf42d98c2740bed43d435d)</div>

## Step 3: Using Dynamic Page for the Master View

In this step, we create the master view of the app using `sap.f.DynamicPage` control.

***

<a name="loio0830bce271bf42d98c2740bed43d435d__section_ed2_4dd_lbb"/>

### Preview

   
  
Master page with `sap.f.DynamicPage`<a name="loio0830bce271bf42d98c2740bed43d435d__fig_r1j_pst_mr"/>

 ![](loiob31948bf54134343bfcb5dc64e00a1e1_HiRes.gif "Master page with sap.f.DynamicPage") 

***

<a name="loio0830bce271bf42d98c2740bed43d435d__section_fd2_4dd_lbb"/>

### Coding

You can view and download all files at [SAP Fiori 2.0 App - Step 3](https://openui5.hana.ondemand.com/#/sample/sap.f.tutorial.fiori2.03/preview).

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
				"sap.ui.core": {}*HIGHLIGHT START*,
				"sap.m": {},*HIGHLIGHT END*
				"sap.f": {}
			}
		},
		"config": {
			"fullWidth": true
		}
	}
}
```

First, we add the `sap.m` library as a dependency in the `manifest.json`.

``` html
	...
	<script id="sap-ui-bootstrap"
		src="https://openui5.hana.ondemand.com/resources/sap-ui-core.js"
		data-sap-ui-theme="sap_belize"
		data-sap-ui-resourceroots='{
			"sap.ui.demo.fiori2": *HIGHLIGHT START*"./",
			"sap.ui.demo.mock": "https://openui5.hana.ondemand.com/test-resources/sap/ui/documentation/sdk/"*HIGHLIGHT END*
		}'
		data-sap-ui-oninit="module:sap/ui/core/ComponentSupport"
		data-sap-ui-compatVersion="edge"
		data-sap-ui-async="true"
		data-sap-ui-frameOptions="trusted">
	</script>
	...
```

We add the link to the mock data that is used in the app.

``` js
sap.ui.define([
	'sap/ui/core/UIComponent'*HIGHLIGHT START*,
	'sap/ui/model/json/JSONModel'*HIGHLIGHT END*
], function(UIComponent*HIGHLIGHT START*, JSONModel*HIGHLIGHT END*) {
	'use strict';

	return UIComponent.extend('sap.ui.demo.fiori2.Component', {

		metadata: {
			manifest: 'json'
		}*HIGHLIGHT START*,

		init: function () {
			var oProductsModel;

			UIComponent.prototype.init.apply(this, arguments);

			// set products demo model on this sample
			oProductsModel = new JSONModel(sap.ui.require.toUrl('sap/ui/demo/mock') + '/products.json');
			oProductsModel.setSizeLimit(1000);
			this.setModel(oProductsModel, 'products');
		}*HIGHLIGHT END*
	});
});
```

We create the `init` method in the `Component.js` to set the model.

``` xml
*HIGHLIGHT START*<mvc:View
	controllerName="sap.ui.demo.fiori2.controller.Master"
	xmlns="sap.m"
	xmlns:f="sap.f"
	xmlns:mvc="sap.ui.core.mvc">
	<f:DynamicPage id="dynamicPageId" toggleHeaderOnTitleClick="false">
		<!-- DynamicPage Title -->
		<f:title>
			<f:DynamicPageTitle>
				<f:heading>
					<Title text="Products ({products>/ProductCollectionStats/Counts/Total})"/>
				</f:heading>
			</f:DynamicPageTitle>
		</f:title>

		<!-- DynamicPage Content -->
		<f:content>
			<VBox fitContainer="true">
				<OverflowToolbar class="sapFDynamicPageAlignContent">
					<ToolbarSpacer/>
					<SearchField search=".onSearch" width="17.5rem"/>
					<OverflowToolbarButton icon="sap-icon://add" text="Add" type="Transparent" press=".onAdd"/>
					<OverflowToolbarButton icon="sap-icon://sort" text="Sort" type="Transparent" press=".onSort"/>
				</OverflowToolbar>
				<Table
					id="productsTable"
					inset="false"
					items="{
						path: 'products>/ProductCollection',
						sorter: {
							path: 'Name'
						}
					}"
					class="sapFDynamicPageAlignContent"
					width="auto">
					<columns>
						<Column width="12em">
							<Text text="Product"/>
						</Column>
						<Column	hAlign="End">
							<Text text="Price"/>
						</Column>
					</columns>
					<items>
						<ColumnListItem type="Navigation">
							<cells>
								<ObjectIdentifier title="{products>Name}" text="{products>ProductId}"/>
								<ObjectNumber
									number="{
										parts:[
											{path:'products>Price'},
											{path:'products>CurrencyCode'}
										],
										type: 'sap.ui.model.type.Currency',
										formatOptions: {showMeasure: false}
									}"
									unit="{products>CurrencyCode}"/>
							</cells>
						</ColumnListItem>
					</items>
				</Table>
			</VBox>
		</f:content>

		<!-- DynamicPage Footer -->
		<f:footer>
			<OverflowToolbar>
				<ToolbarSpacer/>
				<Button type="Accept" text="Accept"/>
				<Button type="Reject" text="Reject"/>
			</OverflowToolbar>
		</f:footer>
	</f:DynamicPage>
</mvc:View>*HIGHLIGHT END*
```

We create the master view using `sap.f.DynamicPage`. The page consists of a list with all products.

``` xml
<mvc:View
	displayBlock="true"
	height="100%"
	xmlns="sap.f"
	xmlns:mvc="sap.ui.core.mvc">
	<FlexibleColumnLayout id="flexibleColumnLayout" backgroundDesign="Solid"*HIGHLIGHT START*>
		<beginColumnPages>
			<mvc:XMLView id="beginView" viewName="sap.ui.demo.fiori2.view.Master"/>
		</beginColumnPages>
	</FlexibleColumnLayout>*HIGHLIGHT END*
</mvc:View>
```

We add the master view in `FlexibleColumnLayout's` `beginColumnPages` aggregation.

``` js
*HIGHLIGHT START*sap.ui.define([
	"sap/ui/model/json/JSONModel",
	"sap/ui/core/mvc/Controller",
	"sap/ui/model/Filter",
	"sap/ui/model/FilterOperator",
	'sap/ui/model/Sorter',
	'sap/m/MessageBox'
], function (JSONModel, Controller, Filter, FilterOperator, Sorter, MessageBox) {
	"use strict";

	return Controller.extend("sap.ui.demo.fiori2.controller.Master", {
		onInit: function () {
			this.oView = this.getView();
			this._bDescendingSort = false;
			this.oProductsTable = this.oView.byId("productsTable");
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
			MessageBox.information("This functionality is not ready yet.", {title: "Aw, Snap!"});
		},

		onSort: function () {
			this._bDescendingSort = !this._bDescendingSort;
			var oBinding = this.oProductsTable.getBinding("items"),
				oSorter = new Sorter("Name", this._bDescendingSort);

			oBinding.sort(oSorter);
		}
	});
});*HIGHLIGHT END*
```

We create the master controller that provides a basic search and sort functionality for the products listed in the master page.

