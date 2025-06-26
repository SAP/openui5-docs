<!-- loio91f2c9076f4d1014b6dd926db0e91070 -->

# Initialization Process

The initialization process starts after OpenUI5 runtime is loaded.

The initialization of the OpenUI5 runtime comprises the following steps:

1.  The jQuery plugins, which are mainly located in the `jQuery.sap` namespace, provide fundamental functionality of OpenUI5, such as the modularization concept, a logging framework, performance measurement, and so on.

2.  The global object `sap` is defined.

3.  The `sap.ui.core.Core` class is executed with all its dependencies.

4.  The runtime configuration is determined from different sources.

5.  All libraries and modules declared in the configuration as well as their dependencies are loaded.

6.  For each loaded library, the CSS file of the configured theme is loaded.

7.  When all libraries are loaded and the document is ready, the `initEvent` of the core is fired and all registered handlers are executed.


***

<a name="loio91f2c9076f4d1014b6dd926db0e91070__section_d2s_tlg_vgb"/>

## Initialization Readiness

The optimal point in time to execute or start an application is after the framework has been initialized. There are three ways to hook yourself into this timeframe. The following list describes these initialization readiness hooks in detail and gives you examples when to use them. Depending on your use case you might prefer one way over another.

***

### `ComponentSupport` module

The most sophisticated way to execute code after the framework has been initialized is to use `sap.ui.core.ComponentSupport`. This option is viable for scenarios in which you want to use an `sap.ui.core.UIComponent` as the entry point of your application.

`ComponentSupport` allows you to declaratively define one or more `sap.ui.core.UIComponent` instances in your HTML file and takes care of creating the necessary `sap.ui.core.ComponentContainer` for you.

For a detailed usage guide, please see the [`ComponentSupport` documentation](declarative-api-for-initial-components-82a0fce.md).

***

### Standalone `data-sap-ui-on-init` module

Besides using `sap.ui.core.ComponentSupport`, you can also define a data attribute called `data-sap-ui-on-init` on the OpenUI5 bootstrap script element.

This attribute should reference a valid OpenUI5 module as shown in the snippet below. In this sample you can also see how to use the `data-sap-ui-resource-roots` as part of your init module path.

```html
<script id="sap-ui-bootstrap"
        src="https://ui5.sap.com/resources/sap-ui-core.js"
       ...
        data-sap-ui-resource-roots='{"Startup": "./some/folder"}'
        data-sap-ui-on-init="module:Startup/my/module"
       ...
        data-sap-ui-async="true">
</script>
```

The OpenUI5 core will make sure that the `data-sap-ui-on-init` module is loaded and executed at the correct point in time after the initialization process of the framework. Inside this module you can then execute additional application code, e.g. create a new XML View instance.

Additionally, a dedicated `on-init` module allows for better [CSP compliance](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP) depending on your requirements, since no additional inline `<script>` tag is needed.

Please also have a look at our tutorial section, including the [Quickstart Tutorial](https://help.sap.com/viewer/93953b95df5f4e938c8eb421cef56319/1.138_SAPUI5_ABAP/en-US/592f36fd077b45349a67dcb3efb46ab1.html "Unleash your SAPUI5 skills with this simple three-step tutorial. We start with a simple "Hello World" example, and convert it to a minimalist two-page app.") :arrow_upper_right: tutorial for a broader sample.

***

### `Core.ready()` Promise

The `Core.ready()` function, where `Core` is required from the `sap/ui/core/Core` module, returns a promise which resolves after the framework has been initialized. This code can be written inside your main HTML file in a separate inline `<script>` tag:

```js
sap.ui.require(["sap/ui/core/Core"], function (Core) {
    Core.ready().then( () => {
        // application can be started
    });
});
```

<a name="loiobf10bd41ac8f49048a1ccb743fbfbb8a"/>

<!-- loiobf10bd41ac8f49048a1ccb743fbfbb8a -->

## Loading of Additional Resources During Bootstrap

The OpenUI5 runtime loads and interprets additional resources for the control libraries during bootstrap.

The files are loaded in the following sequence:

1.  Library bootstrap file `/<context-path>/resources/<library-name>/library.js` 

    A JavaScript file that contains the JavaScript code for all enumeration types provided by the library as well as library-specific initialization code that is independent from the controls in the library. The file calls the `sap/ui/core/Lib.init` method with an object that describes the content of the library \(list of contained controls, elements etc.\). For libraries that have been developed with OpenUI5 application development tools or the OpenUI5 offline build tools, this file is generated automatically during the build

2.  Library style sheet file `/<context-path>/resources/<library-name>/themes/<theme-name>/library.css`

    A standard CSS file that contains all styles relevant for this library. For application development tools, this file is generated automatically during the build.


<a name="loiobbce44f06ddc48fda7aeb44eae52ebbc"/>

<!-- loiobbce44f06ddc48fda7aeb44eae52ebbc -->

## Dynamic Loading of Libraries

OpenUI5 provides the `Libary.load()` method to load libraries at runtime in addition to the libraries declared in the runtime configuration. `Library` is required from the `sap/ui/core/Lib` module.

After loading, you can use all controls from the library. For these additional libraries, the same restriction apply as for the declared libraries: Accessing the document object model \(DOM\) is only possible after the `document.ready` event of the HTML page. Also, rendering applies for these libraries in the same way as for the declared libraries.

