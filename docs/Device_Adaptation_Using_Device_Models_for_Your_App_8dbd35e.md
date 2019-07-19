<!-- loio8dbd35e1577b445d8077b2bc6ad8b958 -->

| loio |
| -----|
| 8dbd35e1577b445d8077b2bc6ad8b958 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/8dbd35e1577b445d8077b2bc6ad8b958) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/8dbd35e1577b445d8077b2bc6ad8b958)</div>

## Device Adaptation: Using Device Models for Your App

Depending on the capabilities of the device on which the app is running, the functionality and the design of the application might differ. By introducing a local JSON model holding the device-dependent data, we can bind properties of our views to the device's capabilities.

As an example, on big screens \(if the device is detected as a desktop device\), it is not necessary to show the *Back* button on a detail view in a master-detail scenario, because the master and detail view are shown at the same time. You can control the visibility of the *Back* button with a property from the device model.

You need to make the `sap.ui.Device` API available in a JSON model once in your component to allow controls to be adapted to the current platform using data binding. The code below shows an example of how to achieve this:

`Component.js`

``` js

sap.ui.define([
	"sap/ui/core/UIComponent",
	"sap/ui/model/json/JSONModel",
*HIGHLIGHT START*	"sap/ui/Device"*HIGHLIGHT END*
], function (UIComponent, JSONModel, *HIGHLIGHT START*Device*HIGHLIGHT END*) {

[…]

init: function () {
// set the device model
*HIGHLIGHT START*	var oDeviceModel = new JSONModel(Device);
	oDeviceModel.setDefaultBindingMode("OneWay");
	this.setModel(oDeviceModel, "device");
*HIGHLIGHT END*
[…]
}
```

This instantiates a named JSONModel \(`"device"`\) which contains all of the properties of the `sap.ui.Device` class, like browser, device type, or the current orientation of the screen. You can then bind the model properties in your views as follows:

`Master.view.xml`

``` xml

<Page showNavButton="{device>/system/phone}" />
...
<PullToRefresh visible="{device>/support/touch}" />
```

If you want to negate a value of the device model or make a simple case decision, you can use the expression binding syntax as shown below:

`Master.view.xml`

``` xml

<SearchField showRefreshButton="{= !${device>/support/touch} }" />
```

For more information, see [sap.ui.Device](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.Device.html) in the *API Reference* in the Demo Kit, and the documentation under [The Device API](The_Device_API_69a8e46.md).

