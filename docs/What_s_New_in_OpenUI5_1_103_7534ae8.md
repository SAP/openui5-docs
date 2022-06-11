<!-- loio7534ae89605d45ae989fea85b70f24d8 -->

| loio |
| -----|
| 7534ae89605d45ae989fea85b70f24d8 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/7534ae89605d45ae989fea85b70f24d8) | [demo kit latest release](https://sdk.openui5.org/topic/7534ae89605d45ae989fea85b70f24d8)</div>

## What's New in OpenUI5 1.103

With this release OpenUI5 is upgraded from version 1.102 to 1.103.

***

<a name="loio7534ae89605d45ae989fea85b70f24d8__section_fwt_nbw_5tb"/>

### Preview and Announcements

The following information concerns important upcoming changes. UI changes may have an impact on the user experience and may require test cases to be adapted.


<table>
<tr>
<th valign="top">

Type



</th>
<th valign="top">

Description



</th>
<th valign="top">

Available as of OpenUI5 Version



</th>
</tr>
<tr>
<td valign="top">

Announcement



</td>
<td valign="top">

**Reminder: Outdated OpenUI5 Versions to Be Removed from the CDN**

For security reasons, OpenUI5 versions that are no longer maintained will be removed from the UI5 content delivery network \(CDN\) one year after their end of maintenance. If a version is still in maintenance, patches of that version that are older than one year will also be removed. We have noted that a number of customers are still using such outdated versions or patches. If this affects you, please note that once these versions or patches are removed, your applications will break. Please update to a more recent version or patch. For more information, see: [Removing Outdated UI5 Versions from UI5 CDN](https://blogs.sap.com/2021/01/26/removing-outdated-ui5-versions-from-ui5-cdn/) as well as the UI5 notifications in the Demo Kit.



</td>
<td valign="top">

n/a



</td>
</tr>
</table>

***

<a name="loio7534ae89605d45ae989fea85b70f24d8__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   We now provide the new `sap.ui.model.odata.v4.ODataModel#delete` method.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel%23methods/delete).
-   Multiple requests for absolute property bindings of singleton properties are now merged. For more information, see [Absolute Property Bindings of Singletons](Data_Reuse_648e360.md#loio648e360fa22d46248ca783dc6eb44531__section_APBS).



</td>
</tr>
</table>

***

<a name="loio7534ae89605d45ae989fea85b70f24d8__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.m.DateRangeSelection`, `sap.m.OverflowToolbar`, and `sap.m.IOverflowToolbarContent`**

We have implemented `sap.m.OverflowToolbar` on the `sap.m.DateRangeSelection` to allow it to go to the overflow menu. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.OverflowToolbar).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.MessageBox`**

We have enhanced the `details` property and now it can also be a function that asynchronously fetches details from the backend. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.MessageBox/sample/sap.m.sample.MessageBoxInfo).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.plugins.DataStateIndicator`**

The `MessageStrip` control, which is offered by the `DataStateIndicator` plugin, provides various messages for users that tell them about the current state of the UI. The new `close` event of `DataStateIndicator` is fired when the *Close* button of the `MessageStrip` control is pressed. This allows applications to intervene, for example, and let users remove these messages from the UI. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.plugins.DataStateIndicator%23events/close) for `DataStateIndicator`, the [API Reference](https://sdk.openui5.org/api/sap.m.MessageStrip%23events/close) for `MessageStrip`, and the [Sample](https://sdk.openui5.org/entity/sap.ui.comp.smarttable.SmartTable/sample/sap.ui.comp.sample.smarttable.mtableDataState).



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   Colors in the `StackedBar` microcharts in List cards no longer accept `sap.m.ValueCSSColor` values. Now the colors should have standard semantic values provided by the `sap.m.ValueColor` enum. For more information, see the [Card Microcharts](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/microcharts) section in the Card Explorer.

-   We have allowed the usage of time series charts in the Analytical card. To enable this feature, we now pass the dimensions’ `dataType` parameter in the manifest. For more information, see the [Column with Time Axis](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/analytical/timeAxis) sample in the Card Explorer.

-   We have added documentation and a sample about intent-based navigation actions. Intent-based navigation is a mechanism, which has to be supported by the host environment, that allows you to launch applications or perform actions on semantic objects by using abstract intents. For more information, see the [Navigation](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/actions/navigation) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/cardActions/ibn) in the Card Explorer.




</td>
</tr>
</table>

***

<a name="loio7534ae89605d45ae989fea85b70f24d8__section_cps_cg5_zcb"/>

### Deprecations


<table>
<tr>
<td valign="top">

 For a complete list of all deprecations, see [Deprecated APIs](https://sdk.openui5.org/api/deprecated). 



</td>
</tr>
</table>

