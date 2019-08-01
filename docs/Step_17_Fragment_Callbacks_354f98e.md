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

   
  
The dialog now has an "OK" button<a name="loio354f98ed2b514ba9960556333428d35e__fig_r1j_pst_mr"/>

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
			var oView = this.getView();

			// create dialog lazily
			if (!this.byId("helloDialog")) {
				// load asynchronous XML fragment
				Fragment.load({
					id: oView.getId(),
					name: "sap.ui.demo.walkthrough.view.HelloDialog"*HIGHLIGHT START*,
					controller: this*HIGHLIGHT END*
				}).then(function (oDialog) {
					// connect dialog to the root view of this component (models, lifecycle)
					oView.addDependent(oDialog);
					oDialog.open();
				});
			} else {
				this.byId("helloDialog").open();
			}
		}*HIGHLIGHT START*,

		onCloseDialog : function () {
			this.byId("helloDialog").close();
		}*HIGHLIGHT END*
	});

});
```

As previously described, fragments are pure UI reuse artifacts and do not have a controller. The third parameter of the `sap.ui.xmlfragment` function is optional and allows passing in a reference to a \(controller\) object. For our dialog we reference the `HelloPanel` controller. However, the third parameter does not necessarily have to be a controller but can be any object. Just don't forget the `this` keyword.

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

In the fragment definition, we add a button to the `beginButton` aggregation of the dialog. The press handler is referring to an event handler called `.onCloseDialog`, and since we passed in the reference to the `HelloPanel` controller, the method will be invoked there when the button is pressed. The dialog has an aggregation named `beginButton` as well as `endButton`. Placing buttons in both of these aggregations makes sure that the `beginButton` is placed before the `endButton` on the UI. What `before` means, however, depends on the text direction of the current language. We therefore use the terms `begin` and `end` as a synonym to “left” and “right". In languages with left-to-right direction, the `beginButton` will be rendered left, the `endButton` on the right side of the dialog footer; in right-to-left mode for specific languages the order is switched.

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
*HIGHLIGHT START*openDialogButtonText=Say Hello With Dialog
dialogCloseButtonText=Ok*HIGHLIGHT END*
```

The text bundle is extended by two new texts for the open button and the dialog’s close button.

**Related information**  


[Reusing UI Parts: Fragments](Reusing_UI_Parts_Fragments_36a5b13.md)

[Instantiation of Fragments](Instantiation_of_Fragments_04129b2.md)

