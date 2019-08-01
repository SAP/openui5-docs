<!-- loio91f2c9076f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f2c9076f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f2c9076f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f2c9076f4d1014b6dd926db0e91070)</div>

## Initialization Process

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

### Initialization Readiness

The optimal point in time to execute or start an application is after the framework has been initialized. You can use the `attachInit` function to determine this point in time: The callback of the [`attachInit`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Core/methods/attachInit) function is executed directly after the framework has been initialized.

``` js
sap.ui.getCore().attachInit(function(){
    // application can be started
});
```

As an alternative, you can also use a bootstrap module, see [Standard Variant for Bootstrapping](Standard_Variant_for_Bootstrapping_91f1f45.md).

 <a name="loio91f2c9076f4d1014b6dd926db0e91070 loiobf10bd41ac8f49048a1ccb743fbfbb8a__loiobf10bd41ac8f49048a1ccb743fbfbb8a"/>

<!-- loiobf10bd41ac8f49048a1ccb743fbfbb8a -->

## Loading of Additional Resources During Bootstrap

The OpenUI5 runtime loads and interprets additional resources for the control libraries during bootstrap.

The files are loaded in the following sequence:

1.  Library bootstrap file `/<context-path>/resources/<library-name>/library.js` 

    A JavaScript file that contains the JavaScript code for all enumeration types provided by the library as well as library-specific initialization code that is independent from the controls in the library. The file calls the `sap.ui.getCore().initLibrary` method with an object that describes the content of the library \(list of contained controls, elements etc.\). For libraries that have been developed with OpenUI5 application development tools or the OpenUI5 offline build tools, this file is generated automatically during the build

2.  Library style sheet file `/<context-path>/resources/<library-name>/themes/<theme-name>/library.css`

    OpenUI5A standard CSS file that contains all styles relevant for this library. For application development tools, this file is generated automatically during the build.


 <a name="loio91f2c9076f4d1014b6dd926db0e91070 loiobbce44f06ddc48fda7aeb44eae52ebbc__loiobbce44f06ddc48fda7aeb44eae52ebbc"/>

<!-- loiobbce44f06ddc48fda7aeb44eae52ebbc -->

## Dynamic Loading of Libraries

OpenUI5 provides the `sap.ui.getCore().loadLibary()` method to load libraries at runtime in addition to the libraries declared in the runtime configuration.

After loading, you can use all controls from the library. For these additional libraries, the same restriction apply as for the declared libraries: Accessing the document object model \(DOM\) is only possible after the `document.ready` event of the HTML page. Also, rendering applies for these libraries in the same way as for the declared libraries.

