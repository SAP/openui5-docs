<!-- loio91f1f4536f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f1f4536f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/91f1f4536f4d1014b6dd926db0e91070) | [demo kit latest release](https://sdk.openui5.org/topic/91f1f4536f4d1014b6dd926db0e91070)</div>

## Standard Variant for Bootstrapping

The standard variant for bootstrapping loads all JavaScript modules of a library in advance with one single request for performance reasons.

The library preload file `library-preload.js` contains all modules of a certain library. These modules will only be executed on demand, if the application requires them. Using preloads significantly reduces the number of roundtrips since the single modules are bundled in one file.

> ### Note:  
> An application must **not** reference the `library-preload.js`. If preload files exist, OpenUI5 automatically loads them. The dependencies to libraries are defined as part of the manifest namespace `sap.ui5/dependencies/libs`. For further information, see [Descriptor for Applications, Components, and Libraries \(manifest.json\)](Descriptor_for_Applications_Components_and_Libraries_manifest_json_be0cf40.md).

By setting the `async=true` configuration parameter, the module loader loads the modules and preload files asynchronously. You can enable it in an existing application by specifying the `sap-ui-async` configuration parameter in the start URL, or by adding the `data-sap-ui-async` attribute to the bootstrap tag:

```html
<script
    id="sap-ui-bootstrap"
    src="resources/sap-ui-core.js"
    data-sap-ui-async="true"
    data-sap-ui-on-init="module:my/app/main"
    data-sap-ui-resource-roots='{"my.app": "./"}'
></script>
```

> ### Note:  
> Before you use the `async` configuration parameter, make sure your app is ready for asynchronous loading, see [Best Practices for Loading Modules](Best_Practices_for_Loading_Modules_00737d6.md) and [Is Your Application Ready for Asynchronous Loading?](Is_Your_Application_Ready_for_Asynchronous_Loading_493a15a.md).

**Related Information**  


[noJQuery Variant for Bootstrapping](noJQuery_Variant_for_Bootstrapping_91f1dd0.md "The noJQuery variant supports bootstrapping for an application that already integrates jQuery or uses a different jQuery version than OpenUI5.")

[Configuration of the OpenUI5 Runtime](Configuration_of_the_OpenUI5_Runtime_91f08de.md "OpenUI5 provides several options for the configuration of the OpenUI5 runtime. The possible ways to provide input for the available configuration options are described in detail.")

[Is Your Application Ready for Asynchronous Loading?](Is_Your_Application_Ready_for_Asynchronous_Loading_493a15a.md "Find a collection of information that helps you to find out if your application is ready for asynchronous loading.")

