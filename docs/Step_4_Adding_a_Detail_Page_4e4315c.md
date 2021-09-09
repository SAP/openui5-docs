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

   
  
<a name="loio4e4315cef89e48ceb60b4dc12f5be2d2__fig_r1j_pst_mr"/>Master Page with Empty Detail Page

 ![](loio10dec0cd47ca4a6fb9ce1caf2ba768e3_HiRes.gif "Master Page with Empty Detail Page") 

***

<a name="loio4e4315cef89e48ceb60b4dc12f5be2d2__section_fd2_4dd_lbb"/>

### Coding

You can view and download all files at [Flexible Column Layout App - Step 4](https://openui5.hana.ondemand.com/#/sample/sap.f.tutorial.fiori2.04/preview).

***

<a name="loio4e4315cef89e48ceb60b4dc12f5be2d2__section_a5b_clj_l4b"/>

### webapp/view/Detail.view.xml \[NEW\]

``` xml
*HIGHLIGHT START*<mvc:View
	xmlns:mvc="sap.ui.core.mvc">
</mvc:View>*HIGHLIGHT END*
```

First, we create a blank detail page.

***

<a name="loio4e4315cef89e48ceb60b4dc12f5be2d2__section_t3z_1lj_l4b"/>

### webapp/view/App.view.xml \[MODIFY\]

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

***

<a name="loio4e4315cef89e48ceb60b4dc12f5be2d2__section_xw1_1lj_l4b"/>

### webapp/view/Master.view.xml \[MODIFY\]

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

***

<a name="loio4e4315cef89e48ceb60b4dc12f5be2d2__section_nxz_ykj_l4b"/>

### webapp/controller/Master.controller.js \[MODIFY\]

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

**Parent topicColonSymbol** [Flexible Column Layout App](Flexible_Column_Layout_App_c4de2df.md "In this tutorial, we showcase how to structure your OpenUI5 app using the layout patterns that comply with the SAP Fiori design guidelines.")

**Previous topicColonSymbol** [Step 3: Using Dynamic Page for the Master View](Step_3_Using_Dynamic_Page_for_the_Master_View_0830bce.md "In this step, we create the master view of the app using sap.f.DynamicPage control.")

**Next topicColonSymbol** [Step 5: Using Object Page Layout as a Detail Page](Step_5_Using_Object_Page_Layout_as_a_Detail_Page_d1ffe61.md "In this step, we add sap.uxap.ObjectPageLayout to the detail page to display more information about each product.")

