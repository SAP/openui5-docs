<!-- loio667aa4a5d4914dbf82f843b8954244c2 -->

| loio |
| -----|
| 667aa4a5d4914dbf82f843b8954244c2 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/667aa4a5d4914dbf82f843b8954244c2) | [demo kit latest release](https://sdk.openui5.org/topic/667aa4a5d4914dbf82f843b8954244c2)</div>

## Step 36: Content Density

In this step of our Walkthrough tutorial, we adjust the content density based on the user’s device. OpenUI5 contains different content densities allowing you to display larger controls for touch-enabled devices and a smaller, more compact design for devices that are operated by mouse. In our app, we will detect the device and adjust the density accordingly.

***

### Preview

  
  
**The content density is compact on desktop devices and cozy on touch-enabled devices**

![](images/loiof216b131c492448d8a1df25db2b9a26d_LowRes.png "The content density is compact on desktop devices and cozy on touch-enabled
					devices")

***

### Coding

You can view and download all files at [Walkthrough - Step 36](https://sdk.openui5.org/entity/sap.m.tutorial.walkthrough/sample/sap.m.tutorial.walkthrough.36).

***

### webapp/Component.js

```js
...

		getContentDensityClass() {
			return Device.support.touch ? "sapUiSizeCozy" : "sapUiSizeCompact";
		}
	});
});
```

To prepare the content density feature we will also add a helper method `getContentDensityClass`. OpenUI5 controls can be displayed in multiple sizes, for example in a `compact` size that is optimized for desktop and non-touch devices, and in a `cozy` mode that is optimized for touch interaction. The controls look for a specific CSS class in the HTML structure of the application to adjust their size.

This helper method queries the `Device` API directly for touch support of the client and returns the CSS class `sapUiSizeCompact` if touch interaction is not supported and `sapUiSizeCozy` for all other cases. We will use it throughout the application coding to set the proper content density CSS class.

***

### webapp/controller/App.controller.js

```js
sap.ui.define([
	"sap/ui/core/mvc/Controller"
], (Controller) => {
	"use strict";

	return Controller.extend("ui5.walkthrough.controller.App", {

		onInit() {
			this.getView().addStyleClass(this.getOwnerComponent().getContentDensityClass());
		}
	});
});
```

We add an `onInit` method to the app controller that is called when the app view is instantiated. There, we query the helper function that we defined on the app component in order to set the corresponding style class on the app view. All controls inside the app view will now automatically adjust to either the compact or the cozy size, as defined by the style.

***

### webapp/manifest.json

```json
...
  "sap.ui5": {
    ...  
    },
    "contentDensities": {
      "compact": true,
      "cozy": true
    }
    ...
  }
```

In the `contentDensities` section of the `sap.ui5` namespace, we have to specify the modes that the application supports. Containers like the SAP Fiori launchpad allow switching the content density based on these settings.

As we have just enabled the app to run in both modes depending on the devices capabilities, we can set both to `true` in the application descriptor.

**Related Information**  


[Content Densities](Content_Densities_e54f729.md "The devices used to run apps that are developed with OpenUI5 run on various different operating systems and have very different screen sizes. OpenUI5 contains different content densities for certain controls that allow your app to adapt to the device in question, allowing you to display larger controls for touch-enabled devices and a smaller, more compact design for devices that are operated by mouse.")

[API Reference: `sap.ui.Device`](https://sdk.openui5.org/api/sap.ui.Device)

