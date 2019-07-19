<!-- loioa59b3de038874f879cf20bfc3287bd7c -->

| loio |
| -----|
| a59b3de038874f879cf20bfc3287bd7c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/a59b3de038874f879cf20bfc3287bd7c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/a59b3de038874f879cf20bfc3287bd7c)</div>

## Step 10: Adding More Pages

In this step, we create an additional page that is displayed in a separate fullscreen column.

***

<a name="loioa59b3de038874f879cf20bfc3287bd7c__section_yfh_d31_12b"/>

### Preview

   
  
Additional page displayed in a separate fullscreen column<a name="loioa59b3de038874f879cf20bfc3287bd7c__fig_zfh_d31_12b"/>

 ![](loio41f6ae105130408ca78197f7c528e388_HiRes.gif "Additional page displayed in a separate fullscreen column") 

***

<a name="loioa59b3de038874f879cf20bfc3287bd7c__section_fd2_4dd_lbb"/>

### Coding

You can view and download all files at [SAP Fiori 2.0 App - Step 10](https://openui5.hana.ondemand.com/#/sample/sap.f.tutorial.fiori2.10/preview).

``` xml
*HIGHLIGHT START*<mvc:View
	xmlns="sap.m"
	xmlns:f="sap.f"
	xmlns:mvc="sap.ui.core.mvc">
	<f:DynamicPage toggleHeaderOnTitleClick="false">
		<!-- DynamicPage Title -->
		<f:title>
			<f:DynamicPageTitle>
				<f:heading>
					<Title text="About supplier"/>
				</f:heading>
			</f:DynamicPageTitle>
		</f:title>
	</f:DynamicPage>
</mvc:View>*HIGHLIGHT END*
```

We create a simple additional page view.

``` json
			...
			"routes": [
*HIGHLIGHT START*				{
					"pattern": "page2",
					"name": "page2",
					"target": "page2",
					"layout": "EndColumnFullScreen"
				},*HIGHLIGHT END*
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
				},
				{
					"pattern": "detail/{product}/detailDetail/{supplier}/{layout}",
					"name": "detailDetail",
					"target": [
						"master",
						"detail",
						"detailDetail"
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
				},
				"detailDetail": {
					"viewName": "DetailDetail",
					"controlAggregation": "endColumnPages"
				}*HIGHLIGHT START*,
				"page2": {
					"viewName": "AboutPage",
					"controlAggregation": "endColumnPages"
				}*HIGHLIGHT END*
			}
		}
	}
}
```

Similar to the previous step, we add the additional page view to our existing routes in the `manifest.json`.

``` xml
<mvc:View
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
*HIGHLIGHT START*		<content>
			<m:Link text="Navigate to next page…" press=".handleAboutPress"/>
		</content>*HIGHLIGHT END*
	</DynamicPage>
</mvc:View>
```

We add a link in the detail-detail page with a `press` event handler.

``` js
sap.ui.define([
	"sap/ui/model/json/JSONModel",
	"sap/ui/core/mvc/Controller"*HIGHLIGHT START*,
	'sap/f/library'*HIGHLIGHT END*
], function (JSONModel, Controller*HIGHLIGHT START*, fioriLibrary*HIGHLIGHT END*) {
	"use strict";

	return Controller.extend("sap.ui.demo.fiori2.controller.DetailDetail", {
		onInit: function () {
			var oOwnerComponent = this.getOwnerComponent();

			this.oRouter = oOwnerComponent.getRouter();
			this.oModel = oOwnerComponent.getModel();

			this.oRouter.getRoute("detailDetail").attachPatternMatched(this._onPatternMatch, this);
		},

*HIGHLIGHT START*		handleAboutPress: function () {
			this.oRouter.navTo("page2", {layout: fioriLibrary.LayoutType.EndColumnFullScreen});
		},*HIGHLIGHT END*

		_onPatternMatch: function (oEvent) {
		...
```

Finally, we add a `handleAboutPress` function in the detail-detail page controller to navigate to the additional page without passing any data this time.

