<!-- loiof030afccc30f461c9660724561cb7264 -->

| loio |
| -----|
| f030afccc30f461c9660724561cb7264 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/f030afccc30f461c9660724561cb7264) | [demo kit latest release](https://sdk.openui5.org/topic/f030afccc30f461c9660724561cb7264)</div>

## Step 17: Fragment Callbacks \(TypeScript\)

Now that we have integrated the dialog, it's time to add some user interaction. The user will definitely want to close the dialog again at some point, so we add a button to close the dialog and assign an event handler.

***

### Preview

  
  
**The dialog now has an "OK" button**

![The graphic has an explanatory text.](images/loioc351bbd078824c43bf1758b0c3679cbd_LowRes.png "The dialog now has an "OK" button")

***

<a name="loiof030afccc30f461c9660724561cb7264__section_mt1_5fk_syb"/>

### Coding

You can view all files at [OpenUI5 TypeScript Walkthrough - Step 17: Fragment Callbacks](https://github.com/sap-samples/ui5-typescript-walkthrough/tree/main/steps/17) and [download the solution as a zip file](https://sap-samples.github.io/ui5-typescript-walkthrough/ui5-typescript-walkthrough-step-17.zip).

***

<a name="loiof030afccc30f461c9660724561cb7264__section_nt1_5fk_syb"/>

### webapp/controller/HelloPanel.controller.ts

We add an event handler function into the `HelloPanel` controller file that closes the dialog when triggered. To get the dialog instance, we use the `byId` function and then call the `close` function of the dialog.

```js
import Controller from "sap/ui/core/mvc/Controller";
import MessageToast from "sap/m/MessageToast";
import JSONModel from "sap/ui/model/json/JSONModel";
import ResourceModel from "sap/ui/model/resource/ResourceModel";
import ResourceBundle from "sap/base/i18n/ResourceBundle";
import Dialog from "sap/m/Dialog";

/**
 * @namespace ui5.walkthrough.controller
 */
export default class HelloPanel extends Controller {
    private dialog: Dialog;

    onShowHello(): void {
        ...
    }
   async onOpenDialog(): Promise<void> {
        ...
    }
    onCloseDialog(): void {
        // note: We don't need to chain to the pDialog promise, since this event-handler
        // is only called from within the loaded dialog itself.
        (this.byId("helloDialog") as Dialog)?.close();
    }        
};
```

***

<a name="loiof030afccc30f461c9660724561cb7264__section_d5m_ypr_r2b"/>

### webapp/i18n/i18n.properties

We extend the text bundle by the new text for the dialog's `Close` button.

```ini
# App Descriptor
appTitle=Hello World
appDescription=A simple walkthrough app that explains the most important concepts of OpenUI5

# Hello Panel
showHelloButtonText=Say Hello
helloMsg=Hello {0}
homePageTitle=UI5 TypeScript Walkthrough
helloPanelTitle=Hello World
openDialogButtonText=Say Hello With Dialog
dialogCloseButtonText=Ok
```

***

### webapp/view/HelloDialog.fragment.xml

In the fragment definition, we add a button to the `beginButton` aggregation of the dialog and refer the press handler to the event handler we just defined in the controller of the panel's content view.

```xml
<core:FragmentDefinition
   xmlns="sap.m"
   xmlns:core="sap.ui.core">
   <Dialog
      id="helloDialog"
      title ="Hello {/recipient/name}">
      <beginButton>
         <Button
            text="{i18n>dialogCloseButtonText}"
            press=".onCloseDialog"/>
      </beginButton>
   </Dialog>
</core:FragmentDefinition>
```

By using the `loadFragment` function to create the fragment content in the controller of the panel's content view, the method will be invoked there when the button is pressed. The dialog has an aggregation named `beginButton` as well as `endButton`. Placing buttons in both of these aggregations makes sure that the `beginButton` is placed before the `endButton` on the UI. What `before` means, however, depends on the text direction of the current language. We therefore use the terms `begin` and `end` as a synonym to "left" and "right". In languages with left-to-right direction, the `beginButton` will be rendered left, the `endButton` on the right side of the dialog footer; in right-to-left mode for specific languages the order is switched.

**Parent topic:**[Walkthrough Tutorial \(TypeScript\)](Walkthrough_Tutorial_TypeScript_dad1905.md "In this tutorial we'll introduce you to all major development paradigms of OpenUI5. We'll demonstrate the use of TypeScript with OpenUI5 and highlight the specific characteristics of this approach.")

**Next:**[Step 16: Dialogs and Fragments \(TypeScript\)](Step_16_Dialogs_and_Fragments_TypeScript_4b2e306.md "In this step, we will take a closer look at another element which can be used to assemble views: the fragment.")

**Previous:**[Step 18: Icons \(TypeScript\)](Step_18_Icons_TypeScript_49b1ac6.md "Our dialog is still pretty much empty. Since OpenUI5 is shipped with a large icon font that contains more than 500 icons, we will add an icon to greet our users when the dialog is opened.")

**Related Information**  


[Reusing UI Parts: Fragments](Reusing_UI_Parts_Fragments_36a5b13.md "Fragments are light-weight UI parts (UI sub-trees) which can be reused, defined similar to views, but do not have any controller or other behavior code involved.")

[Instantiation of Fragments](Instantiation_of_Fragments_04129b2.md "OpenUI5 provides two options to instantiate a fragment: If it is instantiated inside a controller extending sap.ui.core.mvc.Controller, the loadFragment() function is the way to go. However, if it is instantiated in a non-controller artefact, the generic function sap.ui.core.Fragment.load() can be used.")

[API Reference: `sap.m.Dialog`](https://sdk.openui5.org/api/sap.m.Dialog)

[Samples: `sap.m.Dialog`](https://sdk.openui5.org/entity/sap.m.Dialog)

