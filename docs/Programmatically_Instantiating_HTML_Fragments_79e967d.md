| loio |
| -----|
| 79e967d093c247639cf60f77cee810d2 |

<div id="loio">

view on: [help.sap.com](https://help.sap.com/viewer/DRAFT/3237636b137e43519a20ad5513c49ccb/latest/en-US/79e967d093c247639cf60f77cee810d2.html) | [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/79e967d093c247639cf60f77cee810d2) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/79e967d093c247639cf60f77cee810d2)</div>
<!-- loio79e967d093c247639cf60f77cee810d2 -->

## Programmatically Instantiating HTML Fragments

For each fragment type, OpenUI5 provides a method that can be used to programmatically instantiate a fragment.

***

To give an example of a programmatic instantiation of an HTML fragment, you first have to define one. The following code presents an example definition:

```lang-js
<div data-sap-ui-type="sap.m.Button" data-press="doSomething" data-text="Hello World"></div>
```

This fragment can be instantiated from a controller as follows:

```lang-js
sap.ui.require(["sap/ui/core/Fragment"], function(Fragment) {
    Fragment.load({
        type: "HTML",
        name: "my.useful.UiPartZ",
        controller: oController // this specific fragment again needs a controller 
    }).then(function(myButton) {
        // ...
});
```

This instantiation can be done at any place in the code, given that a controller is available and the returned **button** can be used like any **button**.

