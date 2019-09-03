<!-- loioa04b0d10fb494d1cb722b9e341b584ba -->

| loio |
| -----|
| a04b0d10fb494d1cb722b9e341b584ba |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/a04b0d10fb494d1cb722b9e341b584ba) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/a04b0d10fb494d1cb722b9e341b584ba)</div>

## Bootstrapping: Loading and Initializing

To use OpenUI5 features in your HTML page, you have to load and initialize the SAPUI5 library.

You can use the OpenUI5 bootstrap script in your page to initialize OpenUI5 runtime automatically as soon as the script is loaded and executed by the browser. For simple use cases as well as the default OpenUI5 installation, this is sufficient to build and run UIs. In addition to this, you can specify the set of OpenUI5 libraries and the theme used for your application in the configuration settings.

> Note:
> If you run your app standalone, the bootstrap is added to your HTML page. In an SAP Fiori launchpad environment, the launchpad executes the bootstrap and no additional HTML page is needed to display the app.
> 
> 

The following code snippet shows a typical bootstrap script tag:

``` html
<script id="sap-ui-bootstrap" 
     type="text/javascript"
     src="resources/sap-ui-core.js"
     data-sap-ui-theme="sap_belize"
     data-sap-ui-libs="sap.m"
     data-sap-ui-compatVersion="edge">
</script>
```

The attributes `data-sap-ui-theme="sap_belize"` and `data-sap-ui-libs="sap.m"` already provide examples of how OpenUI5 runtime can be configured to the needs of an application.

***

### Overview of Bootstrap Files

OpenUI5 provides several bootstrap files for different use cases. The following table gives an overview of the most important resources and the respective use cases. The resource names refer to the `resources/` folder in the OpenUI5 installation. The actual base URL depends on your platform and administrative setup.

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Resource</th>
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>`sap-ui-core.js`</td>
			<td>This is the standard bootstrap file, which we recommend to use for typical use cases. It already contains jQuery, `jquery-ui-position` and only the minimum required parts of the core library \(`sap.ui.core`\). Required files are loaded dynamically using XMLHttpRequest \(XHR\). For more information, see [Standard Variant for Bootstrapping](Standard_Variant_for_Bootstrapping_91f1f45.md).</td>
		</tr>
		<tr>
			<td>Content Delivery Network \(CDN\)</td>
			<td>You can access the libraries externally from a CDN. For more information see [Variant for Bootstrapping from Content Delivery Network](Variant_for____________Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md).</td>
		</tr>
		<tr>
			<td>`sap-ui-core-nojQuery.js`</td>
			<td>You use this bootstrap file for applications with their own jQuery version. It also contains the minimum required parts of the core library, but **not** jQuery and `jquery-ui-position`. For more information, see [noJQuery Variant for Bootstrapping](noJQuery_Variant_for_Bootstrapping_91f1dd0.md).</td>
		</tr>
		<tr>
			<td>`sap/ui/core/library-preload.js`</td>
			<td>This file contains most of the modules that are contained in the `sap.ui.core` library, but the modules are parsed and executed only on demand, and not immediately.

 > Note:
 > An application must not reference this file. If the configuration option is set to `preload`, OpenUI5 automatically loads the file.

 For more information, see [Standard Variant for Bootstrapping](Standard_Variant_for_Bootstrapping_91f1f45.md).</td>
		</tr>
		<tr>
			<td>`sap-ui-core-lean.js`</td>
			<td>This bootstrap file is similar to the `sap-ui-core.js` file, but in this use case only the jQuery and one OpenUI5 file are loaded immediately and the other files are loaded dynamically.

 > Note:
 > This use case is usually **not** used and may be removed in future.
			</td>
		</tr>
		<tr>
			<td>`sap-ui-custom*.js`</td>
			<td>File names that match this pattern are reserved for custom merged files used by the application.

 > Note:
 > The proposed naming scheme for these files needs to be adapted in future versions for the same encapsulation reasons as mentioned above.
			</td>
		</tr>
	</tbody>
</table>

