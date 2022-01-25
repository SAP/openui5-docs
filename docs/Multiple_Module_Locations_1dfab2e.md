<!-- loio1dfab2e19fc0479d9dfcefc28d3642f1 -->

| loio |
| -----|
| 1dfab2e19fc0479d9dfcefc28d3642f1 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/1dfab2e19fc0479d9dfcefc28d3642f1) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/1dfab2e19fc0479d9dfcefc28d3642f1)</div>

## Multiple Module Locations

OpenUI5 supports multiple module locations by means of the `sap.ui.loader.config` function.

In web applications, modules can be located in different locations, such as servers and web apps. A web application can, for example, be deployed as an individual web app and contain modules that have to be loaded at runtime. OpenUI5 and its modules, however, have to be loaded either from a content delivery network \(CDN\) or from a centrally deployed web app. By default, OpenUI5 loads modules from its resource root URL, that is, from the centrally deployed web application. This would fail for modules that are contained in your web application.

The `sap.ui.loader.config` function associates a module name prefix with a URL prefix. All modules are loaded from the registered URL instead of the standard resource root URL:

```
sap.ui.loader.config({
	paths: {
		'my/module': 'https://example.com/resources/my/module'
	}
});
```

Thus, it is possible to redirect the request for the application-specific modules to the corresponding web application:

``` html
			
	<script src="https://openui5.hana.ondemand.com/resources/sap-ui-core.js" ></script>

	<script>
		// redirect the 'my.webapp' package to the local web app
		sap.ui.loader.config({
			paths:{
				"my/webapp": "my-webapp/resources/my/webapp"
			}
		});
		
		sap.ui.require([
			'sap/ui/core/Core',	
			'my/webapp/MyModule01’	// loads /my-webapp/resources/my/webapp/MyModule01.js
		], function ( Core, MyModule01 ) {

			//[…] use modules
		}
	</script>
```

> ### Note:  
> The registered URL above contains the transformed module name prefix `my/webapp/`. This allows a more flexible packaging of the modules, for example, if you decide to deploy all modules named `my.company.*` to the central URL `http://my.company/shared/` without packaging them into a two level hierarchy of subfolders:
> 
> ```
> 
> sap.ui.loader.config({
>  	paths:{
>    		"my/company": "http://my.company/shared/"
>       }
> });
> ```
> 
> However, when the standard build tools of the OpenUI5 framework are used, the full package name will be part of the runtime file hierarchy and the registration must contain the transformed package hierarchy as above.

