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
sap.ui.require(["sap/ui/core/Fragment"], function(Fragment) {
    Fragment.load({
        name: "my.useful.VerySimpleUiPart"
    }).then(function(myButton) {
        // ...
    });
});
```

> Note:
> This specific fragment does not use a controller; if controls inside a fragment needs methods that are to be defined in a controller, the controller has to be referred to in an additional parameter.
> 
> 

Fragments can be instantiated from JSViews, as well. Fragments of any type can be used within views of any type.

If XML fragments are used within XML views, giving the view ID as fragment ID will allow calling `this.byId(…)` in the view’s controller to retrieve controls inside the fragment. The following code inside the controller will instantiate the above fragment with the `Button` and then again retrieve the `Button`:

``` xml
sap.ui.require(["sa/ui/core/Fragment"], function(Fragment) {
    Fragment.load({
        name: "my.useful.VerySimpleUiPart"
    }).then(function(myButton) {
        // ...
    });
});
var theSameButton = this.byId("btnInFragment"); // returns the button in the fragment
```

