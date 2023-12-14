<!-- loio3510034eb6274fd8a8fb7d65c2f1aa46 -->

| loio |
| -----|
| 3510034eb6274fd8a8fb7d65c2f1aa46 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/3510034eb6274fd8a8fb7d65c2f1aa46) | [demo kit latest release](https://sdk.openui5.org/topic/3510034eb6274fd8a8fb7d65c2f1aa46)</div>

## Step 6: Modules \(TypeScript\)

In OpenUI5, resources are often referred to as modules. In this step, we replace the alert from the last exercise with a proper Message Toast from the `sap.m` library.

***

### Preview

  
  
**A message toast displays the "Hello World" message**

![A message toast displays the Hello World message](images/loio2f629a95211f49afa367b60d233fb390_LowRes.png "A message toast displays the "Hello World" message")

***

<a name="loio3510034eb6274fd8a8fb7d65c2f1aa46__section_nlr_cvc_syb"/>

### Coding

You can view all files at [OpenUI5 TypeScript Walkthrough - Step 6: Modules](https://github.com/sap-samples/ui5-typescript-walkthrough/steps/06/README.md).

***

<a name="loio3510034eb6274fd8a8fb7d65c2f1aa46__section_olr_cvc_syb"/>

### webapp/controller/App.controller.ts

We now replace the native `alert` function with the `show` method of the `sap/m/MessageToast` control of OpenUI5. For this, we extend the imports with the `sap/m/MessageToast` module.

```js
import MessageToast from "sap/m/MessageToast";
import Controller from "sap/ui/core/mvc/Controller";

/**
 * @name ui5.walkthrough.controller.App
 */
export default class AppController extends Controller {
    onShowHello(): void {
        MessageToast.show("Hello World");
     }
};
```

For now, the message toast just displays a static "Hello World" message. We'll show how to load a translated text here in [Step 8: Translatable Texts \(TypeScript\)](Step_8_Translatable_Texts_TypeScript_4dcf52e.md).

**Parent topic:**[Walkthrough Tutorial \(TypeScript\)](Walkthrough_Tutorial_TypeScript_dad1905.md "In this tutorial we'll introduce you to all major development paradigms of OpenUI5. We'll demonstrate the use of TypeScript with OpenUI5 and highlight the specific characteristics of this approach.")

**Next:**[Step 5: Controllers \(TypeScript\)](Step_5_Controllers_TypeScript_e5c58fe.md "In this step, we replace the text with a button and show the “Hello World” message when the button is pressed. The handling of the button's press event is implemented in the controller of the view.")

**Previous:**[Step 7: JSON Model \(TypeScript\)](Step_7_JSON_Model_TypeScript_cfbbeab.md "Now that we have set up the view and controller, it’s about time to think about the M in MVC.")

**Related Information**  


[API Reference: `sap.m.MessageToast`](https://sdk.openui5.org/api/sap.m.MessageToast)

