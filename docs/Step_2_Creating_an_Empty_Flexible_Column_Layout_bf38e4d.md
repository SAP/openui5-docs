<!-- loiobf38e4de70084477b9e104bf6f6d7737 -->

| loio |
| -----|
| bf38e4de70084477b9e104bf6f6d7737 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/bf38e4de70084477b9e104bf6f6d7737) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/bf38e4de70084477b9e104bf6f6d7737)</div>

## Step 2: Creating an Empty Flexible Column Layout

In this step, we add an instance of the `sap.f.FlexibleColumnLayout` in the main view of the app.

***

<a name="loiobf38e4de70084477b9e104bf6f6d7737__section_ed2_4dd_lbb"/>

### Preview

   
  
An empty instance of the `sap.f.FlexibleColumnLayout` control<a name="loiobf38e4de70084477b9e104bf6f6d7737__fig_r1j_pst_mr"/>

 ![](loio533d16592a7046e195278bf367507756_HiRes.png "An empty instance of the sap.f.FlexibleColumnLayout
					control") 

***

<a name="loiobf38e4de70084477b9e104bf6f6d7737__section_fd2_4dd_lbb"/>

### Coding

You can view and download all files at [SAP Fiori 2.0 App - Step 2](https://openui5.hana.ondemand.com/#/sample/sap.f.tutorial.fiori2.02/preview).

``` json
{
	"_version": "1.12.0",
	"sap.app": {
		"id": "sap.ui.demo.fiori2",
		"type": "application",
		"applicationVersion": {
			"version": "1.0.0"
		}
	},
	"sap.ui5": {
*HIGHLIGHT START*		"rootView": {
			"viewName": "sap.ui.demo.fiori2.view.App",
			"type": "XML",
			"async": true,
			"id": "fcl"
		},*HIGHLIGHT END*
		"dependencies": {
			"minUI5Version": "1.60.0",
			"libs": {
				"sap.ui.core": {}*HIGHLIGHT START*,
				"sap.f": {}*HIGHLIGHT END*
			}
		},
		"config": {
			"fullWidth": true
		}
	}
}
```

First, we add the `sap.f` library as a dependency in the `manifest.json` file as most of the SAP Fiori 2.0 controls are in this library.

``` xml
*HIGHLIGHT START*<mvc:View
	displayBlock="true"
	height="100%"
	xmlns="sap.f"
	xmlns:mvc="sap.ui.core.mvc">
		<FlexibleColumnLayout id="flexibleColumnLayout" backgroundDesign="Solid"></FlexibleColumnLayout>
</mvc:View>*HIGHLIGHT END*
```

We create a new **`App.view.xml`** that contains an instance of the `sap.f.FlexibleColumnLayout` control. Keep in mind that there is no content yet and the app appears as an empty page.

``` json
{
	"_version": "1.12.0",
	"sap.app": {
		"id": "sap.ui.demo.fiori2",
		"type": "application",
		"applicationVersion": {
			"version": "1.0.0"
		}
	},
	"sap.ui5": {
*HIGHLIGHT START*		"rootView": {
			"viewName": "sap.ui.demo.fiori2.view.App",
			"type": "XML",
			"async": false,
			"id": "fcl"
		},*HIGHLIGHT END*
		"dependencies": {
			"minUI5Version": "1.60.0",
			"libs": {
				"sap.ui.core": {},
				"sap.f": {}
			}
		},
		"config": {
			"fullWidth": true
		}
	}
}
```

We set the `rootView` to point to the created `App.view.xml`.

