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

![](images/loio2f629a95211f49afa367b60d233fb390_LowRes.png "A message toast displays the "Hello World" message")

***

<a name="loio3510034eb6274fd8a8fb7d65c2f1aa46__section_nlr_cvc_syb"/>

### Coding

You can view and download all files at [Walkthrough - Step 6](https://github.com/sap-samples/).

***

<a name="loio3510034eb6274fd8a8fb7d65c2f1aa46__section_olr_cvc_syb"/>

### webapp/controller/App.controller.ts

We now replace the native `alert` function with the `show` method of the `sap/m/MessageToast` library of OpenUI5. For this, we extend the imports with the `sap/m/MessageToast` module.

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

***

### Conventions

Use the name of the artifact to load for naming the module \(without namespace\).

**Related Information**  


[API Reference: `sap.m.MessageToast`](https://sdk.openui5.org/api/sap.m.MessageToast)

