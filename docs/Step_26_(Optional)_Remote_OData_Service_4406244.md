<!-- loio44062441f3bd4c67a4f665ae362d1109 -->

| loio |
| -----|
| 44062441f3bd4c67a4f665ae362d1109 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/44062441f3bd4c67a4f665ae362d1109) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/44062441f3bd4c67a4f665ae362d1109)</div>

## Step 26: \(Optional\) Remote OData Service

So far we have worked with local JSON data, but now we will access a real OData service to visualize remote data.

***

In the real world, data often resides on remote servers and is accessed via an OData service. We will add a data source configuration to the manifest and replace the JSONModel type for our `invoice` model with the publicly available Northwind OData service to visualize remote data. You will be surprised how little needs to be changed in order to make this work!

> Note:
> This step is optional. If you cannot get it to work, don't worry too much, the remaining steps will also work with the local JSON data you have used so far.
> 
> 

***

### Preview

   
  
Products from the OData invoices test service are now shown within our app<a name="loio44062441f3bd4c67a4f665ae362d1109__fig_r1j_pst_mr"/>

 ![](loio99a649180be34423b9c6ba8379b26098_HiRes.png "Products from the OData invoices test service are now shown within our
					app") 

***

### Coding

You can view and download all files at [Walkthrough - Step 26](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.26/preview).

``` js
{
  "_version": "1.12.0",
  "sap.app": {
	...
	"ach": "CA-UI5-DOC"*HIGHLIGHT START*,
	"dataSources": {
	  "invoiceRemote": {
		"uri": "https://services.odata.org/V2/Northwind/Northwind.svc/",
		"type": "OData",
		"settings": {
		  "odataVersion": "2.0"
		}
	  }
	}*HIGHLIGHT END*
  },
  "sap.ui": {
	...
  },
  "sap.ui5": {
	...
	"models": {
	  "i18n": {
		"type": "sap.ui.model.resource.ResourceModel",
		"settings": {
		  "bundleName": "sap.ui.demo.walkthrough.i18n.i18n"
		}
	  },
	  "invoice": {*HIGHLIGHT START*
		"dataSource": "invoiceRemote"
	  *HIGHLIGHT END*}
	}
  }
}
```

In the `sap.app` section of the descriptor file, we add a data source configuration. With the `invoiceRemote`, key we specify a configuration object that allows automatic model instantiation. We specify the type of the service \(`OData`\) and the model version \(`2.0`\). In this step, we want to use the publicly available Northwind OData service located at `https://services.odata.org/V2/Northwind/Northwind.svc/`. Therefore, the URI points to the official Northwind OData service.

In the `models` section, we replace the content of the `invoice` model. This key is still used as model name when the model is automatically instantiated during the component initialization. However, the `invoiceRemote` value of the `dataSource` key is a reference to the data source section that we specified above. This configuration allows the component to retrieve the technical information for this model during the start-up of the app.

Our component now automatically creates an instance of `sap.ui.model.odata.v2.ODataModel` according to the settings we specified above, and makes it available as a model named `invoice`. When you use the `invoiceRemote` data source, the `ODataModel` fetches the data from the real Northwind OData service. The invoices we receive from the Northwind OData service have identical properties as the JSON data we used previously \(except for the `status` property, which is not available in the Northwind OData service\).

> Note:
> If you want to have a default model on the component, you can change the name of the model to an empty string in the descriptor file. Automatically instantiated models can be retrieved by calling `this.getModel` in the component. In the controllers of component-based apps you can call `this.getView().getModel()` to get the automatically instantiated model. For retrieving a named model you have to pass on the model name defined in the descriptor file to `getModel`, that is, in the component you would call `this.getModel("invoice")` to get our automatically generated `invoice` model that we defined in the descriptor.
> 
> 

You can now try to run the app and see what happens - we will see an error related to our new configuration in the console:

   
  
Violations of the same-origin policy in Google Chrome<a name="loio44062441f3bd4c67a4f665ae362d1109__fig_jyf_f1k_c5"/>

 ![](loio2c36d72282e34903a97197783fe92122_HiRes.png "Violations of the same-origin policy in Google Chrome") 

Due to the so called same-origin policy, browsers deny AJAX requests to service endpoints in case the service endpoint has a different domain/subdomain, protocol, or port than the app. The browser refuses to connect to a remote URL directly for security reasons. Depending on your development enviroment you have different options to overcome this limitation:

-   [SAP Web IDE: Configure a destination](Request_Fails_Due_to_Same-Origin_Policy_(Cross-Origin_Resource_Sharing_-_CORS)_5bb388f.md#loio5bb388fc289d44dca886c8fa25da466e__UsingHelperService)
-   [Local Development: Configure a local proxy \(CORS anywhere\)](Request_Fails_Due_to_Same-Origin_Policy_(Cross-Origin_Resource_Sharing_-_CORS)_5bb388f.md#loio5bb388fc289d44dca886c8fa25da466e__CORSAnywhere)
-   [Workaround: Disabling the same-origin policy in the browser](Request_Fails_Due_to_Same-Origin_Policy_(Cross-Origin_Resource_Sharing_-_CORS)_5bb388f.md#loio5bb388fc289d44dca886c8fa25da466e__DisablingSameOriginPolicy) \(not recommended, only for testing\)

**Related information**  


[OData Home Page](http://www.odata.org/)

[API Reference: `sap.ui.model.odata.v2.ODataModel`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.v2.ODataModel.html)

[First-Aid Kit](First-Aid_Kit_dfe4f79.md)

[Request Fails Due to Same-Origin Policy \(Cross-Origin Resource Sharing - CORS\)](Request_Fails_Due_to_Same-Origin_Policy_(Cross-Origin_Resource_Sharing_-_CORS)_5bb388f.md)

