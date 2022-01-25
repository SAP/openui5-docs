<!-- loio354f98ed2b514ba9960556333428d35e -->

| loio |
| -----|
| 354f98ed2b514ba9960556333428d35e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/354f98ed2b514ba9960556333428d35e) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/354f98ed2b514ba9960556333428d35e)</div>

## Step 17: Fragment Callbacks

Now that we have integrated the dialog, it's time to add some user interaction. The user will definitely want to close the dialog again at some point, so we add a button to close the dialog and assign an event handler.

***

### Preview

   
  
<a name="loio354f98ed2b514ba9960556333428d35e__fig_r1j_pst_mr"/>The dialog now has an "OK" button

 ![](loio2a0aee6164b24340b0d34a0515c82f19_HiRes.png "The dialog now has an "OK" button") 

***

### Coding

You can view and download all files at [Walkthrough - Step 17](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.17/preview).

``` js
sap.ui.define([
	"sap/ui/core/mvc/Controller",
	"sap/m/MessageToast",
	"sap/ui/core/Fragment"
], function (Controller, MessageToast, Fragment) {
	"use strict";

	return Controller.extend("sap.ui.demo.walkthrough.controller.HelloPanel", {

		onShowHello : function () {
			// read msg from i18n model
			var oBundle = this.getView().getModel("i18n").getResourceBundle();
			var sRecipient = this.getView().getModel().getProperty("/recipient/name");
			var sMsg = oBundle.getText("helloMsg", [sRecipient]);

			// show message
			MessageToast.show(sMsg);
		},

		onOpenDialog : function () {

			if (!this.pDialog) {
				this.pDialog = this.loadFragment({
					name: "sap.ui.demo.walkthrough.view.HelloDialog"
				});
			} 
			this.pDialog.then(function(oDialog) {
				oDialog.open();
			});
		}*HIGHLIGHT START*,

		onCloseDialog : function () {
			// note: We don't need to chain to the pDialog promise, since this event-handler
			// is only called from within the loaded dialog itself.
			this.byId("helloDialog").close();
		}*HIGHLIGHT END*
	});

});
```

The event handler function is put into the same controller file and it closes the dialog by accessing the internal helper function that returns the dialog.

***

### webapp/view/HelloDialog.fragment.xml

``` xml
<core:FragmentDefinition
   xmlns="sap.m"
   xmlns:core="sap.ui.core" >
   <Dialog
      id="helloDialog"
      title ="Hello {/recipient/name}">
*HIGHLIGHT START*      <beginButton>
         <Button
            text="{i18n>dialogCloseButtonText}"
            press=".onCloseDialog"/>
      </beginButton>*HIGHLIGHT END*
   </Dialog>
</core:FragmentDefinition>
```

In the fragment definition, we add a button to the `beginButton` aggregation of the dialog. The press handler refers to an event handler called `.onCloseDialog`. By using the `loadFragment` function to create the fragment content, the method will be invoked there when the button is pressed. The dialog has an aggregation named `beginButton` as well as `endButton`. Placing buttons in both of these aggregations makes sure that the `beginButton` is placed before the `endButton` on the UI. What `before` means, however, depends on the text direction of the current language. We therefore use the terms `begin` and `end` as a synonym to “left” and “right". In languages with left-to-right direction, the `beginButton` will be rendered left, the `endButton` on the right side of the dialog footer; in right-to-left mode for specific languages the order is switched.

***

<a name="loio354f98ed2b514ba9960556333428d35e__section_d5m_ypr_r2b"/>

### webapp/i18n/i18n.properties

``` prefs
# App Descriptor
appTitle=Hello World
appDescription=A simple walkthrough app that explains the most important concepts of OpenUI5

# Hello Panel
showHelloButtonText=Say Hello
helloMsg=Hello {0}
homePageTitle=Walkthrough
helloPanelTitle=Hello World
openDialogButtonText=Say Hello With Dialog
*HIGHLIGHT START*dialogCloseButtonText=Ok*HIGHLIGHT END*
```

The text bundle is extended by the new text for the dialog’s close button.

**Parent topic:** [Walkthrough](Walkthrough_3da5f4b.md "In this tutorial we will introduce you to all major development paradigms of OpenUI5.")

**Next:** [Step 16: Dialogs and Fragments](Step_16_Dialogs_and_Fragments_4da7298.md "In this step, we will take a closer look at another element which can be used to assemble views: the fragment.")

**Previous:** [Step 18: Icons](Step_18_Icons_776f735.md "Our dialog is still pretty much empty. Since OpenUI5 is shipped with a large icon font that contains more than 500 icons, we will add an icon to greet our users when the dialog is opened.")

**Related Information**  


[Reusing UI Parts: Fragments](Reusing_UI_Parts_Fragments_36a5b13.md "Fragments are light-weight UI parts (UI sub-trees) which can be reused, defined similar to views, but do not have any controller or other behavior code involved.")

[Instantiation of Fragments](Instantiation_of_Fragments_04129b2.md "OpenUI5 provides two options to instantiate a fragment: If it is instantiated inside a controller extending sap.ui.core.mvc.Controller, the loadFragment() function is the way to go. However, if it is instantiated in a non-controller artefact, the generic function sap.ui.core.Fragment.load() can be used.")

