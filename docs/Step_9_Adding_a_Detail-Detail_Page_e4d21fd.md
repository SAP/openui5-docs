<!-- loioe4d21fd03edb49da82cbaab9dbd274e8 -->

| loio |
| -----|
| e4d21fd03edb49da82cbaab9dbd274e8 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/e4d21fd03edb49da82cbaab9dbd274e8) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/e4d21fd03edb49da82cbaab9dbd274e8)</div>

## Step 9: Adding a Detail-Detail Page

In this step, we create a detail-detail page using `sap.f.DynamicPage`, which is opened by choosing a supplier from the detail page.

***

<a name="loioe4d21fd03edb49da82cbaab9dbd274e8__section_yfh_d31_12b"/>

### Preview

   
  
Detail-detail page displaying the name of the selected supplier<a name="loioe4d21fd03edb49da82cbaab9dbd274e8__fig_zfh_d31_12b"/>

 ![](loio30466794b2164305a9693ccd23af0380_HiRes.gif "Detail-detail page displaying the name of the selected supplier") 

***

<a name="loioe4d21fd03edb49da82cbaab9dbd274e8__section_fd2_4dd_lbb"/>

### Coding

You can view and download all files at [SAP Fiori 2.0 App - Step 9](https://openui5.hana.ondemand.com/#/sample/sap.f.tutorial.fiori2.09/preview).

``` xml
*HIGHLIGHT START*<mvc:View
	controllerName="sap.ui.demo.fiori2.controller.DetailDetail"
	xmlns="sap.f"
	xmlns:m="sap.m"
	xmlns:mvc="sap.ui.core.mvc">
	<DynamicPage toggleHeaderOnTitleClick="false">
		<title>
			<DynamicPageTitle>
				<heading>
					<m:FlexBox wrap="Wrap" fitContainer="true" alignItems="Center">
						<m:Title text="{products>text}" wrapping="true" class="sapUiTinyMarginEnd"/>
					</m:FlexBox>
				</heading>
			</DynamicPageTitle>
		</title>
	</DynamicPage>
</mvc:View>*HIGHLIGHT END*
```

We create a detail-detail page view using `sap.f.DynamicPage` with only a title.

``` js
*HIGHLIGHT START*sap.ui.define([
	"sap/ui/model/json/JSONModel",
	"sap/ui/core/mvc/Controller"
], function (JSONModel, Controller) {
	"use strict";

	return Controller.extend("sap.ui.demo.fiori2.controller.DetailDetail", {
		onInit: function () {
			var oOwnerComponent = this.getOwnerComponent();

			this.oRouter = oOwnerComponent.getRouter();
			this.oModel = oOwnerComponent.getModel();

			this.oRouter.getRoute("detailDetail").attachPatternMatched(this._onPatternMatch, this);
		},

		_onPatternMatch: function (oEvent) {
			this._supplier = oEvent.getParameter("arguments").supplier || this._supplier || "0";
			this._product = oEvent.getParameter("arguments").product || this._product || "0";

			this.getView().bindElement({
				path: "/ProductCollectionStats/Filters/1/values/" + this._supplier,
				model: "products"
			});
		},

		onExit: function () {
			this.oRouter.getRoute("detailDetail").detachPatternMatched(this._onPatternMatch, this);
		}
	});
});*HIGHLIGHT END*
```

We create the detail-detail page controller.

``` json
			...
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
				}*HIGHLIGHT START*,
				{
					"pattern": "detail/{product}/detailDetail/{supplier}/{layout}",
					"name": "detailDetail",
					"target": [
						"master",
						"detail",
						"detailDetail"
					]
				}*HIGHLIGHT END*
			],
			"targets": {
				"master": {
					"viewName": "Master",
					"controlAggregation": "beginColumnPages"
				},
				"detail": {
					"viewName": "Detail",
					"controlAggregation": "midColumnPages"
				}*HIGHLIGHT START*,
				"detailDetail": {
					"viewName": "DetailDetail",
					"controlAggregation": "endColumnPages"
				}*HIGHLIGHT END*
			}
		}
	}
}
```

We add the detail-detail page to our existing routes in the `manifest.json`.

``` xml
			...
			<ObjectPageSection title="Suppliers">
				<subSections>
					<ObjectPageSubSection>
						<blocks>
							<m:Table
								id="suppliersTable"
								items="{path : 'products>/ProductCollectionStats/Filters/1/values'}">
								<m:columns>
									<m:Column/>
								</m:columns>
								<m:items>
									<m:ColumnListItem type="Navigation"*HIGHLIGHT START* press=".onSupplierPress"*HIGHLIGHT END*>
										<m:cells>
											<m:ObjectIdentifier text="{products>text}"/>
										</m:cells>
									</m:ColumnListItem>
								</m:items>
							</m:Table>
						</blocks>
					</ObjectPageSubSection>
				</subSections>
			</ObjectPageSection>
		</sections>
		...
```

We add a `press` event handler for each item in the *SUPPLIERS* table in the detail page.

``` js
sap.ui.define([
	"sap/ui/core/mvc/Controller"*HIGHLIGHT START*,
	'sap/f/library'*HIGHLIGHT END*
], function (Controller*HIGHLIGHT START*, fioriLibrary*HIGHLIGHT END*) {
	"use strict";

	return Controller.extend("sap.ui.demo.fiori2.controller.Detail", {
		onInit: function () {
			var oOwnerComponent = this.getOwnerComponent();

			this.oRouter = oOwnerComponent.getRouter();
			this.oModel = oOwnerComponent.getModel();

			this.oRouter.getRoute("master").attachPatternMatched(this._onProductMatched, this);
			this.oRouter.getRoute("detail").attachPatternMatched(this._onProductMatched, this);
*HIGHLIGHT START*			this.oRouter.getRoute("detailDetail").attachPatternMatched(this._onProductMatched, this);*HIGHLIGHT END*
		},

*HIGHLIGHT START*		onSupplierPress: function (oEvent) {
			var supplierPath = oEvent.getSource().getBindingContext("products").getPath(),
				supplier = supplierPath.split("/").slice(-1).pop();

			this.oRouter.navTo("detailDetail", {layout: fioriLibrary.LayoutType.ThreeColumnsMidExpanded, supplier: supplier, product: this._product});
		},*HIGHLIGHT END*

		_onProductMatched: function (oEvent) {
		...
```

We add an `onSupplierPress` function in the detail page controller in order to pass the data for the selected supplier and navigate to the detail-detail page.

``` js
		...
		onRouteMatched: function (oEvent) {
			var sRouteName = oEvent.getParameter("name"),
				oArguments = oEvent.getParameter("arguments");

			// Save the current route name
			this.currentRouteName = sRouteName;
			this.currentProduct = oArguments.product;
*HIGHLIGHT START*			this.currentSupplier = oArguments.supplier;*HIGHLIGHT END*
		},

		onStateChanged: function (oEvent) {
			var bIsNavigationArrow = oEvent.getParameter("isNavigationArrow"),
				sLayout = oEvent.getParameter("layout");

			// Replace the URL with the new layout if a navigation arrow was used
			if (bIsNavigationArrow) {
				this.oRouter.navTo(this.currentRouteName, {layout: sLayout, product: this.currentProduct*HIGHLIGHT START*, supplier: this.currentSupplier*HIGHLIGHT END*}, true);
			}
		},

		onExit: function () {
			this.oRouter.detachRouteMatched(this.onRouteMatched, this);
		}
	});
});
```

Finally, we pass data for the supplier in the detail-detail page.

