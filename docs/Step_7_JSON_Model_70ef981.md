<!-- loio70ef981d350a495b940640801701c409 -->

| loio |
| -----|
| 70ef981d350a495b940640801701c409 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/70ef981d350a495b940640801701c409) | [demo kit latest release](https://sdk.openui5.org/topic/70ef981d350a495b940640801701c409)</div>

## Step 7: JSON Model

Now that we have set up the view and controller, it’s about time to think about the M in MVC.

We will add an input field to our app, bind its value to the model, and bind the same value to the description of the input field. The description will be directly updated as the user types.

***

### Preview

  
  
**An input field and a description displaying the value of the input field**

![The graphic has an explanatory text](images/loioafc105517a644407bd90662e3d94ea01_LowRes.png "An input field and a description displaying the value of the input
					field")

***

<a name="loio70ef981d350a495b940640801701c409__section_e2g_rvc_syb"/>

### Coding

You can view and download all files at [Walkthrough - Step 7](https://sdk.openui5.org/entity/sap.m.tutorial.walkthrough/sample/sap.m.tutorial.walkthrough.07).

***

<a name="loio70ef981d350a495b940640801701c409__section_f2g_rvc_syb"/>

### webapp/controller/App.controller.js

```js
sap.ui.define([
   "sap/ui/core/mvc/Controller",
   "sap/m/MessageToast",
   "sap/ui/model/json/JSONModel"
], (Controller, MessageToast, JSONModel) => {
   "use strict";

   return Controller.extend("ui5.walkthrough.controller.App", {
      onInit() {
         // set data model on view
         const oData = {
            recipient : {
               name : "World"
            }
         };
         const oModel = new JSONModel(oData);
         this.getView().setModel(oModel);
      },

      onShowHello() {
         MessageToast.show("Hello World");
      }
   });
});
```

We add an `onInit` function to the controller. This is one of OpenUI5’s lifecycle methods that is invoked by the framework when the controller is created, similar to the constructor of a control.

Inside the function we instantiate a JSON model. The data for the model only contains a single property for the "recipient”, and inside this it also contains one additional property for the name.

To be able to use this model from within the XML view, we call the `setModel` function on the view and pass on our newly created model. The model is now set on the view.

The message toast is just showing the static "Hello World" message. We will show how to load a translated text here in the next step.

***

### webapp/view/App.view.xml

```xml
<mvc:View
   controllerName="ui5.walkthrough.controller.App"
   xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc">
   <Button
      text="Say Hello"
      press=".onShowHello"/>
   <Input
      value="{/recipient/name}"
      description="Hello {/recipient/name}"
      valueLiveUpdate="true"
      width="60%"/>
</mvc:View>
```

We add an `sap/m/Input` control to the view. With this, the user can enter a recipient for the greetings. We bind its value to a OpenUI5 model by using the declarative binding syntax for XML views:

-   The curly brackets `{…}` indicate that data is taken from the value of the `recipient`'s object name property. This is called "data binding".

-   `/recipient/name` declares the path in the model.


**Parent topic:**[Walkthrough Tutorial \(JavaScript\)](Walkthrough_Tutorial_JavaScript_3da5f4b.md "In this tutorial we will introduce you to all major development paradigms of OpenUI5.")

**Next:**[Step 6: Modules](Step_6_Modules_f665d0d.md "In OpenUI5, resources are often referred to as modules. In this step, we replace the alert from the last exercise with a proper Message Toast from the sap.m library.")

**Previous:**[Step 8: Translatable Texts](Step_8_Translatable_Texts_df86bfb.md "In this step we move the texts of our UI to a separate resource file.")

**Related Information**  


[Model View Controller \(MVC\)](Model_View_Controller_MVC_91f2334.md "The Model View Controller (MVC) concept is used in OpenUI5 to separate the representation of information from the user interaction. This separation facilitates development and the changing of parts independently.")

[Data Binding](Data_Binding_68b9644.md "You use data binding to bind UI elements to data sources to keep the data in sync and allow data editing on the UI.")

[JSON Model](JSON_Model_96804e3.md#loio96804e3315ff440aa0a50fd290805116 "The JSON model can be used to bind controls to JavaScript object data, which is usually serialized in the JSON format.")

[API Reference: `sap.ui.define`](https://sdk.openui5.org/api/sap.ui/methods/sap.ui.define)

