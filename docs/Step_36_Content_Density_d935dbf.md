<!-- loiod935dbf196d34997bf1ac42ac3e81579 -->

| loio |
| -----|
| d935dbf196d34997bf1ac42ac3e81579 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/d935dbf196d34997bf1ac42ac3e81579) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/d935dbf196d34997bf1ac42ac3e81579)</div>

## Step 36: Content Density

In this step of our Walkthrough tutorial, we adjust the content density based on the user’s device. OpenUI5 contains different content densities allowing you to display larger controls for touch-enabled devices and a smaller, more compact design for devices that are operated by mouse. In our app, we will detect the device and adjust the density accordingly.

***

### Preview

   
  
<a name="loiod935dbf196d34997bf1ac42ac3e81579__fig_r1j_pst_mr"/>The content density is compact on desktop devices and cozy on touch-enabled devices

 ![](loio04b6669bbc8a4524be5a998ad78544ac_HiRes.png "The content density is compact on desktop devices and cozy on touch-enabled
					devices") 

***

### Coding

You can view and download all files at [Walkthrough - Step 36](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.36/preview).

***

### webapp/Component.js

``` js
...
		init: function () {
...		}*HIGHLIGHT START*,*HIGHLIGHT END*
...
*HIGHLIGHT START*		getContentDensityClass : function () {
			if (!this._sContentDensityClass) {
				if (!Device.support.touch) {
					this._sContentDensityClass = "sapUiSizeCompact";
				} else {
					this._sContentDensityClass = "sapUiSizeCozy";
				}
			}
			return this._sContentDensityClass;
		}
*HIGHLIGHT END*
	});
});
```

To prepare the content density feature we will also add a helper method `getContentDensityClass`. OpenUI5 controls can be displayed in multiple sizes, for example in a `compact` size that is optimized for desktop and non-touch devices, and in a `cozy` mode that is optimized for touch interaction. The controls look for a specific CSS class in the HTML structure of the application to adjust their size.

This helper method queries the `Device` API directly for touch support of the client and returns the CSS class `sapUiSizeCompact` if touch interaction is not supported and `sapUiSizeCozy` for all other cases. We will use it throughout the application coding to set the proper content density CSS class.

***

### webapp/controller/App.controller.js

``` js
sap.ui.define([
	"sap/ui/core/mvc/Controller"
], function (Controller) {
	"use strict";

	return Controller.extend("sap.ui.demo.walkthrough.controller.App", {

*HIGHLIGHT START*		onInit: function () {
			this.getView().addStyleClass(this.getOwnerComponent().getContentDensityClass());
		}*HIGHLIGHT END*
	});
});
```

We add a method `onInit` on the app controller that is called when the app view is instantiated. There we query the helper function that we defined on the app component to set the corresponding style class on the app view, All controls inside the app view will now automatically adjust either to the compact or cozy size as defined by the style.

***

### webapp/controller/HelloDialog.controller.js

``` js
sap.ui.define([
	"sap/ui/core/mvc/Controller",
	"sap/m/MessageToast",
"sap/ui/core/syncStyleClass"
], function (Controller, MessageToast, syncStyleClass) {
	"use strict";

	return Controller.extend("sap.ui.demo.walkthrough.controller.HelloPanel", {

		onShowHello : function () {
			// read msg from i18n model
			var oBundle = this.getView().getModel("i18n").getResourceBundle();
			var sRecipient = this.getView().getModel().getProperty("/recipient/name");
			var sMsg = oBundle.getText("helloMsg", [sRecipient]);
		},

			// show message
			MessageToast.show(sMsg);
		},

		onOpenDialog : function () {
			var oView = this.getView();

			if (!this.pDialog) {
				this.pDialog = this.loadFragment({
					name: "sap.ui.demo.walkthrough.view.HelloDialog"
				*HIGHLIGHT START*}).then(function (oDialog){
					// forward compact/cozy style into dialog
					syncStyleClass(this.getOwnerComponent().getContentDensityClass(), this.getView(), oDialog);
					return oDialog;
				}.bind(this));*HIGHLIGHT END*
			} 
			this.pDialog.then(function(oDialog) {
				oDialog.open();
			});
		},

		onCloseDialog : function () {
			// note: We don't need to chain to the pDialog promise, since this event-handler
			// is only called from within the loaded dialog itself.
			this.byId("helloDialog").close();
		}

	});

});

```

The "Hello World" dialog is not part of the `HelloPanel` view but opened in a special part of the DOM called "static area". The content density class defined on the `app` view is not known to the dialog so we sync the style class of the app with the dialog manually.

***

### webapp/manifest.json

``` json
...
  "sap.ui5": {
    ...     
    "dependencies": {
      ...
    }*HIGHLIGHT START*,
    "contentDensities": {
      "compact": true,
      "cozy": true
    }
*HIGHLIGHT END*
  }
```

In the `contentDensities` section of the `sap.ui5` namespace, we specify the modes that the application supports. Containers like the SAP Fiori launchpad allow switching the content density based on these settings.

As we have just enabled the app to run in both modes depending on the devices capabilities, we can set both to `true` in the application descriptor.

***

<a name="loiod935dbf196d34997bf1ac42ac3e81579__section_kpq_zct_qbb"/>

### Summary

You should now be familiar with the major development paradigms and concepts of OpenUI5 and have created a very simple first app. You are now ready to build a proper app based on what you've learned.

If you want to dive deeper into specific topics, you can use the other tutorials that show some of the aspects of this Walkthrough and advanced topics in more detail.

**Parent topic:** [Walkthrough](Walkthrough_3da5f4b.md "In this tutorial we will introduce you to all major development paradigms of OpenUI5.")

**Next:** [Step 35: Device Adaptation](Step_35_Device_Adaptation_d63a15e.md "We now configure the visibility and properties of controls based on the device that we run the application on. By making use of the sap.ui.Device API and defining a device model we will make the app look great on many devices.")

**Previous:** [Step 37: Accessibility](Step_37_Accessibility_ff7cab1.md "As the last step in this tutorial, we are going to improve the accessibility of our app.")

**Related Information**  


[Content Densities](Content_Densities_e54f729.md "The devices used to run apps that are developed with OpenUI5 run on various different operating systems and have very different screen sizes. OpenUI5 contains different content densities for certain controls that allow your app to adapt to the device in question, allowing you to display larger controls for touch-enabled devices and a smaller, more compact design for devices that are operated by mouse.")

[API Reference: `sap.ui.Device.media.RANGESETS`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.Device.media.RANGESETS.html)

[API Reference: `sap.ui.Device`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.Device.html)

[API Reference: `sap.ui.core.syncStyleClass`](https://openui5.hana.ondemand.com/#/api/module:sap/ui/core/syncStyleClass)

