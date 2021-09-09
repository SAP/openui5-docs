<!-- loiodf8c9c3d79b54c928855162bafcd88ee -->

| loio |
| -----|
| df8c9c3d79b54c928855162bafcd88ee |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/df8c9c3d79b54c928855162bafcd88ee) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/df8c9c3d79b54c928855162bafcd88ee)</div>

## Step 15: Nested Views

Our panel content is getting more and more complex and now it is time to move the panel content to a separate view. With that approach, the application structure is much easier to understand, and the individual parts of the app can be reused.

***

### Preview

   
  
<a name="loiodf8c9c3d79b54c928855162bafcd88ee__fig_r1j_pst_mr"/>The panel content is now refactored to a separate view \(No visual changes to last step\)

 ![](loiodc7fa7048c8b4083a9732901350a0c6d_HiRes.png "The panel content is now refactored to a separate view (No visual changes to
					last step)") 

***

### Coding

You can view and download all files at [Walkthrough - Step 15](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.15/preview).

``` xml
<mvc:View
	controllerName="sap.ui.demo.walkthrough.controller.App"
	xmlns="sap.m"
	xmlns:mvc="sap.ui.core.mvc"
	displayBlock="true">
	<Shell>
		<App class="myAppDemoWT">
			<pages>
				<Page title="{i18n>homePageTitle}">
					<content>
*HIGHLIGHT START*						<mvc:XMLView viewName="sap.ui.demo.walkthrough.view.HelloPanel"/>*HIGHLIGHT END*
					</content>
				</Page>
			</pages>
		</App>
	</Shell>
</mvc:View>

```

Instead of putting the panel and its content directly into our `App` view, we will move it to a new separate `HelloPanel` view. We refer to this using an `XMLView` tag in the content aggregation of the panel.

***

### webapp/view/HelloPanel.view.xml \(New\)

``` xml
*HIGHLIGHT START*<mvc:View
   controllerName="sap.ui.demo.walkthrough.controller.HelloPanel"
   xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc">
   <Panel
      headerText="{i18n>helloPanelTitle}"
      class="sapUiResponsiveMargin"
      width="auto" >
      <content>
         <Button
            text="{i18n>showHelloButtonText}"
            press=".onShowHello"
            class="myCustomButton"/>
         <Input
            value="{/recipient/name}"
            valueLiveUpdate="true"
            width="60%"/>
         <FormattedText
            htmlText="Hello {/recipient/name}"
            class="sapUiSmallMargin sapThemeHighlight-asColor myCustomText"/>
      </content>
   </Panel>
</mvc:View>*HIGHLIGHT END*
```

The whole content for the panel is now added to the new file `HelloPanel.view.xml`. We also specify the controller for the view by setting the `controllerName` attribute of the XML view.

***

### webapp/controller/HelloPanel.controller.js \(New\)

``` js
*HIGHLIGHT START*sap.ui.define([
   "sap/ui/core/mvc/Controller",
   "sap/m/MessageToast"
], function (Controller, MessageToast) {
   "use strict";
   return Controller.extend("sap.ui.demo.walkthrough.controller.HelloPanel", {
      onShowHello : function () {
         // read msg from i18n model
         var oBundle = this.getView().getModel("i18n").getResourceBundle();
         var sRecipient = this.getView().getModel().getProperty("/recipient/name");
         var sMsg = oBundle.getText("helloMsg", [sRecipient]);
         // show message
         MessageToast.show(sMsg);
      }
   });
});*HIGHLIGHT END*
```

To have a reusable asset, the method `onShowHello` is also moved from the app controller to the `HelloPanel` controller.

***

### webapp/controller/App.controller.js

``` js
sap.ui.define([
   "sap/ui/core/mvc/Controller"
], function (Controller) {
   "use strict";
   return Controller.extend("sap.ui.demo.walkthrough.controller.App", {
   });
});
```

We have now moved everything out of the app view and controller. The app controller remains an empty stub for now, we will use it later to add more functionality.

**Parent topicColonSymbol** [Walkthrough](Walkthrough_3da5f4b.md "In this tutorial we will introduce you to all major development paradigms of OpenUI5.")

**Previous topicColonSymbol** [Step 14: Custom CSS and Theme Colors](Step_14_Custom_CSS_and_Theme_Colors_723f4b2.md "Sometimes we need to define some more fine-granular layouts and this is when we can use the flexibility of CSS by adding custom style classes to controls and style them as we like.")

**Next topicColonSymbol** [Step 16: Dialogs and Fragments](Step_16_Dialogs_and_Fragments_4da7298.md "In this step, we will take a closer look at another element which can be used to assemble views: the fragment.")

