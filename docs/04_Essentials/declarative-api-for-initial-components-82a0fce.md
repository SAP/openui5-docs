<!-- loio82a0fcecc3cb427c91469bc537ebdddf -->

# Declarative API for Initial Components

The declarative API enables you to define the initially started component directly in the HTML markup.

***

<a name="loio82a0fcecc3cb427c91469bc537ebdddf__section_p1l_4by_jkb"/>

## Using the `ComponentSupport` Module

With the declarative `sap/ui/core/ComponentSupport` API, you can define the initially started component directly in the HTML markup instead of in the imperative way using JavaScript or TypeScript. The declarative `ComponentSupport` must be enabled via the bootstrap:

```html
<!-- index.html -->
<script id="sap-ui-bootstrap"
    src="resources/sap-ui-core.js"
    data-sap-ui-on-init="module:sap/ui/core/ComponentSupport"
    data-sap-ui-async="true"
    data-sap-ui-resource-roots='{ "my.app": "./" }'
    data-...="...">
</script>
```

This module scans the DOM for HTML elements containing a special data attribute named `data-sap-ui-component`. All DOM elements marked with this data attribute will be regarded as container elements into which a `sap/ui/core/ComponentContainer` is inserted. Additional data attributes are then used to define the constructor arguments of the created `ComponentContainer` instance, e.g. `data-name` for the name of the component which should be instantiated:

```html
<!-- index.html -->
<body id="content" class="sapUiBody sapUiSizeCompact" role="application">
    <div data-sap-ui-component
        data-id="myRootComponentContainer"
        data-name="my.app"
        data-height="100%"
        data-settings='{ "id": "myRootComponent" }'
        data-handle-validation="true"
        data-...="...">
    </div>
    <!-- ... -->
</body>
```

***

<a name="loio82a0fcecc3cb427c91469bc537ebdddf__section_tks_rby_jkb"/>

## Declarative Configuration of `ComponentContainer`

> ### Caution:  
> As HTML is case-insensitive, property or event names with upper-case characters have to be "escaped" with the hyphen character. This is similar to CSS attributes. In the following sample, the `handleValidation` argument of the `ComponentContainer` constructor is used:
> 
> ```html
> 
> <div data-sap-ui-component ... data-handle-validation="true"></div>
> 
> ```

> ### Note:  
> The following data attributes for registering event handlers have been deprecated since OpenUI5 version 1.120 and won't work in the next major version because of the removal of accessing the global namespace:
> 
> -   `data-component-created`
> 
> -   `data-component-failed`
> 
> 
> Alternatively, you can provide your own module in the bootstrap via `on-init`, in which you create an instance of the `ComponentContainer` in the JavaScript code:
> 
> ```html
> <!DOCTYPE html>
> <html>
>   <head>
>     <!-- .... -->
>     <script id="sap-ui-bootstrap"
>       src="resources/sap-ui-core.js"
>       data-sap-ui-on-init="module:my/app/bootstrap"
>       data-sap-ui-resource-roots='{ "my.app": "./" }'
>       data-sap-ui-async="true"
>       data-...="..."
>     ></script>
>   </head>
>   <body id="content" class="sapUiBody sapUiSizeCompact" role="application">
>   </body>
> </html>
> ```
> 
> ```
> // my/app/bootstrap.js
> sap.ui.define([
>   "sap/ui/core/ComponentContainer",
>   "sap/ui/core/library"
> ], (ComponentContainer, sapUiCoreLib) => {
>   "use strict";
>   const { Container } = sapUiCoreLib;
>   const oComponentContainer = new ComponentContainer({
>     name: "my.app",
>     manifest: true,
>     lifecycle: Container,
>     handleValidation: true,
>     componentCreated: function(oEvent) {
>       const oComponent = oEvent.getParameter("component");
>       // ...
>     },
>     componentFailed: function(oEvent) {
>       const oReason = oEvent.getParameter("reason");
>       // ...
>     }
>   });
>   oComponentContainer.placeAt("content");
> });
> ```

***

### Asynchronous loading with `ComponentSupport`

The `ComponentSupport` module enforces asynchronous module loading of the component with "manifest first". This means, that the `manifest.json` file is loaded before evaluating the component to optimize loading behavior. In this way libraries and other dependencies can be loaded asynchronously and in parallel. To achieve this, the following settings for the ComponentContainer are applied by default:

-   `async` \{\*boolean\*\} \(forced to `true`\)
-   `manifest` \{\*boolean|string\*\} \(forced to `true` if no string is provided to ensure manifest first\)
-   `lifecycle` \{\*sap.ui.core.ComponentLifecycle\*\} \(defaults to `Container`\)
-   `autoPrefixId` \{\*boolean\*\} \(defaults to `true`\)

For details on the manifest, see [Manifest \(Descriptor for Applications, Components, and Libraries\)](manifest-descriptor-for-applications-components-and-libraries-be0cf40.md).

See also [`ComponentSupport`](https://ui5.sap.com/#/api/module:sap/ui/core/ComponentSupport) and [`ComponentContainer`](https://ui5.sap.com/#/api/sap.ui.core.ComponentContainer) for more information. 

***

<a name="loio82a0fcecc3cb427c91469bc537ebdddf__section_zmp_rwc_kkb"/>

## Delay the Initial Component Instantiation

In some cases, the component initialisation must wait until all pre-required modules have been loaded. If this is the case, the `ComponentSupport` module needs to be executed later, and you have to replace the `on-init` module execution in the bootstrap with a custom module:

```html
<!-- index.html -->
<script id="sap-ui-bootstrap"
  src="resources/sap-ui-core.js"
  data-sap-ui-on-init="module:my/app/bootstrap"
  data-sap-ui-resource-roots='{ "my.app": "./" }'
  data-sap-ui-async="true"
  data-...="...">
</script>
```

The custom module can load dependencies and execute code before activating the `ComponentSupport` module:

```js
// my/app/bootstrap.js
sap.ui.define(["my/app/MyModule"], (MyModule) => {
  "use strict";
    // Execute code which needs to be executed before component initialization
    // Requiring the ComponentSupport module automatically executes the component initialisation for all declaratively defined components
    MyModule.init().then(() => sap.ui.require(["sap/ui/core/ComponentSupport"]));
});
```

