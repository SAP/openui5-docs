<!-- loiodf86bfbeab0645e5b764ffa488ed57dc -->

| loio |
| -----|
| df86bfbeab0645e5b764ffa488ed57dc |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/df86bfbeab0645e5b764ffa488ed57dc) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/df86bfbeab0645e5b764ffa488ed57dc)</div>

## Step 8: Translatable Texts

In this step we move the texts of our UI to a separate resource file.

This way, they are all in a central place and can be easily translated into other languages. This process of internationalization – in short `i18n` – is achieved in OpenUI5 by using a special resource model and the standard data binding syntax, but without preceding `/`.

***

### Preview

   
  
An input field and a description displaying the value of the input field \(No visual changes to last step\)<a name="loiodf86bfbeab0645e5b764ffa488ed57dc__fig_r1j_pst_mr"/>

 ![](loioe5a9bb4cb06b4d9c8b37914bf5cd2d13_HiRes.png "An input field and a description displaying the value of the input field (No visual
					changes to last step)") 

***

### Coding

You can view and download all files at [Walkthrough - Step 8](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.08/preview).

``` prefs
*HIGHLIGHT START*showHelloButtonText=Say Hello
helloMsg=Hello {0}*HIGHLIGHT END*
```

We create the folder `webapp/i18n` and the file `i18n.properties` inside. The resolved bundle name is `sap.ui.demo.walkthrough.i18n`, as we will see later. The `properties` file for texts contains name-value pairs for each element. You can add any number of parameters to the texts by adding numbers in curly brackets to them. These numbers correspond to the sequence in which the parameters are accessed \(starting with 0\).

In this tutorial we will only have one properties file. However, in real-world projects, you would have a separate file for each supported language with a suffix for the locale, for example`i18n_de.properties` for German, `i18n_en.properties` for English, and so on. When a user runs the app, OpenUI5 will load the language file that fits best to the user's environment.

***

### controller/App.controller.js

``` js
sap.ui.define([
   "sap/ui/core/mvc/Controller",
   "sap/m/MessageToast",
   "sap/ui/model/json/JSONModel"*HIGHLIGHT START*,
   "sap/ui/model/resource/ResourceModel"*HIGHLIGHT END*
], function (Controller, MessageToast, JSONModel*HIGHLIGHT START*, ResourceModel*HIGHLIGHT END*) {
   "use strict";
   return Controller.extend("sap.ui.demo.walkthrough.controller.App", {
     onInit : function () {
         // set data model on view
         var oData = {
            recipient : {
               name : "World"
            }
         };
         var oModel = new JSONModel(oData);
         this.getView().setModel(oModel);
         *HIGHLIGHT START*// set i18n model on view
         var i18nModel = new ResourceModel({
            bundleName: "sap.ui.demo.walkthrough.i18n.i18n"
         });
         this.getView().setModel(i18nModel, "i18n");*HIGHLIGHT END*
      },
      onShowHello : function () {
       *HIGHLIGHT START*  // read msg from i18n model
         var oBundle = this.getView().getModel("i18n").getResourceBundle();
         var sRecipient = this.getView().getModel().getProperty("/recipient/name");
         var sMsg = oBundle.getText("helloMsg", [sRecipient]);
         // show message
         MessageToast.show(sMsg);*HIGHLIGHT END*
      }
   });
});
```

In the `onInit` function we instantiate the `ResourceModel` that points to the new message bundle file where our texts are now located \(`i18n.properties file`\). The bundle name `sap.ui.demo.walkthrough.i18n.i18n` consists of the application namespace `sap.ui.demo.walkthrough` \(the application root as defined in the `index.html`\), the folder name `i18n` and finally the file name `i18n` without extension. The OpenUI5 runtime calculates the correct path to the resource; in this case the path to our `i18n.properties` file. Next, the model instance is set on the view as a named model with the key `i18n`. You use named models when you need to have several models available in parallel.

In the `onShowHello` event handler function we access the `i18n` model to get the text from the message bundle file and replace the placeholder `{0}` with the recipient from our data model. The `getProperty` method can be called in any model and takes the data path as an argument. In addition, the resource bundle has a specific `getText` method that takes an array of strings as second argument.

The resource bundle can be accessed with the `getResourceBundle` method of a `ResourceModel`. Rather than concatenating translatable texts manually, we can use the second parameter of `getText` to replace parts of the text with non-static data. During runtime, OpenUI5 tries to load the correct`i18n_*.properties` file based on your browser settings and your locale. In our case we have only created one `i18n.properties` file to make it simple. However, you can see in the network traffic of your browser’s developer tools that OpenUI5 tries to load one or more `i18n_*.properties` files before falling back to the default `i18n.properties` file.

***

### webapp/view/App.view.xml

``` xml
<mvc:View
   controllerName="sap.ui.demo.walkthrough.controller.App"
   xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc">
   <Button
      text*HIGHLIGHT START*="{i18n>showHelloButtonText}"*HIGHLIGHT END*
      press=".onShowHello"/>
   <Input
      value="{/recipient/name}"
      description="Hello {/recipient/name}"
      valueLiveUpdate="true"
      width="60%"/>
</mvc:View>

```

In the XML view, we use data binding to connect the button text to the `showHelloButtonText` property in the `i18n` model. A resource bundle is a flat structure, therefore the preceding slash \(/\) can be omitted for the path.

> Note:
> The description text is not completely localized in this example for illustration purposes. To be on the safe side, we would have to use a similar mechanism as in the controller to use a string from the resource bundle and replace parts of it. This can be done with the `jQuery.sap.formatMessage` formatter.
> 
> Furthermore, `i18n` files only impact client-side application texts. Texts that are loaded from back-end systems can appear in all languages that are supported by the back-end system.
> 
> 

***

### Conventions

-   The resource model for internationalization is called the `i18n` model.

-   The default filename is `i18n.properties`.

-   Resource bundle keys are written in \(lower\) camelCase.

-   Resource bundle values can contain parameters like `{0}`, `{1}`, `{2}`, …

-   Never concatenate strings that are translated, always use placeholders.

-   Use Unicode escape sequences for special characters.


**Related information**  


[Resource Model](Resource_Model_.md#loio91f122a36f4d1014b6dd926db0e91070)

[API Reference: `jQuery.sap.util.ResourceBundle`](https://openui5.hana.ondemand.com/#docs/api/symbols/jQuery.sap.util.ResourceBundle.html)

[API Reference: `sap.ui.model.resource.ResourceModel`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.resource.ResourceModel.html)

[Samples: `sap.ui.model.resource.ResourceModel` ](https://openui5.hana.ondemand.com/explored.html#/entity/sap.ui.model.resource.ResourceModel/samples)

