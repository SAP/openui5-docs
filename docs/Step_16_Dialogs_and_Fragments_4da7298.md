<!-- loio4da72985139b4b83b5f1c1e0c0d2ed5a -->

| loio |
| -----|
| 4da72985139b4b83b5f1c1e0c0d2ed5a |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/4da72985139b4b83b5f1c1e0c0d2ed5a) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/4da72985139b4b83b5f1c1e0c0d2ed5a)</div>

## Step 16: Dialogs and Fragments

In this step, we will take a closer look at another element which can be used to assemble views: the fragment.

Fragments are light-weight UI parts \(UI subtrees\) which can be reused but do not have any controller. This means, whenever you want to define a certain part of your UI to be reusable across multiple views, or when you want to exchange some parts of a view against one another under certain circumstances \(different user roles, edit mode vs read-only mode\), a fragment is a good candidate, especially where no additional controller logic is required.

A fragment can consist of 1 to n controls. At runtime, fragments placed in a view behave similar to "normal" view content, which means controls inside the fragment will just be included into the view’s DOM when rendered. There are of course controls that are not designed to become part of a view, for example, dialogs.

But even for these controls, fragments can be particularly useful, as you will see in a minute.

We will now add a dialog to our app. Dialogs are special, because they open on top of the regular app content and thus do not belong to a specific view. That means the dialog must be instantiated somewhere in the controller code, but since we want to stick with the declarative approach and create reusable artifacts to be as flexible as possible, and because dialogs cannot be specified as views, we will create an XML fragment containing the dialog. A dialog, after all, can be used in more than only one view of your app.

***

### Preview

   
  
A dialog opens when the new “Say Hello With Dialog” button is clicked<a name="loio4da72985139b4b83b5f1c1e0c0d2ed5a__fig_dzj_yzv_sr"/>

 ![](loiof22d75236864472193c3be229053b0f0_HiRes.png "A dialog opens when the new “Say Hello With Dialog” button is clicked") 

***

### Coding

You can view and download all files at [Walkthrough - Step 16](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.16/preview).

``` xml
<mvc:View
   controllerName="sap.ui.demo.walkthrough.controller.HelloPanel"
   xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc">
   <Panel
      headerText="{i18n>helloPanelTitle}"
      class="sapUiResponsiveMargin"
      width="auto" >
      <content>
    *HIGHLIGHT START*  <Button
         id="helloDialogButton"
         text="{i18n>openDialogButtonText}"
         press=".onOpenDialog"
         class="sapUiSmallMarginEnd"/>
*HIGHLIGHT END*
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
</mvc:View>
```

We add a new button to the view to open the dialog. It simply calls an event handler function in the controller of the panel’s content view. We will need the new `id="helloDialogButton"` in [Step 29: Integration Test with OPA](Step_29_Integration_Test_with_OPA_9bf4dce.md).

It is a good practice to set a unique ID like `helloWorldButton` to key controls of your app so that can be identified easily. If the attribute \`id\` is not specified, the OpenUI5 runtime generates unique but changing ID like \`\_\_button23\` for the control. Inspect the DOM elements of your app in the browser to see the difference.

***

### webapp/view/HelloDialog.fragment.xml \(New\)

``` xml
*HIGHLIGHT START*<core:FragmentDefinition
   xmlns="sap.m"
   xmlns:core="sap.ui.core" >
   <Dialog
      id="helloDialog"
      title="Hello {/recipient/name}">
   </Dialog>
</core:FragmentDefinition>*HIGHLIGHT END*
```

We add a new XML file to declaratively define our dialog in a fragment. The fragment assets are located in the `core` namespace, so we add an `xml` namespace for it inside the `FragmentDefinition` tag.

The syntax is similar to a view, but since fragments do not have a controller this attribute is missing. Also, the fragment does not have any footprint in the DOM tree of the app, and there is no control instance of the fragment itself \(only the contained controls\). It is simply a container for a set of reuse controls.

We also add an `id` for our `Dialog` to be able to access the dialog from our `HelloPanel` controller.

***

### webapp/controller/HelloPanel.controller.js

``` js
sap.ui.define([
	"sap/ui/core/mvc/Controller",
	"sap/m/MessageToast",
*HIGHLIGHT START*	"sap/ui/core/Fragment"*HIGHLIGHT END*
], function (Controller, MessageToast*HIGHLIGHT START*, Fragment*HIGHLIGHT END*) {
	"use strict";

	return Controller.extend("sap.ui.demo.walkthrough.controller.HelloPanel", {

		onShowHello : function () {
			…
		}*HIGHLIGHT START*,
		onOpenDialog : function () {
			var oView = this.getView();

			// create dialog lazily
			if (!this.byId("helloDialog")) {
				// load asynchronous XML fragment
				Fragment.load({
					id: oView.getId(),
					name: "sap.ui.demo.walkthrough.view.HelloDialog"
				}).then(function (oDialog) {
					// connect dialog to the root view of this component (models, lifecycle)
					oView.addDependent(oDialog);
					oDialog.open();
				});
			} else {
				this.byId("helloDialog").open();
			}
		}
*HIGHLIGHT END*
	});
});
```

If the dialog in the fragment does not exist yet, the fragment is instantiated by calling the `sap.ui.xmlfragment` method with the following arguments:

-   The ID of the `HelloPanel` view

    This parameter is used to prefix the IDs inside our fragment. There, we have defined the ID `helloDialog` for the `Dialog` control, and we can access the dialog via the view by calling `oView.byId("helloDialog")`. This makes sure that even if you instantiate the same fragment in other views in the same way, each dialog will have its unique ID that is concatenated from the view ID and the dialog ID.

    Using unique IDs is important, because duplicate IDs lead to errors in the framework.

-   The path of the fragment definition


We add the dialog as "dependent" on the view to be connected to the lifecycle of the view’s model. A convenient side-effect is that the dialog will automatically be destroyed when the view is destroyed. Otherwise, we would have to destroy the dialog manually to free its resources.

***

### Conventions

-   Always use the `addDependent` method to connect the dialog to the lifecycle management and data binding of the view, even though it is not added to its UI tree.

-   Private functions and variables should always start with an underscore.


**Related information**  


[Reusing UI Parts: Fragments](Reusing_UI_Parts_Fragments_36a5b13.md)

[Dialogs and other Popups as Fragments](Dialogs_and_other_Popups_as_Fragments_448c641.md)

[Stable IDs: All You Need to Know](Stable_IDs_All_You_Need_to_Know_f51dbb7.md)

[API Reference: `sap.ui.core.Fragment`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.Fragment.html)

