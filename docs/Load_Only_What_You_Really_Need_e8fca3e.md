<!-- loioe8fca3e4c68a4f289660299d806ba99e -->

| loio |
| -----|
| e8fca3e4c68a4f289660299d806ba99e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/e8fca3e4c68a4f289660299d806ba99e) | [demo kit latest release](https://sdk.openui5.org/topic/e8fca3e4c68a4f289660299d806ba99e)</div>

## Load Only What You Really Need

The amount of resources and data that your app loads will directly affect the performance of your app. You should declare all dependencies and remove unused libraries and classes from your code.

***

<a name="loioe8fca3e4c68a4f289660299d806ba99e__section_dvs_cvy_yfb"/>

### Keep Your Library Dependencies Up To Date

Always define the libraries you use in the manifest and remove all libraries that you do not intend to use in your code. If you have no manifest, you have to specify the used libraries in the OpenUI5 bootstrap. If you specify the used libraries in either place, they are loaded optimized. This means that all used controls, styles, etc. are not requested separately. For every mentioned library, the library preload file, the library styles, and the text translations are loaded once during the application startup. No further requests are necessary while using the application, because all needed artefacts are already included in the respective library preload file.

```json
"sap.ui5": {
	"dependencies": {
		"minUI5Version": "1.60.0",
		"libs": {
			"sap.ui.core": {},
			"sap.m": {},
			"sap.ui.layout": {}
		}
	}
	...
}
```

-   Learn how: Walkthrough Tutorial [Step 10: Descriptor for Applications](Step_10_Descriptor_for_Applications_8f93bf2.md)
-   Find out more: [Descriptor for Applications, Components, and Libraries \(manifest.json\)](Descriptor_for_Applications_Components_and_Libraries_manifest_json_be0cf40.md)

***

<a name="loioe8fca3e4c68a4f289660299d806ba99e__section_pxb_zvy_yfb"/>

### Declare Local Dependencies

In the JavaScript files of your app, define all dependencies to OpenUI5 framework classes and app resources via `sap.ui.define`. If you have unused dependencies, you should remove them right away.

The UI5 Tooling can then create a "cleaned-up" version of your app that only contains the resources you really need. The so-called application preload will greatly speed up the initial load time of your app.

```json
sap.ui.define([
	"sap/ui/core/mvc/Controller",
	"sap/m/MessageToast",
	"sap/base/Log"
], function (Controller, MessageToast, Log) {
	...
```

-   Learn how: Walkthrough Tutorial [Step 10: Descriptor for Applications](Step_10_Descriptor_for_Applications_8f93bf2.md)
-   Find out more:
    -   [Modules and Dependencies](Modules_and_Dependencies_91f23a7.md)
    -   [https://help.sap.com/viewer/825270ffffe74d9f988a0f0066ad59f0/Cloud/en-US/dfb26ef028624cf486a8bbb0bfd459ff.html](https://help.sap.com/viewer/825270ffffe74d9f988a0f0066ad59f0/Cloud/en-US/dfb26ef028624cf486a8bbb0bfd459ff.html)
    -   [UI5 Tooling](https://sap.github.io/ui5-tooling/)


***

<a name="loioe8fca3e4c68a4f289660299d806ba99e__section_s3g_5yy_yfb"/>

### Use Lazy Loading

Use controls like `sap.m.List` or UI patterns that support displaying data selectively or with pagination. Make sure that your backend service is designed to deliver small chunks of data as well.

```
<List
	growing="true"
	growingThreshold="20"
	...>
```

-   Learn how: Testing Tutorial [Step 7: Changing the Table to a Growing Table](Step_7_Changing_the_Table_to_a_Growing_Table_016e0d4.md)

-   Find out more: [Growing Feature for Table and List](Growing_Feature_for_Table_and_List_9164ba7.md)


