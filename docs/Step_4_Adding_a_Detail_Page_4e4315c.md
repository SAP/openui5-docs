<!-- loio4e4315cef89e48ceb60b4dc12f5be2d2 -->

| loio |
| -----|
| 4e4315cef89e48ceb60b4dc12f5be2d2 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/4e4315cef89e48ceb60b4dc12f5be2d2) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/4e4315cef89e48ceb60b4dc12f5be2d2)</div>

## Step 4: Adding a Detail Page

In this step, we add an empty detail page.

***

<a name="loio4e4315cef89e48ceb60b4dc12f5be2d2__section_ed2_4dd_lbb"/>

### Preview

   
  
Master Page with Empty Detail Page<a name="loio4e4315cef89e48ceb60b4dc12f5be2d2__fig_r1j_pst_mr"/>

 ![](loio10dec0cd47ca4a6fb9ce1caf2ba768e3_HiRes.gif "Master Page with Empty Detail Page") 

***

<a name="loio4e4315cef89e48ceb60b4dc12f5be2d2__section_fd2_4dd_lbb"/>

### Coding

You can view and download all files at [SAP Fiori 2.0 App - Step 4](https://openui5.hana.ondemand.com/#/sample/sap.f.tutorial.fiori2.04/preview).

``` xml
*HIGHLIGHT START*<mvc:View
	xmlns:mvc="sap.ui.core.mvc">
</mvc:View>*HIGHLIGHT END*
```

First, we create a blank detail page.

``` xml
<mvc:View
	displayBlock="true"
	height="100%"
	xmlns="sap.f"
	xmlns:mvc="sap.ui.core.mvc">
	<FlexibleColumnLayout id="flexibleColumnLayout" backgroundDesign="Solid">
		<beginColumnPages>
			<mvc:XMLView id="beginView" viewName="sap.ui.demo.fiori2.view.Master"/>
		</beginColumnPages>
*HIGHLIGHT START*		<midColumnPages>
			<mvc:XMLView id="detailView" viewName="sap.ui.demo.fiori2.view.Detail"/>
		</midColumnPages>*HIGHLIGHT END*
	</FlexibleColumnLayout>
</mvc:View>
```

We add the detail page in `FlexibleColumnLayout's` `midColumnPages` aggregation in the `App.view.xml` file. This way the detail page will be displayed in the middle column.

``` xml
		...
		<!-- DynamicPage Content -->
					...

					...
					<items>
						<ColumnListItem type="Navigation"*HIGHLIGHT START* press=".onListItemPress"*HIGHLIGHT END*>
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
					...
```

We add a `press` handler to each `ColumnListItem` in the `Master.view.xml`.

``` js
sap.ui.define([
	"sap/ui/model/json/JSONModel",
	"sap/ui/core/mvc/Controller",
	"sap/ui/model/Filter",
	"sap/ui/model/FilterOperator",
	'sap/ui/model/Sorter',
	'sap/m/MessageBox'*HIGHLIGHT START*,
	'sap/f/library'*HIGHLIGHT END*
], function (JSONModel, Controller, Filter, FilterOperator, Sorter, MessageBox*HIGHLIGHT START*, fioriLibrary*HIGHLIGHT END*) {
	"use strict";
		...

		...
		onSort: function () {
			this._bDescendingSort = !this._bDescendingSort;
			var oBinding = this.oProductsTable.getBinding("items"),
				oSorter = new Sorter("Name", this._bDescendingSort);

			oBinding.sort(oSorter);
		}*HIGHLIGHT START*,

		onListItemPress: function () {
			var oFCL = this.oView.getParent().getParent();

			oFCL.setLayout(fioriLibrary.LayoutType.TwoColumnsMidExpanded);
		}*HIGHLIGHT END*
	});
});
```

In the `Master.controller.js`, we attach a `onListItemPress` function to the `press` handler, which changes the `layout` to `TwoColumnsBeginExpanded`. This means that there are going to be two columns, where the first one is larger than the second. For more information on the available layout types, see [Types of Layout](Types_of_Layout_3b9f760.md).

