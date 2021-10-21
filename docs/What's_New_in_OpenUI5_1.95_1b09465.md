<!-- loio1b094659cfcf422c968ce17d39f89211 -->

| loio |
| -----|
| 1b094659cfcf422c968ce17d39f89211 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/1b094659cfcf422c968ce17d39f89211) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/1b094659cfcf422c968ce17d39f89211)</div>

## What's New in OpenUI5 1.95

With this release OpenUI5 is upgraded from version 1.94 to 1.95.

***

<a name="loio1b094659cfcf422c968ce17d39f89211__section_yvs_ksr_2qb"/>

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

**Reminder: Outdated Versions to Be Removed from the CDN**

For security reasons, versions that are no longer maintained will be removed from the UI5 content delivery network \(CDN\) one year after their end of maintenance. If a version is still in maintenance, patches of that version that are older than one year will also be removed. We have noted that a number of customers are still using such outdated versions or patches. If this affects you, please note that once these versions or patches are removed, your applications will break. Please update to a more recent version or patch. For more information, see: [Removing Outdated UI5 Versions from UI5 CDN](https://blogs.sap.com/2021/01/26/removing-outdated-ui5-versions-from-ui5-cdn/).



</td>
<td valign="top">

n/a



</td>
</tr>
</table>

***

<a name="loio1b094659cfcf422c968ce17d39f89211__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**OpenUI5 OData V2 Model**

The new version of the OpenUI5 OData V2 model introduces the following features:

-   The optional `bDeleteCreatedEntities` parameter has been added to the `sap.ui.model.odata.v2.ODataModel#resetChanges` method. If set to `true`, any created entities are removed.

-   The `sap.ui.model.odata.v2.ODataModel#deleteCreatedEntry` method has been deprecated. It does not update controls but cannot be changed for compatibility reasons. Applications should use `sap.ui.model.odata.v2.ODataModel#resetChanges` instead.




</td>
</tr>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   A new `sap.ui.model.odata.v4.ODataContextBinding#moveEntityTo` method. You can use this API in a list-detail scenario to load details first, as described in [Relative Bindings](Data_Reuse_648e360.md). Note that this method is still a work in progress and should not be used for productive applications yet.

-   An absolute property binding with a path that ends in `$count` now supports the `$apply`, `$filter`, and `$search` OData system query options.

-   You can now provide handlers that provide the security token header. Note that expiration is currently only supported for the `X-CSRF-Token` header. For more information, see [Security Token Handling](Model_Instantiation_and_Data_Access_9613f1f.md#loio9613f1f2d88747cab21896f7216afdac__section_STH).




</td>
</tr>
</table>

***

<a name="loio1b094659cfcf422c968ce17d39f89211__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.m.Button`**

We have improved the accessibility of the control, and the screen readers now announce when there is a change in the text, tooltip, or icon in a stand-alone `sap.m.Button`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Button).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.DatePicker`, `sap.m.DateRangeSelection`, `sap.m.DateTimePicker`, and `sap.ui.unified.Calendar`**

These controls now have the new property `showCurrentDateButton`, which displays an additional button in the navigation part of the calendar. When pressed, the control navigates to the current date and focuses on it. This feature is available for pickers whose display format allows picking a day. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.DatePicker) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.DatePicker/sample/sap.m.sample.DatePicker).



</td>
</tr>
<tr>
<td valign="top">

`**sap.m.StandardListItem**`

Information texts in lists can now also be wrapped if wrapping is enabled for this control. However, a *More* option for these texts is not available. For more information, see the [API Reference for `wrapping`](https://openui5.hana.ondemand.com/#/api/sap.m.StandardListItem%23methods/getWrapping), the [API Reference for `info`](https://openui5.hana.ondemand.com/#/api/sap.m.StandardListItem%23methods/getInfo), and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.StandardListItem/sample/sap.m.sample.StandardListItemWrapping).



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   We have introduced \(in experimental state\) support for data caching. This feature enables host-environment developers to implement client-side data caching. Additionally, card developers have options to control what data is cached and how it should be cached. For more information, see the [Data Handling - Cache](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/data), [Integrate - Caching](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/data) sections, and the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/cache) in the Card Explorer.

-   The side indicators in the numeric header of the card now support semantic colors. This functionality is achieved using the new `state` property of the `SideIndicator`. For more information, see the [Analytical Card Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/analytical) in the Card Explorer.

-   We have added a new `refreshData` method. You can use it to refresh only that part of the card that shows new data, without rerendering the whole card. For more information, see the [Refresh Data Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/extension/refreshData) in the Card Explorer.

-   The Analytical type card can now visualize \(in experimental state\) all charts from the `sap.viz` library. To enable it, we have enhanced the card manifest with new properties - `feeds`, which allows developers to define more measures and dimensions, and `chartProperties` to customize the charts. The properties `legend`, `plotArea`, `title`, `dimensionAxis`, and `measureAxis` are now deprecated. For more information, see the [Analytical Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/analytical) section and the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/analytical/bubble) in the Card Explorer.




</td>
</tr>
</table>

***

<a name="loio1b094659cfcf422c968ce17d39f89211__section_cps_cg5_zcb"/>

### Deprecations


<table>
<tr>
<td valign="top">

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://openui5.hana.ondemand.com/#/api/deprecated). 



</td>
</tr>
</table>

