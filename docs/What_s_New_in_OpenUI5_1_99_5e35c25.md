<!-- loio5e35c2512e014e3b9831afd1cd041ed4 -->

| loio |
| -----|
| 5e35c2512e014e3b9831afd1cd041ed4 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/5e35c2512e014e3b9831afd1cd041ed4) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/5e35c2512e014e3b9831afd1cd041ed4)</div>

## What's New in OpenUI5 1.99

With this release OpenUI5 is upgraded from version 1.98 to 1.99.

***

<a name="loio5e35c2512e014e3b9831afd1cd041ed4__section_vvy_452_rrb"/>

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

For security reasons, versions that are no longer maintained will be removed from the UI5 content delivery network \(CDN\) one year after their end of maintenance. If a version is still in maintenance, patches of that version that are older than one year will also be removed. We have noted that a number of customers are still using such outdated versions or patches. If this affects you, please note that once these versions or patches are removed, your applications will break. Please update to a more recent version or patch. For more information, see: [Removing Outdated UI5 Versions from UI5 CDN](https://blogs.sap.com/2021/01/26/removing-outdated-ui5-versions-from-ui5-cdn/) as well as the UI5 notifications in the Demo Kit.



</td>
<td valign="top">

n/a



</td>
</tr>
</table>

***

<a name="loio5e35c2512e014e3b9831afd1cd041ed4__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   You can now use the `filter`, `sort`, `changeParameters`, and `suspend` methods on a list binding with transient contexts if the list binding is either a [root binding](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding%23methods/getRootBinding) or its `$$ownRequest` binding parameter is set to `true`.

-   We removed the experimental `sap.ui.model.odata.v4.ODataContextBinding#moveEntityTo` method.

-   The new [`sap.ui.model.odata.v4.ODataModel#getKeepAliveContext`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel%23methods/getKeepAliveContext) method searches for a matching context in list bindings with the new [`$$getKeepAliveContext`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel%23methods/bindList) binding parameter. The found context is [set to keep-alive](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context%23methods/setKeepAlive) and returned. For more information, see [Relative Bindings](Data_Reuse_648e360.md#loio648e360fa22d46248ca783dc6eb44531__section_relativeBindings).

-   In a list binding, you can now create new records at the beginning of the list, but below previously created new records. For this, you have to set the `bAtEnd` parameter to `false` in the first call of [`sap.ui.model.odata.v4.ODataListBinding#create`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding%23methods/create), and to `true` in all subsequent calls.

-   We enabled the [creation](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding%23methods/create) of inactive rows, introduced with OpenUI5 1.97 for `Auto` update groups, also for `API` groups. For more information on batch groups, see [Batch Control](Batch_Control_74142a3.md).




</td>
</tr>
</table>

***

<a name="loio5e35c2512e014e3b9831afd1cd041ed4__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.m.Carousel`**

The control now shows `sap.m.illustratedMessage` in use cases where there’s nothing to display. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Carousel) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Carousel/sample/sap.m.sample.CarouselEmptyMessages).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.DynamicDateRange` \(Experimental\)**

We have added new standard options to the control:

-   `Date and Time`: Used to select a single Date/Time value with a `DateTimePicker`.

-   `From / To (Date and Time)`, `From (Date and Time)` `То (Date and Time)`. These options are similar to the existing `From / To`, `From`, and `To`, but the new ones include time selection. When the new options are not used together with their date-only alternatives, their names are simplified, respectively to `From / To`, `From`, and `To`.

-   `Month in Year`: When this option is selected, a `Calendar` control appears, and the user can pick a month and a year.


For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.TimePicker) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.TimePicker/sample/sap.m.sample.TimePicker).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.SinglePlanningCalendar`**

We have introduced new behavior – an option to zoom in and zoom out to make the calendar appointments easier to read. You can do this by using the new `scaleFactor` property that changes the height of the calendar rows. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SinglePlanningCalendar) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.SinglePlanningCalendar).



</td>
</tr>
<tr>
<td valign="top">

<code><b>sap.m.upload.UploadSet</b></code>

You can now drag the `UploadSetItems` within `UploadSet` to rearrange the items.

The `itemDragStart` and `itemDrop` events are also being exposed. These events return the item as a parameter to the event handler. The events are triggered when you drag and drop items that have already been uploaded.



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   List, Table, and Timeline cards now \(experimentally\) support pagination. For more information, see the [Pagination](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/pagination) section and the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/pagination/client) in the Card Explorer.

-   We have \(experimentally\) enabled the List, Table, Analytical, and Timeline cards to display illustrated messages when there is no data for the card’s content. In addition, you can use the card manifest to further configure specific illustrated messages and texts for chosen no-data scenarios. For more information, see the [Custom Error Message](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/configuration/customErrorMessages) section and the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/customErrorMessages) in the Card Explorer.

-   The Adaptive card now supports schema 1.3 of MS Adaptive Cards. This comes with several new features: `label` support for input elements inside cards; support for required fields via the `isRequired` property of the input elements; support for `errorMessage`; support for the `style` property for actions. For more information, see the [Adaptive Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/adaptive) Learn section and the [Styled Actions Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/adaptive/styled-actions) in the Card Explorer.

-   The Calendar card supports placeholder loading - a type of busy indicator that provides the user with a rough outline of the content while it is loading.




</td>
</tr>
</table>

***

<a name="loio5e35c2512e014e3b9831afd1cd041ed4__section_cps_cg5_zcb"/>

### Deprecations


<table>
<tr>
<td valign="top">

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://openui5.hana.ondemand.com/#/api/deprecated). 



</td>
</tr>
</table>

