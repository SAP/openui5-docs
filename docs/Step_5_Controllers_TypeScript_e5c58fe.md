<!-- loioe5c58fe81fed4d31988be6899c1188e7 -->

| loio |
| -----|
| e5c58fe81fed4d31988be6899c1188e7 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/e5c58fe81fed4d31988be6899c1188e7) | [demo kit latest release](https://sdk.openui5.org/topic/e5c58fe81fed4d31988be6899c1188e7)</div>

## Step 5: Controllers \(TypeScript\)

In this step, we replace the text with a button and show the “Hello World” message when the button is pressed. The handling of the button's `press` event is implemented in the controller of the view.

***

### Preview

  
  
**A Say Hello button is added**

![A Say Hello button is added](images/loiocedfdf89b30643ddbfcab1fe50bfa892_LowRes.png "A Say Hello button is added")

***

<a name="loioe5c58fe81fed4d31988be6899c1188e7__section_yqd_crc_syb"/>

### Coding

You can view all files at [OpenUI5 TypeScript Walkthrough - Step 5: Controllers](https://github.com/sap-samples/ui5-typescript-walkthrough/steps/05/README.md).

***

<a name="loioe5c58fe81fed4d31988be6899c1188e7__section_cyr_snf_lzb"/>

### webapp/controller/App.controller.ts \(New\)

First of all, we need a controller for our app view that defines how the view should react to user inputs, such as a button press event.

We create the folder `webapp/controller` and a new file `App.controller.ts` inside. We define the app controller in its own file by extending the OpenUI5-provided `sap/ui/core/mvc/Controller`. In the beginning, it holds only a single function called `onShowHello` that shows an alert.

```js
import Controller from "sap/ui/core/mvc/Controller";

/**
 * @name ui5.walkthrough.controller.App
 */
export default class AppController extends Controller {
    onShowHello(): void {
        // show a native JavaScript alert
        alert("Hello World");
     }
};
```

***

<a name="loioe5c58fe81fed4d31988be6899c1188e7__section_zqd_crc_syb"/>

### webapp/view/App.view.xml

We add a reference to the controller by setting the `controllerName` attribute of the view. This way we get access to the event handlers and other functionalities defined in the controller.

We also replace the text control with a button with text “Say Hello” and assign a press event to it. When pressed, the button triggers the `onShowHello` event handler function we introduced in the controller of the view. To point out that the press event handler of the button is located in the controller of the view and not in the Global Namespace, we prefix the handler name with a "`.`" character.

```xml
<mvc:View
   controllerName="ui5.walkthrough.controller.App"
   xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc">
   <Button
      text="Say Hello"
      press=".onShowHello"/>
</mvc:View>
```

A view does not necessarily need an explicitly assigned controller. You do not have to create a controller if the view is just displaying information and no additional functionality is required. If a controller is specified, it is instantiated after the view is loaded.

***

### Conventions

-   Controller names are capitalized

-   All controllers are stored in the `controller` folder
-   Controllers carry the same name as the related view \(if there is a 1:1 relationship\)

-   Event handlers are prefixed with `on`

-   Controller names always end with `*.controller.js` \(in JavaScript\) or `*.controller.ts` \(in TypeScript\)


**Parent topic:**[Walkthrough Tutorial \(TypeScript\)](Walkthrough_Tutorial_TypeScript_dad1905.md "In this tutorial we'll introduce you to all major development paradigms of OpenUI5. We'll demonstrate the use of TypeScript with OpenUI5 and highlight the specific characteristics of this approach.")

**Next:**[Step 4: XML Views \(TypeScript\)](Step_4_XML_Views_TypeScript_6c66ed8.md "Putting all our UI into the index.ts file will very soon result in a messy setup, and there is quite a bit of work ahead of us. So let’s do a first modularization by putting the sap/m/Text control into a dedicated view.")

**Previous:**[Step 6: Modules \(TypeScript\)](Step_6_Modules_TypeScript_3510034.md "In OpenUI5, resources are often referred to as modules. In this step, we replace the alert from the last exercise with a proper Message Toast from the sap.m library.")

**Related Information**  


[Model View Controller \(MVC\)](Model_View_Controller_MVC_91f2334.md "The Model View Controller (MVC) concept is used in OpenUI5 to separate the representation of information from the user interaction. This separation facilitates development and the changing of parts independently.")

[Controller](Controller_121b8e6.md "A controller contains methods that define how models and views interact.")

[API Reference: `sap.ui.core.mvc.Controller`](https://sdk.openui5.org/api/sap.ui.core.mvc.Controller)

