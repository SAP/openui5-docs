<!-- loio408b40efed3c416681e1bd8cdd8910d4 -->

| loio |
| -----|
| 408b40efed3c416681e1bd8cdd8910d4 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/408b40efed3c416681e1bd8cdd8910d4) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/408b40efed3c416681e1bd8cdd8910d4)</div>

## Performance: Speed Up Your App

If a web app has performance issues, finding the cause can be both a time-consuming and nerve-consuming task. To help you avoid and solve performance issues in your app, here are some good practices we've discovered while dealing with OpenUI5 apps.

OpenUI5 apps are basically JavaScript files sent to a client by a server and interpreted by the browser. So it's not only the coding of the app that can cause slow performance. It often turns out, for example, that the configuration is wrong. Slow networks or servers may also have a heavy impact on the performance of a web app. Let's have a look at the most common issues that impact performance.

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_AsyncLoading"/>

### Enable Asynchronous Loading in the Bootstrap

Configuration issues are often caused by an old bootstrap or a wrong usage of the activated features. Here's an example of what a bootstrap should look like for an up-to-date OpenUI5 app:

``` html
<script 
	id="sap-ui-bootstrap"
	src="/resources/sap-ui-core.js"
	data-sap-ui-theme="sap_belize"
	data-sap-ui-compatVersion="edge"
	*HIGHLIGHT START*data-sap-ui-async="true"*HIGHLIGHT END*
	data-sap-ui-onInit="module:my/app/main"
	data-sap-ui-resourceroots='{"my.app": "./"}'
>
```

The most important setting is `data-sap-ui-async="true"`. It enables the runtime to load all the modules and preload files for declared libraries asynchronously, if an asynchronous API is used. Setting `async=true` leverages the browser's capabilities to execute multiple requests in parallel, without blocking the UI.

The attribute `data-sap-ui-onInit` defines the module `my.app.Main`, which will be loaded initially.

> ### Note:  
> Configuration of the bootstrap can only be done for standalone applications and when the bootstrap is under control of the developer. The bootstrap of applications from a Fiori Launchpad is managed by the Launchpad.

> ### Note:  
> The `data-sap-ui-async="true"` configuration option requires extensive testing as well as cooperation on the application side to ensure a stable and fully working application. It is, therefore, **not** activated automatically, but needs to be configured accordingly. If you encounter issues or want to prepare your application for asynchronous loading, see [Is Your Application Ready for Asynchronous Loading?](Is_Your_Application_Ready_for_Asynchronous_Loading_493a15a.md) The bootstrap attribute `data-sap-ui-async="true"` affects both modules **and** preload files. If it is not possible to load the modules asynchronously \(e.g. for compatibility reasons\), use `data-sap-ui-preload="async"` to configure at least the preloads for asynchronous loading. For further information, see [Standard Variant for Bootstrapping](Standard_Variant_for_Bootstrapping_91f1f45.md).

If you listen to the `init` event as part of your `index.html` page, make sure that you implement the asynchronous behavior also here, as shown in the following code snippet:

``` html
<script>
	sap.ui.getCore().attachInit(function() {
		sap.ui.require(["sap/ui/core/ComponentContainer"], function(ComponentContainer) {
			new ComponentContainer({
				name: "your.component",
				manifest: true,
				height: "100%",
				componentCreated: function(oParams) {
					var oComponent = oParams.getParameter("component");
					// do something with the component instance
				}
			}).placeAt("content");
		});
	});
</script>
```

> ### Note:  
> Please note that this variant with inline scripting is not CSP-compliant. It is better to create a module with `sap.ui.define` which contains the startup code and load it via `data-sap-ui-onInit="module:my/app/main"` \( this usually also requires a declaration of `data-sap-ui-resourceroots`, e.g.: `data-sap-ui-resourceroots='{"my.app": "./"}` \).

> ### Note:  
> Applications without a descriptor file can declare additional dependencies explicitly via the bootstrap parameter `data-sap-ui-libs`. If those dependencies are not listed, such as transitive dependencies that are inherited from a listed library, OpenUI5 will load them automatically, but then has to first read the configured libraries and find out about these dependencies. This can take time as the application might benefit less from parallel loading.

**Additional Information:**

