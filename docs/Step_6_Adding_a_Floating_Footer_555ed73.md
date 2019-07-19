<!-- loio555ed73903b34c70a23ba13af1a5d71e -->

| loio |
| -----|
| 555ed73903b34c70a23ba13af1a5d71e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/555ed73903b34c70a23ba13af1a5d71e) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/555ed73903b34c70a23ba13af1a5d71e)</div>

## Step 6: Adding a Floating Footer

In this step, we add a floating footer to the detail page.

***

<a name="loio555ed73903b34c70a23ba13af1a5d71e__section_ed2_4dd_lbb"/>

### Preview

   
  
`ObjectPageLayout` with a floating footer<a name="loio555ed73903b34c70a23ba13af1a5d71e__fig_r1j_pst_mr"/>

 ![](loio24122e039ed14a7a874ec26d0cf51614_HiRes.png "ObjectPageLayout with a floating footer") 

***

<a name="loio555ed73903b34c70a23ba13af1a5d71e__section_fd2_4dd_lbb"/>

### Coding

You can view and download all files at [SAP Fiori 2.0 App - Step 6](https://openui5.hana.ondemand.com/#/sample/sap.f.tutorial.fiori2.06/preview).

```
<mvc:View
	displayBlock="true"
	height="100%"
	xmlns="sap.f"
	xmlns:mvc="sap.ui.core.mvc">
	<FlexibleColumnLayout id="flexibleColumnLayout"*HIGHLIGHT START* stateChange="onStateChanged"*HIGHLIGHT END* backgroundDesign="Solid">
		<beginColumnPages>
			<mvc:XMLView id="beginView" viewName="sap.ui.demo.fiori2.view.Master"/>
		</beginColumnPages>
		<midColumnPages>
			<mvc:XMLView id="detailView" viewName="sap.ui.demo.fiori2.view.Detail"/>
		</midColumnPages>
	</FlexibleColumnLayout>
</mvc:View>
```

First, we communicate changes to the layout with the use of the `stateChange` event.

```
		...
		</sections>

*HIGHLIGHT START*		<footer>
			<m:OverflowToolbar>
				<m:ToolbarSpacer/>
				<m:Button type="Accept" text="Save"/>
				<m:Button type="Reject" text="Cancel"/>
			</m:OverflowToolbar>
		</footer>*HIGHLIGHT END*
	</ObjectPageLayout>
</mvc:View>
```

We add a footer inside the `sap.uxap.ObjectPageLayout`.

``` xml
<mvc:View
*HIGHLIGHT START*	controllerName="sap.ui.demo.fiori2.controller.Detail"*HIGHLIGHT END*
	xmlns="sap.uxap"
	xmlns:m="sap.m"
	xmlns:f="sap.f"
	xmlns:form="sap.ui.layout.form"
	xmlns:mvc="sap.ui.core.mvc">
	<ObjectPageLayout
		id="ObjectPageLayout"
		showTitleInHeaderContent="true"
		alwaysShowContentHeader="false"
		preserveHeaderStateOnScroll="false"
		headerContentPinnable="true"
		isChildPage="true"
		upperCaseAnchorBar="false">
		<headerTitle>
			<ObjectPageDynamicHeaderTitle>
				<actions>
					<m:ToggleButton
						text="Edit"
						type="Emphasized*HIGHLIGHT START*"
						press=".onEditToggleButtonPress"/>*HIGHLIGHT END*
					<m:Button
						text="Delete"
						type="Transparent"/>
					<m:Button
						text="Copy"
						type="Transparent"/>
					<m:Button
						icon="sap-icon://action"
						type="Transparent"/>
				</actions>
			</ObjectPageDynamicHeaderTitle>
		</headerTitle>
		...
```

We add a `press` event handler to the *Edit* button.

``` js
*HIGHLIGHT START*sap.ui.define([
	"sap/ui/core/mvc/Controller"
], function (Controller) {
	"use strict";

	return Controller.extend("sap.ui.demo.fiori2.controller.Detail", {
		onEditToggleButtonPress: function() {
			var oObjectPage = this.getView().byId("ObjectPageLayout"),
				bCurrentShowFooterState = oObjectPage.getShowFooter();

			oObjectPage.setShowFooter(!bCurrentShowFooterState);
		}
	});
});*HIGHLIGHT END*
```

Finally, we create the controller and add a simple function to it to show and hide the footer.

