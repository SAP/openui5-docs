<!-- loio70ef981d350a495b940640801701c409 -->

| loio |
| -----|
| 70ef981d350a495b940640801701c409 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/70ef981d350a495b940640801701c409) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/70ef981d350a495b940640801701c409)</div>

## Step 7: JSON Model

Now that we have set up the view and controller, it’s about time to think about the M in MVC.

We will add an input field to our app, bind its value to the model, and bind the same value to the description of the input field. The description will be directly updated as the user types.

***

### Preview

   
  
An input field and a description displaying the value of the input field<a name="loio70ef981d350a495b940640801701c409__fig_r1j_pst_mr"/>

 ![](loioe5a9bb4cb06b4d9c8b37914bf5cd2d13_HiRes.png "An input field and a description displaying the value of the input
					field") 

***

### Coding

You can view and download all files at [Walkthrough - Step 7](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.07/preview).

``` js
sap.ui.define([
   "sap/ui/core/mvc/Controller",
   "sap/m/MessageToast"*HIGHLIGHT START*,
   "sap/ui/model/json/JSONModel"*HIGHLIGHT END*
], function (Controller, MessageToast, *HIGHLIGHT START*JSONModel*HIGHLIGHT END*) {
   "use strict";
   return Controller.extend("sap.ui.demo.walkthrough.controller.App", {
*HIGHLIGHT START*      onInit : function () {
         // set data model on view
         var oData = {
            recipient : {
               name : "World"
            }
         };
         var oModel = new JSONModel(oData);
         this.getView().setModel(oModel);
      },*HIGHLIGHT END*
      onShowHello : function () {
         MessageToast.show("Hello World");
      }
   });
});

```

We add an init function to the controller. `onInit` is one of OpenUI5’s lifecycle methods that is invoked by the framework when the controller is created, similar to a constructor function of a control.

Inside the function we instantiate a JSON model. The data for the model only contains a single property for the “recipient”, and inside this it also contains one additional property for the name.

To be able to use this model from within the XML view, we call the `setModel` function on the view and pass on our newly created model. The model is now set on the view.

The message toast is just showing the static "Hello World" message. We will show how to load a translated text here in the next step.

***

### webapp/view/App.view.xml

``` xml
<mvc:View
   controllerName="sap.ui.demo.walkthrough.controller.App"
   xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc">
   <Button
      text="Say Hello"
      press=".onShowHello"/>
 *HIGHLIGHT START*  <Input
      value="{/recipient/name}"
      description="Hello {/recipient/name}"
      valueLiveUpdate="true"
      width="60%"/>*HIGHLIGHT END*
</mvc:View>

```

We add an `sap.m.Input` control to the view. With this, the user can enter a recipient for the greetings. We bind its value to a OpenUI5 model by using the declarative binding syntax for XML views:

-   The curly brackets `{…}` indicate that data is taken from the value of the `recipient`'s object name property. This is called "data binding".

-    `/recipient/name` declares the path in the model.


***

### webapp/index.html

``` html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>SAPUI5 Walkthrough</title>
	<script
		id="sap-ui-bootstrap"
		src="https://openui5.hana.ondemand.com/resources/sap-ui-core.js"
		data-sap-ui-theme="sap_belize"
		data-sap-ui-libs="sap.m"
*HIGHLIGHT START*		data-sap-ui-compatVersion="edge"*HIGHLIGHT END*
		data-sap-ui-async="true"
		data-sap-ui-resourceroots='{
			"sap.ui.demo.walkthrough": "./"
		}'
		data-sap-ui-oninit="module:sap/ui/demo/walkthrough/index">
	</script>
	<script src="index.js"></script>
</head>
<body class="sapUiBody" id="content">
</body>
</html>
```

The binding of the value attribute is a simple binding example that contains only a binding pattern. We can also combine texts and binding pattern to a more complex binding result as seen in the description attribute. To be able to use the so-called complex binding syntax we have to enable it globally by setting the bootstrap parameter `data-sap-ui-compatVersion` to `edge`. If this setting is omitted, then only standard binding syntax is allowed, meaning "Hello `{/recipient/name}`" would not work anymore while "`{/recipient/name}`" would work just fine.

> Note:
> You can either use `data-sap-ui-compatVersion="edge"` or `data-sap-ui-bindingSyntax="complex"` in the script. By setting the "edge" compatibility mode, the complex binding syntax is automatically enabled. The `edge` mode automatically enables compatibility features that otherwise would have to be enabled manually. For more information, see [Compatibility Version Information](Compatibility_Version_Information_9feb96d.md).
> 
> 

***

### Conventions

-   Use Hungarian notation for variable names.


**Related information**  


[Model View Controller \(MVC\)](Model_View_Controller_(MVC)_91f2334.md)

[Data Binding](Data_Binding_68b9644.md)

[JSON Model](JSON_Model_.md#loio96804e3315ff440aa0a50fd290805116)

[API Reference: `sap.ui.define`](https://openui5.hana.ondemand.com/#/api/sap.ui/methods/sap.ui.define)

