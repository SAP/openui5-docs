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

### Use Asynchronous Loading

Configuration issues are often caused by an old bootstrap or a wrong usage of the activated features. Here's an example of what a bootstrap should look like for an up-to-date OpenUI5 app:

``` html
<script id="sap-ui-bootstrap"
	src="openui5/resources/sap-ui-core.js"
	data-sap-ui-libs="sap.m"
	data-sap-ui-theme="sap_belize"
	data-sap-ui-bindingSyntax="complex"
	data-sap-ui-compatVersion="edge"
	*HIGHLIGHT START*data-sap-ui-async="true"*HIGHLIGHT END*
	data-sap-ui-resourceroots='{
		"your.app": "yourDir/"
}'>
```

> Note:
> For more information about bootstrap attributes, see [Bootstrapping: Loading and Initializing](Bootstrapping_Loading_and_Initializing__a04b0d1.md).
> 
> 

The most important setting is `data-sap-ui-async="true"`. This enables the runtime to load all the modules and preload files for all declared libraries asynchronously, if an asynchronous API is used. Setting `async=true` leverages the browser's capabilities to execute multiple requests in parallel, without blocking the UI thread.

> Note:
> The `data-sap-ui-async="true"` configuration option requires extensive testing as well as cooperation on the application side to ensure a stable and fully working application. It is, therefore, **not** activated automatically, but needs to be configured accordingly. If you encounter issues, or want to prepare your application for asynchronous loading, see [Is Your Application Ready for Asynchronous Loading?](Is_Your_Application_Ready_for_Asynchronous_Loading_493a15a.md) The bootstrap attribute `data-sap-ui-async="true"` affects both modules **and** preload files. If it is not possible to load the modules asynchronously \(e.g. for compatibility reasons\), use `data-sap-ui-preload="async"` to configure at least the preloads for asynchronous loading. For further information, see [Standard Variant for Bootstrapping](Standard_Variant_for_Bootstrapping_91f1f45.md).
> 
> 

The `index.html` file:

``` html
...
<scriptr
	id="sap-ui-bootstrap"
	src="/resources/sap-ui-core.js"
	data-sap-ui-theme="sap_belize"
	data-sap-ui-compatVersion="edge"
	data-sap-ui-async="true"
	data-sap-ui-onInit="module:my/app/main"
	data-sap-ui-resourceRoots='{"my.app": "./"}'
></script>
```

If you listen to the `init` event as part of your `index.html` page, make sure that you implement the asynchronous behavior also here, as shown in the following code snippet.

> Note:
> We recommend that you do **not** use this anymore, because inline scripting is not CSP compliant.
> 
> 

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

> Note:
> Applications without a descriptor file can declare additional dependencies explicitly via the bootstrap parameter `data-sap-ui-libs`. If those dependencies are not listed, such as transitive dependencies that are inherited from a listed library, OpenUI5 will load them automatically, but then has to first read the configured libraries and find out about these dependencies. This can take time as the application might benefit less from parallel loading.
> 
> 

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_AsyncModuleLoading"/>

### Make Use of Asynchronous Module Loading \(AMD Style\)

If modules follow the synchronous module defintion \(AMD\) standard and the bootstrap flag `data-sap-ui-async` is set to `true`, custom scripts and other modules can also be loaded asynchronously when the preload is not available. It will help you in the future to enable asynchronous loading of individual modules combined with the usage of HTTP/2 or AMD-based packagers. It also ensures proper dependency tracking between modules.

But it isn't enough to write AMD modules. You also need to prevent access to OpenUI5 classes via global names. Do not use `new sap.m.Button()`, but require the `Button` and call the constructor via the local AMD reference.

