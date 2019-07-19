<!-- loioe8fca3e4c68a4f289660299d806ba99e -->

| loio |
| -----|
| e8fca3e4c68a4f289660299d806ba99e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/e8fca3e4c68a4f289660299d806ba99e) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/e8fca3e4c68a4f289660299d806ba99e)</div>

## Load Only What You Really Need

The amount of resources and data that your app loads will directly affect the performance of your app. You should declare all dependencies and remove unused libraries and classes from your code.

***

<a name="loioe8fca3e4c68a4f289660299d806ba99e__section_dvs_cvy_yfb"/>

### Keep Your Library Dependencies Up To Date

A library preload file, the library styles and text translations are loaded for every library you define in the application descriptor or the OpenUI5 bootstrap. Always define libraries in the manifest and remove all libraries that you do not intend to use in your code.

``` json
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
-   Find out more: [Descriptor for Applications, Components, and Libraries](Descriptor_for_Applications,_Components,_and_Libraries_be0cf40.md)

***

<a name="loioe8fca3e4c68a4f289660299d806ba99e__section_pxb_zvy_yfb"/>

### Declare Local Dependencies

In the JavaScript files of your app, define all dependencies to OpenUI5 framework classes and app resources via `sap.ui.define`. If you have unused dependencies, you should remove them right away.

The UI5 Build and Development tooling can then create a "cleaned-up" version of your app that only contains the resources you really need. The so-called application preload will greatly speed up the initial load time of your app.

``` json
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
    -   [https://github.com/SAP/ui5-tooling](https://github.com/SAP/ui5-tooling)

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


