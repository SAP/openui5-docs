<!-- loioc2f4684363c64d5fbaf65662c11dc6ea -->

| loio |
| -----|
| c2f4684363c64d5fbaf65662c11dc6ea |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/c2f4684363c64d5fbaf65662c11dc6ea) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/c2f4684363c64d5fbaf65662c11dc6ea)</div>

## Model Instantiation

The app configures several data models that are used throughout the app to update the views or to store additional configuration options.

The service model and the resource bundle are instantiated automatically by the app’s component during startup and described in the first section. The local view models and helper models such as the device model are set up as JSON models and described in the second section.

***

<a name="loioc2f4684363c64d5fbaf65662c11dc6ea__section_automatic_model_instantiation"/>

### Automatic Model Instantiation

The templates instantiate the service and resource model automatically using the following configuration entries in the descriptor. When the component of the app is initialized, these models will be made available under the configured name throughout the app.

An external service is defined in the `dataSources` section of the `sap.app` namespace. In the example shown below, we configure an OData V2 model and the alias `"mainService"` in the `manifest.json` descriptor file:

``` js

{
	…
	"sap.app": {
		…
		"i18n": "i18n/i18n.properties",
		…
		"dataSources": {
			"mainService": {
				"uri": "/here/goes/your/serviceUrl/"
				"type": "OData",
				"settings": {
					"odataVersion": "2.0",
					"localUri": "localService/metadata.xml"
				}
			}
		},
		…
	},
	…
}
```

> Note:
> If you use the OData V4 template, you set the `odataVersion` accordingly.
> 
> 

In the models section of the `sap.ui5` namespace we define two models that will be instantiated automatically. The resource model is a named model \( i18n \) and the OData model is the default model so it has no name. The OData model also receives additional URL parameters via the `metadataUrlParams`. The parameters `sap-server`, `sap-client`, and `sap-language` are passed to the service automatically by OpenUI5, as shown in the following `manifest.json` code snippet:

``` js

{
	…
	"sap.ui5": {
		…
		"models": {
			"i18n": {
				"type": "sap.ui.model.resource.ResourceModel",
				"settings": {
					"bundleName": "sap.ui.demo.masterdetail.i18n.i18n"
				}
			},
			"": {
				"dataSource": "mainService",
				"preload": true
			}
		},
		…
	}
}
```

> Note:
> Before OpenUI5 version 1.30, all models were defined and instantiated in the component's `init` method. We recommend removing all manual model creation code and switching to the automatic model instantiation instead. The "device model" however is still a local model that has to be instantiated manually.
> 
> 

***

### Additional Models for the App

The following models are created as local JSON models in the app and can be referenced by its model name where needed:

-   **device**

    The device model provides an easy access to the device API and is used to configure certain view settings according to the user’s device.

-   **FLP**

    The FLP model is a helper module to configure SAP Fiori launchpad \(FLP\) integration and is used to control the sharing options of the app.

-   **worklistView**

    A local view model for the worklist view that stored configuration options that are bound to controls in the view.

-   **objectView**

    A local view model for the object view that stored configuration options that are bound to controls in the view.


