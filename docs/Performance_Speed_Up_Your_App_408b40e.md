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

### Configuration

Issues with configuration are often caused by an old bootstrap or wrong usage of the activated features. Here's an example of what a bootstrap should look like for an up-to-date OpenUI5 app:

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

***

#### Use asynchronous loading

The most important setting is `data-sap-ui-async="true"`. This enables the runtime to load all the modules and preload files for all declared libraries asynchronously, if an asynchronous API is used. Setting `async=true` leverages the browser's capabilities to execute multiple requests in parallel, without blocking the UI thread.

> Note:
> The `data-sap-ui-async="true"` configuration option requires extensive testing as well as cooperation on application side to ensure a stable and fully working application. It is, therefore, **not** activated automatically, but needs to be configured accordingly. If you encounter issues, or want to prepare your application for asynchronous loading, see [Is Your Application Ready for Asynchronous Loading?](Is_Your_Application_Ready_for_Asynchronous_Loading_493a15a.md).
> 
> 

`index.html` file:

``` html
...
<script
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

#### Use the `manifest.json` descriptor file instead of the bootstrap to define dependencies

Don't specify a link to the CSS in the bootstrap of your app, use the `manifest.json` descriptor file instead.

We recommend using the `manifest.json` application descriptor file to declare dependencies, because this way you can benefit from the preload features of the component factory, which shortens the loading times.

Make sure that you don't load too many dependencies. In most apps, it's enough to load the `sap.ui.core` and the `sap.m` library by default and add additional libraries only when needed.

If you want to make additional libraries generally known in your app, without directly loading them during the app start, you can add them to the dependency declaration in the `manifest.json` file with the `lazy` loading option, which makes sure that the libraries are only loaded when they are needed:

``` json
"sap.ui5": {
	"rootView": {
		"viewName": "app.view.Main",
		"type": "XML"
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

#### Load OpenUI5 from the content delivery network \(CDN\)

Especially if you're running your app in the cloud, you benefit from the global distribution of servers.

For more information, see [Variant for Bootstrapping from Content Delivery Network](Variant_for____________Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md).

***

#### Make sure that all resources are available to avoid 404 errors

For example, make sure that you provide i18n files for all languages in which your app is used.

***

#### Use "manifest first" to load the component

Load the `manifest.json` descriptor file of the component first to analyze and preload the dependencies when loading the component. For more information, see [Manifest First Function](Descriptor_for_Applications,_Components,_and_Libraries_be0cf40.md#loiobe0cf40f61184b358b5faedaec98b2da__manifirst).

***

### Network

To quickly check the network load caused by your app, look at your browser's developer tools, for example the *Network* tab in the Google Chrome developer tools \(*F12*\). You'll see an overview of all requests being sent. Possible issues here may be:

-   Synchronous requests that block each other

    In this case, use the `data-sap-ui-async="true"` setting in the bootstrap.

-   Too many requests

    For OpenUI5 apps that use grunt as a web server, you can use the `openui5_preload` task to bundle and minimize all relevant component files by creating a component-preload file. For more information, see [Optimizing OpenUI5/SAPUI5 Apps](http://scn.sap.com/community/developer-center/front-end/blog/2015/02/18/optimizing-openui5-apps) in the SAPUI5 Developer Center on SAP SCN.

    If you're using SAP Web IDE, refer to [Application Build](https://help.hana.ondemand.com/webide/frameset.htm?dfb26ef028624cf486a8bbb0bfd459ff.html) in the SAP Web IDE documentation.


***

### Code

You can also optimize your coding by doing the following:

-   Use asynchronous view loading as described here: [Instantiating Views](Instantiating_Views_68d0e58.md)

-   If you use data binding with an OData service as a back end, you might also want to consider switching your OData model to our more updated V2 OData model. For more information, see [OData V2 Model](OData_V2_Model_.md#loio6c47b2b39db9404582994070ec3d57a2)

-   Optimize dependent binding as described here: [Optimizing Dependent Bindings](OData_V2_Model_.md#loio62149734b5c24507868e722fe87a75db).

-   Use the model preload feature: Components can preload models for which modules are already loaded otherwise a warning will be shown. The ODataModel V2 benefits especially because the metadata can be loaded in parallel during component load. For more information, see [Manifest Model Preload](Manifest_Model_Preload_26ba6a5.md).

-   Make use of asynchronous module loading \(AMD style\) for custom controls or other scripts. Although it is only supported by the preload, it will help you in future to enable asynchronous loading of individual modules combined with the usage of HTTP/2 or AMD-based packagers. It also ensures proper dependency tracking between modules.

    But it isn't enough to write AMD modules. You also need to prevent access to OpenUI5 classes via global names. Do not use `new sap.m.Button()`, but require the `Button` and call the constructor via the local AMD reference. For more information, see the [API Reference for `sap.ui.define`](https://openui5.hana.ondemand.com/#/api/sap.ui/methods/sap.ui.define) in the Demo Kit.

-   Avoid the usage of `setTimeout()` calls with values greater than `0`. This usually indicates an anti-pattern in application code that is used as a workaround and should be avoided. For more information, see also [JavaScript Code Issues: Don't use timeouts](JavaScript_Code_Issues_030fcd1.md#loio030fcd14963048218488048f407f8f34__11).

-   Don't use visibility for lazy instantiation. For more information, see [Performance Issues: Don't use visibility for lazy instantiation](Performance_Issues_966d67c.md#loio966d67c8cc5046419d1b35556cd9e447__1).


**Related information**  


[Coding Issues to Avoid: Performance Issues](Performance_Issues_966d67c.md)

[Performance Measurement Using sap/ui/performance/Measurement Module](Performance_Measurement_Using_sapuiperformanceMeasurement_Module_78880c0.md)

[Blog: SAPUI5 Application Startup Performance – Best Practices](https://blogs.sap.com/2016/10/29/sapui5-application-startup-performance-best-practices/)

[Blog: SAPUI5 Application Startup Performance – Advanced Topics](https://blogs.sap.com/2016/11/19/sapui5-application-startup-performance-advanced-topics/)

