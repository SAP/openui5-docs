<!-- loio82a0fcecc3cb427c91469bc537ebdddf -->

| loio |
| -----|
| 82a0fcecc3cb427c91469bc537ebdddf |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/82a0fcecc3cb427c91469bc537ebdddf) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/82a0fcecc3cb427c91469bc537ebdddf)</div>

## Declarative API for Initial Components

The declarative API enables you to define the initially started component directly in the HTML markup.

With the declarative API it is possible to define the initially started component directly in the HTML markup instead of the imperative way using JavaScript.

To define the initial component in a declarative way, use the `ComponentSupport` module. This module reads the DOM and searches for HTML elements containing a custom data attribute which is used to place the component at the right position:

``` html
<div data-sap-ui-component data-name="my.component"></div>
<div data-sap-ui-component data-name="my.component2"></div>
```

This feature is not active by default, but must be enabled inside the bootstrap:

``` html
<script id="sap-ui-bootstrap"
    src="resources/sap-ui-core.js"
    data-sap-ui-async="true"
    data-sap-ui-theme="sap_belize"
 
    data-sap-ui-onInit="module:sap/ui/core/ComponentSupport"> <!-- Enable declarative component support -->
</script>
```

The `ComponentSupport` module enforces asynchronous module loading of the component with "manifest first". This means, that the `manifest.json` file is loaded before evaluating the component to optimize loading behavior. For details, see [Descriptor for Applications, Components, and Libraries](Descriptor_for_Applications,_Components,_and_Libraries_be0cf40.md).

In some cases, the component initialisation must wait until all pre-required modules have been loaded. If this is the case, the `ComponentSupport` module needs to be executed later and you have to replace the `onInit` module execution in the bootstrap with a custom module:

**index.html**

``` html
<script id="sap-ui-bootstrap"
    src="resources/sap-ui-core.js"
    data-sap-ui-async="true"
    data-sap-ui-theme="sap_belize"
 
    data-sap-ui-onInit="module:sap/ui/demo/bootstrap"> <!-- Execute custom module on init -->
</script>
```

The custom module can load dependencies and execute code before activating the `ComponentSupport` module:

**sap/ui/demo/bootstrap.js**

``` js
1   sap.ui.define(["sap/ui/demo/MyModule"], function(MyModule) {
2
3          // Execute code which need to be executed before component initialization
4           MyModule.init().then(function() {
5               // Executes the component initialisation
6               sap.ui.require(["sap/ui/core/ComponentSupport"]);
7           });
8
9   });
```