For more information, see the [API Reference for `sap.ui.define`](https://openui5.hana.ondemand.com/api/sap.ui#methods/sap.ui.define) in the Demo Kit.

Avoid usages of `sap.ui.requireSync` and `jQuery.sap.require` whenever possible! To enable modules to load asynchronously, please use `sap.ui.define` to create modules \(e.g. controllers or components\) or `sap.ui.require` in other cases.

Please follow the guide [Best Practices for Loading Modules](Best_Practices_for_Loading_Modules_00737d6.md).

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_ManifestJson"/>

### Use the `manifest.json` Descriptor File instead of the Bootstrap to define Dependencies

Don't specify a link to the CSS in the bootstrap of your app; use the `manifest.json` descriptor file instead.

We recommend using the `manifest.json` application descriptor file to declare dependencies, because this way you can benefit from the preload features of the component factory, which shortens the loading times.

Make sure that you don't load too many dependencies. In most apps, it's enough to load the `sap.ui.core` and the `sap.m` library by default and add additional libraries only when needed.

If you want to make additional libraries generally known in your app, without directly loading them during the app start, you can add them to the dependency declaration in the `manifest.json` file with the `lazy` loading option, which makes sure that the libraries are only loaded when they are needed:

``` json
"sap.ui5": {
	"rootView": {
		"viewName": "app.view.Main",
		"type": "XML",
		"async": true
	},
	"dependencies": {
		"minUI5Version": "1.30.0",
		"libs": {
			"sap.ui.core": {},
			"sap.m": {},
			"sap.ui.layout": {
				*HIGHLIGHT START*"lazy": true*HIGHLIGHT END*
			}
		},
...
```

For more information, see [Descriptor for Applications, Components, and Libraries](Descriptor_for_Applications,_Components,_and_Libraries_be0cf40.md).

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_LoadFromCDN"/>

### Load OpenUI5 from the Content Delivery Network \(CDN\)

In order to ensure that all static SAPUI5 resources are served with the lowest possible latency in SAP Cloud Platform scenarios, you can load the resources from the Content Delivery Network \(CDN\) cached by AKAMAI. Especially if you're running your app in the cloud, you benefit from the global distribution of servers. For other scenarios, it is possible to configure a custom CDN of choice as an external location.

For more information, see [Variant for Bootstrapping from Content Delivery Network](Variant_for____________Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md).

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_Resources404"/>

### Ensure that all Resources are Available to Avoid 404 Errors

Provide i18n files for all languages used in your application. See: [Identifying the Language Code / Locale](Identifying_the_Language_Code__Locale_91f21f1.md)

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_ManifestFirst"/>

### Use "manifest first" to load the Component

Load the `manifest.json` descriptor file of the component first to analyze and preload the dependencies when loading the component. For more information, see [Manifest First Function](Descriptor_for_Applications,_Components,_and_Libraries_be0cf40.md#loiobe0cf40f61184b358b5faedaec98b2da__manifirst).

``` js
// "Component" required from module "sap/ui/core/Component"
// load manifest.json from default location and evaluate it before creating an instance of the component 
Component.create({
  name: "sap.my.component",
});
```

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_LibraryPreloads"/>

### Ensure that Library Preloads are Enabled

If the library preloads are disabled or not found, every module is loaded separately by a request of its own. Depending on the server and network infrastructure, this can take a lot of time. Except for debugging reasons, it is always recommended to make sure library preloads are used. Fortunately, the library preloads are active by default if the files are present.

In some cases it may happen that preloads are disabled:

-   The `data-sap-ui-preload` bootstrap attribute is empty or set to an invalid value. The attribute is optional and only necessary if the the loading behaviour \(sync / async\) needs to be overwritten manually.

-   Debug sources are enabled in the bootstrap \(`data-sap-ui-debug=true`\) or via the URL \(`sap-ui-debug=true`\).

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_ComponentPreload"/>

### Ensure that Application Resources are Loaded with a Component Preload

Application modules \(e.g. components, controllers, views or resource bundles\) should be loaded asynchronously via the component preload file. Please check \(e.g. via the *Network* tab in the Google Chrome developer tools\) if a component preload \(`component-preload.js`\) is missing. If the application is not configured to load modules asynchronously, any required application files may be loaded synchronously.

If you are using reuse-components, the related files could be bundled inside a library preload. If this library preload is configured to be loaded lazily \(`"lazy": true`\) in the dependencies of `manifest.json`, the library is not available on creation of the related component. In this case, it is required to use `sap.ui.getCore().loadLibrary("my.library")` before creating the component with `Component.create({ name: "my.component" })`. An indicator that a component is inside a library is the attribute `embeddedBy` in its `manifest.json` file.

> Note:
> If the component preload does not exist, the bundle needs to be created, for example by using the [UI5 Build Tooling](https://github.com/SAP/ui5-tooling).
> 
> 

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_RoutingConfigured"/>

### Ensure the Routing is Configured to load Targets Asynchronously

Please check the [Routing Configuration](Routing_Configuration_9023130.md) of the application's `manifest.json` for an `async=true` setting to configure the targets for asynchronous loading.

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_NetworkRequests"/>

### Check Network Requests

To quickly check the network load caused by your app, look at your browser's developer tools, for example the *Network* tab in the Google Chrome developer tools \(*F12*\). You'll see an overview of all requests being sent. Possible issues here may be:

***

#### Synchronous requests that block each other

In this case, use the `data-sap-ui-async="true"` setting in the bootstrap.

***

#### Too many requests

For OpenUI5 apps that use grunt as a web server, you can use the `openui5_preload` task to bundle and minimize all relevant component files by creating a component-preload file. For more information, see [Optimizing OpenUI5/SAPUI5 Apps](http://scn.sap.com/community/developer-center/front-end/blog/2015/02/18/optimizing-openui5-apps) in the SAPUI5 Developer Center on SAP SCN.

If you're using SAP Web IDE, refer to [Application Build](https://help.hana.ondemand.com/webide/frameset.htm?dfb26ef028624cf486a8bbb0bfd459ff.html) in the SAP Web IDE documentation.

***

#### Back-end related performance issues

-   Slow database service \(e.g. OData\)

-   Slow web server or CDN issues \(e.g. serving of static resources\)
-   Slow network infrastructure \(e.g. mobile network\)
-   The h2 protocol is not supported \(only HTTP/1.1\); ideally, the h2 protocol should be supported by the web server

> Note:
> To ensure the correct bandwidth when using UI5-based applications, you can find further information in [2240690](https://launchpad.support.sap.com/#/notes/2240690).
> 
> 

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_MigrateJquery"/>

### Migrate `jquery.sap.*` Modules to their Modularised Variants

Since UI5 version 1.58, the global `jquery.sap.*` modules are deprecated. Please use the modularised variant of the module. If you are still using the `jquery.sap.*` variants, a so-called "stubbing layer" loads the old modules synchronously!

You can find a list of all relevant modules in [Legacy jQuery.sap Replacement](Legacy_jQuery.sap_Replacement_a075ed8.md).

The usages can either be replaced manually or by the the [UI5 Migration Tool](https://github.com/SAP/ui5-migration)

> Note:
> Please declare the required modules in `sap.ui.define` or `sap.ui.require` to ensure that they load asynchronously.
> 
> 

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_MigrateFactories"/>

### Migrate Synchronous Variants of UI5 Factories to Asynchronous Variants

Check if the application is using synchronous UI5 factories and use the asynchronous variants, which are available for components, resource bundles, controllers, views and fragments.

Please visit the overview [Legacy Factories Replacement](Legacy_Factories_Replacement_491bd9c.md)

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_ModelPreload"/>

### Use the OData V2 Model Preload

Components can preload models for which modules are already loaded; otherwise a warning will be shown. The ODataModel V2 benefits especially, because the metadata can be loaded in parallel during a component load.

``` json
"sap.ui5": {
  ...
  "models": {
      "mymodel": {
          "preload": true,
...
```

For more information, see [Manifest Model Preload](Manifest_Model_Preload_26ba6a5.md)

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_MetadataCaching"/>

### Use OData V2 Metadata Caching

To ensure fast loading times for **SAP Fiori applications started from the SAP Fiori launchpad**, the OData metadata is cached on the web browser using cache tokens. The tokens are added with the parameter `sap-context-token` to the URL of metadata requests. Please check in developer tools of your browser \(e.g. the *Network* tab in the Google Chrome developer tools\) if the token is appended to the request URL.

> Note:
> This feature is only supported by OData V2 for SAP Fiori applications.
> 
> 

For more information, please check:

-   [Cache Buster for OData Metadata of SAP Fiori Apps](https://help.sap.com/viewer/a7b390faab1140c087b8926571e942b7/7.52.0/en-US/876e43a272cc45cb82dea640edff0ab2.html)

-   [Scheduling Update of OData Metadata Caching](https://help.sap.com/viewer/a7b390faab1140c087b8926571e942b7/7.52.0/en-US/2439967f0c284f6caf05e4323dd9292e.html)


***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_ListsTables"/>

### Check Lists and Tables

The performance limits of your browser are reached differently depending on the used browser, operating system and hardware. Therefore, it is important to be mindful about the amount of controls and data bindings. This applies especially to lists \(e.g. `sap.m.Table` or `sap.ui.table.Table`\):

-   If a table has more than 100 rows, please use `sap.ui.table.Table` instead of `sap.m.Table` The reason for this is that `sap.m.Table` keeps every loaded row in memory, even if not visible after scrolling. Please also see [Tables: Which One Should I Choose?](Tables_Which_One_Should_I_Choose_148892f.md) to choose the right table for your requirements.
-   If the table rows contain multiple controls and/or custom-data fields, please check if they are required, or if another control can replace them. For example, another list like a ComboBox inside of a table cell may create many controls for every row, which can be very expensive.
-   Check a table for hidden columns and load only the visible ones, if possible.

For further information, please check [Performance of Lists and Tables](Performance_of_Lists_and_Tables_f6a1a0a.md)

***

<a name="loio408b40efed3c416681e1bd8cdd8910d4__section_OptimizeCode"/>

### Further Code Optimization

You can further optimize your code by doing the following:

-   Use asynchronous view loading as described here: [Instantiating Views](Instantiating_Views_68d0e58.md)

-   If you use data binding with an OData service as a back-end, you might also want to consider switching your OData model to our more updated V2 OData model. For more information, see [OData V2 Model](OData_V2_Model_.md#loio6c47b2b39db9404582994070ec3d57a2)

-   Optimize dependent binding as described here: [Optimizing Dependent Bindings](OData_V2_Model_.md#loio62149734b5c24507868e722fe87a75db).

-   Avoid the usage of `setTimeout()` calls with values greater than `0`. This usually indicates an anti-pattern in application code that is used as a workaround and should be avoided. For more information, see also [JavaScript Code Issues: Don't use timeouts](JavaScript_Code_Issues_030fcd1.md#loio030fcd14963048218488048f407f8f34__11).

-   Don't use visibility for lazy instantiation. For more information, see [Performance Issues: Don't use visibility for lazy instantiation](Performance_Issues_966d67c.md#loio966d67c8cc5046419d1b35556cd9e447__1).

-   Please ensure the application does not block the rendering while waiting for back-end requests to respond. Waiting for data before rendering anything is not the favoured user experience. If possible, it is recommended to load data asynchronously and already render the page while the request is pending. Mostly, the requests won't fail, and if they do, it is better to show an error or to navigate to an error page.
-   If a `XML Preprocessor` is used, we recommend to use the [XML View Cache](XML_View_Cache_3d85d5e.md). If configured in the XML View and a properly implemented key provider \(for invalidation\), it is able to cache already processed XML View Preprocessor results.

**Related information**  


[Coding Issues to Avoid: Performance Issues](Performance_Issues_966d67c.md)

[Performance Measurement Using sap/ui/performance/Measurement Module](Performance_Measurement_Using_sapuiperformanceMeasurement_Module_78880c0.md)

[Blog: SAPUI5 Application Startup Performance – Best Practices](https://blogs.sap.com/2016/10/29/sapui5-application-startup-performance-best-practices/)

[Blog: SAPUI5 Application Startup Performance – Advanced Topics](https://blogs.sap.com/2016/11/19/sapui5-application-startup-performance-advanced-topics/)

