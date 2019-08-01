<!-- loio19453962b8074b7399372c65cbe05370 -->

| loio |
| -----|
| 19453962b8074b7399372c65cbe05370 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/19453962b8074b7399372c65cbe05370) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/19453962b8074b7399372c65cbe05370)</div>

## Step 19: Reuse Dialogs

In this step, we expand our reuse concept and invoke the dialog at component level.

In step 16, we created a dialog as fragment, to make it reusable across views or across our whole app. But we placed the logic for retrieving the dialog instance and for opening and closing it respectively in the controller of the `HelloPanel` view. Sticking to this approach would require copying and pasting the code to the controller of each view that needs our dialog. This would cause an undesired code redundancy which we want to avoid.

In this step, we implement the solution to this problem: We expand our reuse concept and invoke the dialog at component level.

***

### Preview

   
  
The dialog is now opened by the component \(no visual changes to last step\)<a name="loio19453962b8074b7399372c65cbe05370__fig_r1j_pst_mr"/>

 ![](loio6fbc14686a044570be0b7654e683cd56_HiRes.png "The dialog is now opened by the component (no visual changes to last
					step)") 

***

### Coding

You can view and download all files at [Walkthrough - Step 19](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.19/preview).

***

### webapp/Component.js

``` js
sap.ui.define([
	"sap/ui/core/UIComponent",
	"sap/ui/model/json/JSONModel"*HIGHLIGHT START*,
	"./controller/HelloDialog"
*HIGHLIGHT END*
], function (UIComponent, JSONModel*HIGHLIGHT START*, HelloDialog*HIGHLIGHT END*) {
	"use strict";
	return UIComponent.extend("sap.ui.demo.walkthrough.Component", {
		metadata : {
			manifest : "json"
		},
		init : function () {
			// call the init function of the parent
			UIComponent.prototype.init.apply(this, arguments);
			// set data model
			var oData = {
				recipient : {
					name : "World"
				}
			};
			var oModel = new JSONModel(oData);
			this.setModel(oModel);

			*HIGHLIGHT START*// set dialog
			this._helloDialog = new HelloDialog(this.getRootControl());
		},


		exit : function() {
			this._helloDialog.destroy();
			delete this._helloDialog;
		},

		openHelloDialog : function () {
			this._helloDialog.open();*HIGHLIGHT END*
		}
	});
});
```

The dialog instantiation is refactored to a new helper object which is stored in a private property of the component. For instantiation of the helper object, we have to pass the view instance to which the dialog is added \(see method call `addDependent` in the implementation of the helper object `HelloDialog.js` below\).

We want to connect the reuse dialog to the lifecycle of the root view of the app, so we pass an instance of the root view on to the constructor. It can be retrieved by calling the `getRootControl` method of the component.

> Note:
> As defined in parameter `rootView` in the `manifest.json` file, our root view is `sap.ui.demo.walkthrough.view.App`. From the component, the root view can be retrieved at runtime by accessing the `rootControl` aggregation.
> 
> 

To be able to open the dialog from other controllers as well, we implement a reuse function `openHelloDialog` which calls the `open` method of our helper object. By doing so, we also decouple the implementation details of the reuse dialog from the application coding.

Up to this point we added the new property `_helloDialog` to the component and assigned an instance of the `HelloDialog` object to it. We want to make sure that the memory allocated for this helper object is freed up when the component is destroyed. Otherwise our application may cause memory leaks.

To do so, we use the `exit` hook. The OpenUI5 framework calls the function assigned to `exit` when destroying the component. We call the destroy function of `HelloDialog` to clean up the helper class and end its lifecycle. Nevertheless, the instance itself would still exist in the browser memory. Therefore we delete our reference to the `HelloDialog` instance by calling `delete this._helloDialog` and the garbage collection of the browser can clean up its memory.

> Note:
> We don't have to destroy the instance of `JSONModel` that we created, because we assigned it to the component with the `setModel` function. The OpenUI5 framework will destroy it together with the component.
> 
> 

***

### webapp/controller/HelloDialog.js \(New\)

``` js
*HIGHLIGHT START*sap.ui.define([
	"sap/ui/base/ManagedObject",
	"sap/ui/core/Fragment"
], function (ManagedObject, Fragment) {
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
				}).then(function (oDialog) {
					// connect dialog to the root view of this component (models, lifecycle)
					oView.addDependent(oDialog);
					oDialog.open();
				});
			} else {
				oView.byId("helloDialog").open();
			}
		}

	});

});
*HIGHLIGHT END*
```

The implementation of the `HelloDialog` reuse object extends an `sap.ui.base.ManagedObject` object to inherit some of the core functionality of OpenUI5.

Our `open` method is refactored from the `HelloPanel` controller and instantiates our dialog fragment as in the previous steps.

> Note:
> We do not pass a controller as third parameter to function `sap.ui.xmlfragment` but a local helper object `oFragmentContoller` which included the needed event handler function `onCloseDialog` for the fragment.
> 
> 

The `open` method now contains our dialog instantiation. The first time the `open` method is called, the dialog is instantiated. The `oView` argument of this method is used to connect the current view to the dialog. We will call the `open` method of this object later in the controller.

The `onCloseDialog` event handler is simply moved from the `HelloPanel` controller to the reuse object.

We also add an `exit` function, just like we did in the component, that will be called automatically when the object is being destroyed. To free up all allocated memory in the helper object, we delete the property that holds the reference to the view. The view itself will be destroyed by the component, so we don't need to take care for that.

***

### webapp/controller/HelloPanel.controller.js

``` js
sap.ui.define([
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
		},
		*HIGHLIGHT START*onOpenDialog : function () {
			this.getOwnerComponent().openHelloDialog();
		}*HIGHLIGHT END*
	});
});
```

The `onOpenDialog` method now accesses its component by calling the helper method `getOwnerComponent`. When calling the open method of the reuse object we pass in the current view to connect it to the dialog.

***

### webapp/view/App.view.xml

``` js
<mvc:View
	controllerName="sap.ui.demo.walkthrough.controller.App"
	xmlns="sap.m"
	xmlns:mvc="sap.ui.core.mvc"
	displayBlock="true">
	<Shell>
		<App class="myAppDemoWT">
			<pages>
				<Page title="{i18n>homePageTitle}">
*HIGHLIGHT START*					<headerContent>
						<Button
							icon="sap-icon://hello-world"
							press=".onOpenDialog"/>
					</headerContent>
*HIGHLIGHT END*
					<content>
						<mvc:XMLView viewName="sap.ui.demo.walkthrough.view.HelloPanel"/>
					</content>
				</Page>
			</pages>
		</App>
	</Shell>
</mvc:View>

```

We add a button to the header area of the app view to show the reuse of the hello world dialog. When pressing the button the dialog will be opened as with the button that we previously created in the panel.

``` js
sap.ui.define([
	"sap/ui/core/mvc/Controller"
], function (Controller) {
	"use strict";

	return Controller.extend("sap.ui.demo.walkthrough.controller.App", {

*HIGHLIGHT START*		onOpenDialog : function () {
			this.getOwnerComponent().openHelloDialog();
		}*HIGHLIGHT END*
	});

});
```

We add the method `onOpenDialog` also to the app controller so that the dialog will open with a reference to the current view.

-   Put all assets that are used across multiple controllers in separate modules.


**Related information**  


[Memory Management on https://developer.mozilla.org](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Memory_Management)

[API Reference: `sap.ui.base.ManagedObject`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.base.ManagedObject.html)

