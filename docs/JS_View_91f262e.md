<!-- loio91f262ef6f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f262ef6f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f262ef6f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f262ef6f4d1014b6dd926db0e91070)</div>

## JS View

You create a JS \(JavaScript\) view in the same way as a controller and use the suffix `.view.js` for the file.

 OpenUI5 provides the following two default methods for implementation:

-   `getControllerName()`: Specifies the controller belonging to this view

    If this method is not implemented or returns `NULL`, the view has no controller.

-   `createContent()`: Called initially once after the controller has been instantiated

    This method is used to create the UI. As the method knows the controller, it can directly attach the event handlers.


> Note:
> ``` js
>    sap.ui.jsview("sap.hcm.Address", {  // this View file is called Address.view.js
>    
>    getControllerName: function() {
>       return "sap.hcm.Address";     // the Controller lives in Address.controller.js
>    },
> 
>    createContent: function(oController) {
>       var oButton = new sap.m.Button({text:"Hello JS View"});
>       oButton.attachPress(oController.handleButtonClicked);
>       return oButton;
>    }
> 
> });
> ```
> 
> 

The string in quotes denotes the view name that equals the OpenUI5 module name within the define/require concept.

> Note:
> In event handlers for controls "this" usually denotes the control itself. This is unexpected when it happens in event handlers that are implemented inside controllers: The controller would usually expected to be denoted as "this". This is no issue for declarative view types, but for JSViews the view developer may need to modify the "this" context as follows:
> 
> ``` js
>    ...
>       oButton.attachPress(jQuery.proxy(oController.handleButtonClicked, oController));
>    ...
> 
> ```
> 
> Alternatively, the view developer can give the event handler method in an array where the second element is the "this" object:
> 
> ``` js
>    ...
>       var oButton = new sap.m.Button({
>          text: "Hello JS View",
>          press: [oController.handleButtonClicked, oController]
>       });
>    ...
> 
> ```
> 
> 

> Note:
> If you want to define IDs for controls inside a JSView to guarantee their uniqueness when reusing views, you can **not** give hardcoded IDs, but have to give the view the opportunity to add its own instance ID as a prefix. This is done by using the `View.createId(...)` method. For the example above, this is done as follows:
> 
> ``` js
> var oButton = new sap.m.Button(this.createId("myButton"), {text:"Hello JS View"});
> ```
> 
> This is not required for declarative view types as the view parser can manage this automatically, see [Support for Unique IDs](Support_for_Unique_IDs_91f28be.md).
> 
> 

