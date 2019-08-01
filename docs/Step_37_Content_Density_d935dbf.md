<!-- loiod935dbf196d34997bf1ac42ac3e81579 -->

| loio |
| -----|
| d935dbf196d34997bf1ac42ac3e81579 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/d935dbf196d34997bf1ac42ac3e81579) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/d935dbf196d34997bf1ac42ac3e81579)</div>

## Step 37: Content Density

In this step of our Walkthrough tutorial, we adjust the content density based on the user’s device. OpenUI5 contains different content densities allowing you to display larger controls for touch-enabled devices and a smaller, more compact design for devices that are operated by mouse. In our app, we will detect the device and adjust the density accordingly.

***

### Preview

   
  
The content density is compact on desktop devices and cozy on touch-enabled devices<a name="loiod935dbf196d34997bf1ac42ac3e81579__fig_r1j_pst_mr"/>

 ![](loio04b6669bbc8a4524be5a998ad78544ac_HiRes.png "The content density is compact on desktop devices and cozy on touch-enabled
					devices") 

***

### Coding

You can view and download all files at [Walkthrough - Step 37](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.37/preview).

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

This helper method queries the **Device** API directly for touch support of the client and returns the CSS class `sapUiSizeCompact` if touch interaction is not supported and `sapUiSizeCozy` for all other cases. We will use it throughout the application coding to set the proper content density CSS class.

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
		}*HIGHLIGHT END*,
		onOpenDialog: function () {
			this.getOwnerComponent().openHelloDialog();
		}
	});
});
```

We add a method `onInit` on the app controller that is called when the app view is instantiated. There we query the helper function that we defined on the app component to set the corresponding style class on the app view, All controls inside the app view will now automatically adjust either to the compact or cozy size as defined by the style.

***

### webapp/controller/HelloDialog.js

``` js
sap.ui.define([
	"sap/ui/base/ManagedObject",
	"sap/ui/core/Fragment",
*HIGHLIGHT START*	"sap/ui/core/syncStyleClass"*HIGHLIGHT END*
], function (ManagedObject, Fragment*HIGHLIGHT START*, syncStyleClass*HIGHLIGHT END*) {
	"use strict";

	return ManagedObject.extend("sap.ui.demo.walkthrough.controller.HelloDialog", {

		constructor : function (oView) {
			this._oView = oView;
		},

		exit : function () {
			delete this._oView;
		},

		open : function () {
			var oView = this._oView;

			// create dialog lazily
			if (!oView.byId("helloDialog")) {
				var oFragmentController = {
					onCloseDialog : function () {
						oView.byId("helloDialog").close();
					}
				};
				// load asynchronous XML fragment
				Fragment.load({
					id: oView.getId(),
					name: "sap.ui.demo.walkthrough.view.HelloDialog",
					controller: oFragmentController
				}).then(function (oDialog){
					// connect dialog to the root view of this component (models, lifecycle)
					oView.addDependent(oDialog);
	*HIGHLIGHT START*				// forward compact/cozy style into dialog
					syncStyleClass(oView.getController().getOwnerComponent().getContentDensityClass(), oView, oDialog);*HIGHLIGHT END*
					oDialog.open();
				});
			} else {
				oView.byId("helloDialog").open();
			}
		}

	});

});

```

The "Hello World" dialog is not part of the `app` view but opened in a special part of the DOM called "static area". The content density class defined on the `app` view is not known to the dialog so we sync the style class of the app with the dialog manually.

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

**Related information**  


[Content Densities](Content_Densities_e54f729.md)

[API Reference: `sap.ui.Device.media.RANGESETS`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.Device.media.RANGESETS.html)

[API Reference: `sap.ui.Device`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.Device.html)

[API Reference: `jQuery.sap.syncStyleClass`](https://openui5.hana.ondemand.com/#/api/jQuery.sap/methods/jQuery.sap.syncStyleClass)

