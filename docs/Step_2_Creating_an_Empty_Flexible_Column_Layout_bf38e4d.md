<!-- loiobf38e4de70084477b9e104bf6f6d7737 -->

| loio |
| -----|
| bf38e4de70084477b9e104bf6f6d7737 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/bf38e4de70084477b9e104bf6f6d7737) | [demo kit latest release](https://sdk.openui5.org/topic/bf38e4de70084477b9e104bf6f6d7737)</div>

## Step 2: Creating an Empty Flexible Column Layout

In this step, we add an instance of the `sap.f.FlexibleColumnLayout` control in the main view of the app.

***

<a name="loiobf38e4de70084477b9e104bf6f6d7737__section_ed2_4dd_lbb"/>

### Preview

  
  
**An empty instance of the sap.f.FlexibleColumnLayout control**

![](images/loio533d16592a7046e195278bf367507756_HiRes.png "An empty instance of the sap.f.FlexibleColumnLayout control")

***

<a name="loiobf38e4de70084477b9e104bf6f6d7737__section_yzh_v3j_l4b"/>

### Coding

You can view and download all files at [Flexible Column Layout App - Step 2](https://sdk.openui5.org/sample/sap.f.tutorial.fcl.02/preview).

***

<a name="loiobf38e4de70084477b9e104bf6f6d7737__section_cyn_x3j_l4b"/>

### webapp/manifest.json \[MODIFY\]

```json
{
	"_version": "1.38.0",
	"sap.app": {
		"id": "sap.ui.demo.fcl",
		"type": "application",
		"applicationVersion": {
			"version": "1.0.0"
		}
	},
	"sap.ui5": {
		"rootView": {
			"viewName": "sap.ui.demo.fcl.view.App",
			"type": "XML",
			"async": true,
			"id": "fcl"
		},
		"dependencies": {
			"minUI5Version": "1.98.0",
			"libs": {
				"sap.f": {},
				"sap.ui.core": {}
				}
		}
	}
}
```

First, we add the `sap.f` library as a dependency in the `manifest.json` file.

***

<a name="loiobf38e4de70084477b9e104bf6f6d7737__section_w1v_z3j_l4b"/>

### webapp/view/App.view.xml \[NEW\]

```xml
<mvc:View
	displayBlock="true"
	height="100%"
	xmlns="sap.f"
	xmlns:mvc="sap.ui.core.mvc">
		<FlexibleColumnLayout id="flexibleColumnLayout" backgroundDesign="Solid"></FlexibleColumnLayout>
</mvc:View>
```

We create a new **`App.view.xml`** that contains an instance of the `sap.f.FlexibleColumnLayout` control. Keep in mind that there is no content yet and the app appears as an empty page.

***

<a name="loiobf38e4de70084477b9e104bf6f6d7737__section_fd2_4dd_lbb"/>

### webapp/manifest.json \[MODIFY\]

```json
{
	"_version": "1.38.0",
	"sap.app": {
		"id": "sap.ui.demo.fcl",
		"type": "application",
		"applicationVersion": {
			"version": "1.0.0"
		}
	},
	"sap.ui5": {
		"rootView": {
			"viewName": "sap.ui.demo.fcl.view.App",
			"type": "XML",
			"async": false,
			"id": "fcl"
		},
		"dependencies": {
			"minUI5Version": "1.98.0",
			"libs": {
				"sap.f": {},
				"sap.ui.core": {}
			}
		},
		"config": {
			"fullWidth": true
		}
	}
}
```

We set the `rootView` to point to the created `App.view.xml`.

**Parent topic:**[Flexible Column Layout App Tutorial](Flexible_Column_Layout_App_Tutorial_c4de2df.md "In this tutorial, we showcase how to structure your OpenUI5 app using the layout patterns that comply with the SAP Fiori design guidelines.")

**Next:**[Step 1: Setting Up the Initial App](Step_1_Setting_Up_the_Initial_App_59b772b.md "We start by setting up a basic OpenUI5 app for this tutorial.")

**Previous:**[Step 3: Using Dynamic Page for the List View](Step_3_Using_Dynamic_Page_for_the_List_View_0830bce.md "In this step, we create the list view of the app using sap.f.DynamicPage control.")

