<!-- loio676b636446c94eada183b1218a824717 -->

| loio |
| -----|
| 676b636446c94eada183b1218a824717 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/676b636446c94eada183b1218a824717) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/676b636446c94eada183b1218a824717)</div>

## Use Asynchronous Loading

Asynchronous loading is the way to go: It makes your applications a lot faster and, through that, better to use.

As OpenUI5 is evolving, the loading processes in the background were significantly improved. To get the best out of these changes in the core and to speed up your app, we recommend that you switch on asynchronous loading. With asynchronous loading, files are retrieved in parallel. This is much quicker than with synchronous loading, where files are retrieved sequentially. There are a few possibilities to do that:

***

<a name="loio676b636446c94eada183b1218a824717__section_ykw_py5_zfb"/>

### Use a Bootstrapping Tag in HTML Files

Add the bootstrapping tag `data-sap-ui-async="true"` to your `index.html` file. This loads the modules for all declared libraries asynchronously. If you have other HTML files in your app, you should to this there as well.

``` html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>My App</title>
	<script
		id="sap-ui-bootstrap"
		...
		data-sap-ui-async="true">
	</script>
...
```

-   Learn how: Walkthrough Tutorial [Step 2: Bootstrap](Step_2_Bootstrap_fe12df2.md)
-   Find out more: [Bootstrapping: Loading and Initializing](Bootstrapping_Loading_and_Initializing__a04b0d1.md)

***

### Add the `async` Property to the `manifest.json`

To also load all application-specific configuration settings asynchronously, set the `async` property in the metadata of the `manifest.json` file to `true`.

``` js
"sap.ui5": {
		"rootView": {
			"viewName": "sap.ui.demo.worklist.view.App",
			"type": "XML",
			"async": true,
			"id": "app"
		},
```

-   Learn how: Walkthrough Tutorial [Step 10: Descriptor for Applications](Step_10_Descriptor_for_Applications_8f93bf2.md)
-   Find out more: [Descriptor for Applications, Components, and Libraries](Descriptor_for_Applications,_Components,_and_Libraries_be0cf40.md)