-   For more information about bootstrap attributes, see [Bootstrapping: Loading and Initializing](Bootstrapping_Loading_and_Initializing_a04b0d1.md)
-   Walkthrough tutorial, [Step 2: Bootstrap](Step_2_Bootstrap_fe12df2.md)
-   [Standard Variant for Bootstrapping](Standard_Variant_for_Bootstrapping_91f1f45.md)
-   [Best Practices for Asynchronous Loading in UI5](https://blogs.sap.com/2018/12/18/ui5ers-buzz-41-best-practices-for-async-loading-in-ui5/)

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_RoutingConfigured"/>

### Ensure that Root View and Routing are Configured to Load Targets Asynchronously

Please check the `rootView` of the application's `manifest.json` file for an `async=true` parameter. This allows the root view to be loaded asynchronously.

To configure the targets for asynchronous loading, please also check the [Routing Configuration](Routing_Configuration_9023130.md) for the `async=true` parameter.

``` json
"sap.ui5": {
	"rootView": {
        "viewName": "sap.ui.demo.walkthrough.view.App",
        "type": "XML",
        "id": "app",
         *HIGHLIGHT START*"async": true*HIGHLIGHT END*
    },
    "routing": {
        "config": {
            "routerClass": "sap.m.routing.Router",
            "viewType": "XML",
            "viewPath": "sap.ui.demo.walkthrough.view",
            "controlId": "app",
            "controlAggregation": "pages",
            *HIGHLIGHT START*"async": true*HIGHLIGHT END*
        }
    },
...
```

**Additional Information:**

-   Walkthrough tutorial, [Step 10: Descriptor for Applications](Step_10_Descriptor_for_Applications_8f93bf2.md)

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_AsyncModuleLoading"/>

### Make Use of Asynchronous Module Loading \(AMD Style\)

If modules follow the Asynchronous Module Definition \(AMD\) standard and the bootstrap flag `data-sap-ui-async` is set to `true`, custom scripts and other modules can also be loaded asynchronously when a preload is not available. It will help you in the future to enable asynchronous loading of individual modules combined with the usage of HTTP/2 or AMD-based module bundlers. It also ensures proper dependency tracking between modules.

But it isn't enough to write AMD modules. You also need to prevent access to OpenUI5 classes via global names. For instance, do not use global namespaces like `new sap.m.Button()` but require the `Button` and call its constructor via the local AMD reference instead.

 For more information, see the [API Reference: `sap.ui.define`](https://openui5.hana.ondemand.com/#/api/sap.ui/methods/sap.ui.define). 

Always avoid usages of `jQuery.sap.require` ! In order to enable modules to load asynchronously, use `sap.ui.define` to create modules \(e.g. controllers or components\) or `sap.ui.require` in other cases.

Please follow the [Best Practices for Loading Modules](Best_Practices_for_Loading_Modules_00737d6.md).

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_ManifestJson"/>

### Use `manifest.json` Instead of the Bootstrap to Define Dependencies

Don't specify a link to the CSS in the bootstrap of your app; use the `manifest.json` descriptor file instead.

Please use the `manifest.json` application descriptor file to declare dependencies. This has several advantages:

-   In the manifest, the dependency information is reusable; it works when the app runs standalone and when it is embedded in the Fiori Launchpad or some other launcher.
-   Moving the dependencies to the manifest loads them later and can therefore make the first rendering happen earlier. Obviously, that first rendering cannot come from the component then.
-   Design-time tools or runtime back-end services \(e.g. AppIndex in ABAP systems\) can use the manifest entries to determine the transitive closure of dependencies and thereby further optimise the parallel loading of dependencies. If the dependencies are maintained in the bootstrap, developers can do this by hand, but will have to update the information on each version upgrade.

Make sure that you don't load too many dependencies. In most apps it's enough to load the libraries `sap.ui.core` and `sap.m` by default, and add additional libraries only when needed.

If you want to make additional libraries generally known in your app, without directly loading them during the app start, you can add them to the dependency declaration in the `manifest.json` file with the `lazy` loading option. This makes sure that the libraries are only loaded when they are needed:

``` json
"sap.ui5": {
	"dependencies": {
		"minUI5Version": "1.70.0",
		"libs": {
			"sap.ui.core": {},
			"sap.m": {},
			"sap.ui.layout": {
				*HIGHLIGHT START*"lazy": true*HIGHLIGHT END*
			}
		},
...
```

If a library preload contains reuse components and this preload is configured to be loaded lazily \(via `"lazy": true` in the dependencies of the `manifest.json`\), the library is not available upon creation of the related component.

In this case you need to use `sap.ui.getCore().loadLibrary("my.library")` before creating the component \(e.g with `Component.create({ name: "my.component" })` or component usage `myComponent.createComponent("myUsage")`\).

An indicator that a component is inside a library is the existence of an entry `sap.app/embeddedBy` in its `manifest.json` file.

**Additional Information:**

-   [Descriptor for Applications, Components, and Libraries](Descriptor_for_Applications,_Components,_and_Libraries_be0cf40.md)

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_LoadFromCDN"/>

### Load OpenUI5 from the Content Delivery Network \(CDN\)

In order to ensure that all static SAPUI5 resources are served with the lowest possible latency in SAP Business Technology Platform scenarios, you can load the resources from the Content Delivery Network \(CDN\) cached by AKAMAI. Especially when running your app in the cloud, you benefit from the global distribution of servers. For other scenarios, it is possible to configure a custom CDN of choice as an external location.

**Additional Information:**

-   [Variant for Bootstrapping from Content Delivery Network](Variant_for_Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md)

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_Resources404"/>

### Ensure that all Resources are Properly Configured to Avoid 404 Errors

Languages can be configured in your manifest since UI5 version 1.77.

The manifest configuration for i18n has now the option to provide the `supportedLocales` and the `fallbackLocale`:

-   The `supportedLocales` should contain all languages for which you have i18n files. e.g. a file named `i18n_en.properties` has the locale `en`.
-   The `fallbackLocale` is the locale loaded before falling back to the root bundle.

**Example:** If the following language files exist:

-   `i18n_en.properties` \(English version, `"en"`\)
-   `i18n_de.properties` \(German version, `"de"`\)

they can be configured in your `manifest.json` in Section `sap.ui5` under `models`:

``` json
"sap.ui5": {
	"models": {
		"i18n": {
			"type": "sap.ui.model.resource.ResourceModel",
			"settings": {
				"bundleName": "sap.ui.demo.todo.i18n.i18n",
				"supportedLocales": ["en", "de"],
				"fallbackLocale": "en"
			}
		}
	}
}
```

With AppDescriptor version 1.21.0 this is also possible in the `i18n` section of `sap.app` in your `manifest.json`:

``` json
"sap.app": {
	"i18n": {
		"bundleUrl": "i18n/i18n.properties",
		"supportedLocales": ["en", "de"],
		"fallbackLocale": "en"
	}
}
```

-   [Identifying the Language Code / Locale](Identifying_the_Language_Code__Locale_91f21f1.md)
-   [Supported Locales and Fallback](Supported_Locales_and_Fallback_ec753bc.md)

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_ManifestFirst"/>

### Use "manifest first" to Load the Component

Load the `manifest.json` descriptor file of the component first to analyze and preload the dependencies when loading the component. For more information, see [Manifest First Function](Descriptor_for_Applications,_Components,_and_Libraries_be0cf40.md#loiobe0cf40f61184b358b5faedaec98b2da__manifirst).

``` js
// "Component" required from module "sap/ui/core/Component"
// load manifest.json from default location and evaluate it before creating an instance of the component 
Component.create({
  name: "my.component",
});
```

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_LibraryPreloads"/>

### Ensure that Library Preloads are Enabled

If the library preloads are disabled or not found, every module is loaded separately by an own request. Depending on the server and network infrastructure, this can take a lot of time. Except for debugging reasons, it is always recommended to make sure library preloads are used. Fortunately, the library preloads are active by default if the files are present.

In some cases it may happen that preloads are disabled:

-   The `data-sap-ui-preload` bootstrap attribute is empty or set to an invalid value. The attribute is optional and only necessary if the loading behavior \(sync / async\) needs to be overwritten manually.

-   Debug sources are enabled in the bootstrap \(`data-sap-ui-debug=true`\) or via the URL \(`sap-ui-debug=true`\).

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_ComponentPreload"/>

### Ensure that Application Resources are Loaded as Component Preload

Application modules \(e.g. components, controllers, views or resource bundles\) should be loaded asynchronously via the component preload file. Check \(e.g. via the Network tab in the Google Chrome developer tools\) if a component preload \(`Component-preload.js`\) is missing. If the application is not configured to load modules asynchronously, required application files may be loaded synchronously.

> ### Note:  
> If a component preload does not exist yet, the bundle needs to be created. For example, you may use the [UI5 Tooling](https://sap.github.io/ui5-tooling/).

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_NetworkRequests"/>

### Check the Network Requests

To quickly check the network load caused by your app, look at your browser's developer tools, for example the Network tab in the Google Chrome developer tools \([F12\]\). You'll see an overview of all requests being sent. Possible issues here may be:

***

#### Synchronous requests that block each other

In this case, use the `data-sap-ui-async="true"` setting in the bootstrap.

***

#### Too many requests

You can use the [UI5 Tooling](https://sap.github.io/ui5-tooling/) to bundle and minimize all relevant component files by creating a component-preload file.

If you're using OpenUI5 apps with grunt as a web server, you can use the `openui5_preload` task; for more information see [Optimizing OpenUI5/SAPUI5 Apps](http://scn.sap.com/community/developer-center/front-end/blog/2015/02/18/optimizing-openui5-apps) in the SAPUI5 Developer Center on SAP SCN.

If you're using SAP Web IDE, refer to [Application Build](https://help.sap.com/viewer/825270ffffe74d9f988a0f0066ad59f0/CF/en-US/dfb26ef028624cf486a8bbb0bfd459ff.html) in the SAP Web IDE documentation.

***

#### Back-end related performance issues

-   Slow database service \(e.g. OData\)

-   Slow web server or CDN issues \(e.g. serving of static resources\)
-   Slow network infrastructure \(e.g. mobile network\)
-   The h2 protocol is not supported \(only HTTP/1.1\); ideally, the h2 protocol should be supported by the web server

**Additional Information:**

-   To determine the minimum required bandwidth when using UI5-based applications, you can find further information in SAP Note [2240690](https://launchpad.support.sap.com/#/notes/2240690) on front-end network bandwidth sizing.

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_MigrateJquery"/>

### Migrate `jquery.sap.*` Modules to their Modularised Variants

Since UI5 version 1.58, the global `jquery.sap.*` modules are deprecated. Please use the modularised variant of the module. If you are still using the `jquery.sap.*` variants, a so-called "stubbing layer" may load the old module synchronously!

You can find a list of modules in the [Legacy jQuery.sap Replacement](Legacy_jQuery.sap_Replacement_a075ed8.md) documentation.

The usages can either be replaced manually or by the [UI5 Migration Tool](https://github.com/SAP/ui5-migration).

> ### Note:  
> Please make sure to declare the required modules in `sap.ui.define` or `sap.ui.require` to ensure that they get loaded asynchronously.

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_MigrateFactories"/>

### Migrate Synchronous Variants of UI5 Factories to Asynchronous Variants

Check if the application uses synchronous UI5 factories. Many asynchronous variants are available, e.g. for Components, Resource Bundles, Controllers, Views and Fragments. Please visit the following overview:[Legacy Factories Replacement](Legacy_Factories_Replacement_491bd9c.md).

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_ModelPreload"/>

### Use the OData Model Preload

Components can preload models for which modules are already loaded; otherwise a warning will be shown. The OData model \(V2 or V4\) benefits especially, because the metadata can be loaded in parallel during a component load.

``` json
"sap.ui5": {
  ...
  "models": {
      "mymodel": {
          "preload": true,
...
```

For the OData V2 model, also consider using the model parameter `earlyTokenRequest`. For more information, see the [API Reference: `sap.ui.model.odata.v2.ODataModel`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v2.ODataModel). 

For the OData V4 model, also consider using the model parameter `earlyRequests`. For more information, see the [API Reference: `sap.ui.model.odata.v4.ODataModel`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel). 

For more information, see [Manifest Model Preload](Manifest_Model_Preload_26ba6a5.md).

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_MetadataCaching"/>

### Use OData Metadata Caching

To ensure fast loading times for **SAP Fiori applications started from the SAP Fiori launchpad**, the OData metadata is cached on the web browser using cache tokens. The tokens are added with the parameter `sap-context-token` to the URL of metadata requests. Please check via the developer tools of your browser \(e.g. the Network tab in the Google Chrome developer tools\) if the token has been appended to the request URL.

> ### Note:  
> This feature is currently only supported for ABAP back ends.

**Additional Information:**

-   [Cache Buster for OData Metadata of SAP Fiori Apps](https://help.sap.com/viewer/a7b390faab1140c087b8926571e942b7/7.52.0/en-US/876e43a272cc45cb82dea640edff0ab2.html)

-   [Scheduling Update of OData Metadata Caching](https://help.sap.com/viewer/a7b390faab1140c087b8926571e942b7/7.52.0/en-US/2439967f0c284f6caf05e4323dd9292e.html)


***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_useSelectQuery"/>

### Use a `$select` Query when Binding an Aggregation in the OData V2 Model

With a `$select` query you enable your application to fetch only necessary properties of an entity from the collection.

As an example, consider the EntityType "Customers", which is available from the public Northwind OData service at [https://services.odata.org/V2/Northwind/Northwind.svc/Customers?$format=json](https://services.odata.org/V2/Northwind/Northwind.svc/Customers?$format=json). It has several properties.

If you have an `sap.m.List` that only needs to display the `CompanyName` from the collection, you could add the following to your XML view:

``` xml
...
<List
    id="myList"
    ...
    items="{
        path: '/Customers',
        parameters: {
            select: 'CustomerID,CompanyName'
        }
    }">
    ...
```

Note that all key properties, such as the `CustomerID`, should still be added, even though they're not directly relevant to the user.

As a result, the response size of your application is reduced significantly. You also enable the back end to perform a more efficient database query.

In the OData V4 model, `$select` and `$expand` values can be automatically defined. For more information, see [Automatic determination of $expand and $select](Automatic_determination_of_$expand_and_$select_10ca58b.md).

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_ListsTables"/>

### Check Lists and Tables

The performance limits are reached differently depending on the used browser, operating system and hardware. Therefore, it is important to be mindful about the amount of controls and data bindings. This applies especially to lists and their variants \(e.g. `sap.m.Table` or `sap.ui.table.Table`\):

-   If a table needs to display more than 100 rows, please use `sap.ui.table.Table` instead of `sap.m.Table` The reason for this is that `sap.m.Table` keeps every loaded row in memory, even if not visible after scrolling. To choose the right table variant for your requirements, check out the documentation about [Tables: Which One Should I Choose?](Tables_Which_One_Should_I_Choose_148892f.md)
-   If the table rows contain multiple controls and/or custom-data fields, please check if they are required, or if another control can replace them. For example, another list like a ComboBox inside of a table cell may create many controls for every row, which can be very expensive.
-   Check tables for hidden columns and load only the visible ones, if possible.

**Additional Information:**

-    [Performance of Lists and Tables](Performance_of_Lists_and_Tables_f6a1a0a.md)


***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_OptimizeCode"/>

### Further Code Optimization

-   Use asynchronous view loading as described here: [Instantiating Views](Instantiating_Views_68d0e58.md).

-   Use the OData V4 model, which has an improved performance over the OData V2 model.

    Visit the [OData V4 Model](OData_V4_Model_5de13cf.md) documentation and ensure that all required features are available.

    For a quick start, follow the [OData V4](OData_V4_bcdbde6.md) tutorial.

-   If you use data binding with an OData V2 service as a back end, you should consider switching your OData model to our more updated OData V2 model. For more information, see [OData V2 Model](OData_V2_Model_6c47b2b.md#loio6c47b2b39db9404582994070ec3d57a2).

-   Optimize dependent bindings as described here: [Optimizing Dependent Bindings](OData_V2_Model_6c47b2b.md#loio62149734b5c24507868e722fe87a75db).

-   Avoid the usage of `setTimeout()` calls with values greater than `0`. This usually indicates an anti-pattern in application code that is used as a workaround and should be avoided. For more information, see also [JavaScript Code Issues: Don't use timeouts](JavaScript_Code_Issues_030fcd1.md#loio030fcd14963048218488048f407f8f34__11).

-   Don't use visibility for lazy instantiation. For more information, see [Performance Issues: Don't use visibility for lazy instantiation](Performance_Issues_966d67c.md#loio966d67c8cc5046419d1b35556cd9e447__1).

-   Please ensure the application does not block the rendering while waiting for back-end requests to respond. Waiting for data before rendering anything is not the favored user experience. It is recommended to load data asynchronously and already render the page while the request is pending. Mostly, the requests won't fail, and if they do, it is better to show an error or to navigate to an error page.
-   If an `XML Preprocessor` is used, we recommend to use the [XML View Cache](XML_View_Cache_3d85d5e.md). If configured in the XML View and with a properly implemented key provider \(for invalidation\), it is able to cache already processed XML View Preprocessor results.

**Related Information**  


[Coding Issues to Avoid: Performance Issues](Performance_Issues_966d67c.md)

[Performance Measurement Using sap/ui/performance/Measurement Module](Performance_Measurement_Using_sapuiperformanceMeasurement_Module_78880c0.md)

[Blog: SAPUI5 Application Startup Performance – Best Practices](https://blogs.sap.com/2016/10/29/sapui5-application-startup-performance-best-practices/)

[Blog: SAPUI5 Application Startup Performance – Advanced Topics](https://blogs.sap.com/2016/11/19/sapui5-application-startup-performance-advanced-topics/)

