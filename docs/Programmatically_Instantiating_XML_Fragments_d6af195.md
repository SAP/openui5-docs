<!-- loiod6af195124cf430599530668ddea7425 -->

| loio |
| -----|
| d6af195124cf430599530668ddea7425 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/d6af195124cf430599530668ddea7425) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/d6af195124cf430599530668ddea7425)</div>

## Programmatically Instantiating XML Fragments

For each fragment type, OpenUI5 provides a method that can be used to programmatically instantiate a fragment.

***

To give an example of a programmatic instantiation of an XML fragment, you first have to define one. The following code presents an example definition:

``` xml
<Button xmlns="sap.ui.commons" id="btnInFragment" text="Hello World" />
```

This fragment can be instantiated from a controller as follows:

``` xml
// "Fragment" required from module "sap/ui/core/Fragment"
Fragment.load({
    name: "my.useful.VerySimpleUiPart"
}).then(function(oMyButton) {
    // ...
});
```

> ### Note:  
> This specific fragment does not use a controller; if controls inside a fragment need methods that are defined in a controller, the controller has to be given as an additional parameter.

Fragments can be instantiated from JSViews, as well. Fragments of any type can be used within views of any type.

If XML fragments are used within XML views, you can use the view ID also as the fragment ID. This will allow you to call `this.byId(…)` in the view’s controller in order to retrieve controls inside the fragment. The following code inside the controller will instantiate the above fragment with the `Button` and then again retrieve the `Button` via its ID:

``` xml
// "Fragment" required from module "sap/ui/core/Fragment"
// The variable 'this' is a controller instance in this example
Fragment.load({
    name: "my.useful.VerySimpleUiPart"
}).then(function(myButton) {
    // Retrieve the button via its ID
    // in this exsample: myButton == theSameButton
    var theSameButton = this.byId("btnInFragment");
});
```

> ### Caution:  
> Make sure that you are correctly chaining to the `Fragment.load` Promise!
> 
> Calling `sap.ui.getCore().byId("...")` or `oController.byId("...")` before the `Fragment.load` Promise is resolved will result in `undefined`.

**Related Information**  


[API Reference: `Fragment.load()`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Fragment/methods/sap.ui.core.Fragment.load)

