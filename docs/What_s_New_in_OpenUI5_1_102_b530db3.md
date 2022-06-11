<!-- loiob530db37f4db4164b5e68f20bff93a9a -->

| loio |
| -----|
| b530db37f4db4164b5e68f20bff93a9a |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/b530db37f4db4164b5e68f20bff93a9a) | [demo kit latest release](https://sdk.openui5.org/topic/b530db37f4db4164b5e68f20bff93a9a)</div>

## What's New in OpenUI5 1.102

With this release OpenUI5 is upgraded from version 1.101 to 1.102.

***

<a name="loiob530db37f4db4164b5e68f20bff93a9a__section_jhg_nsb_ntb"/>

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

<a name="loiob530db37f4db4164b5e68f20bff93a9a__section_yxw_pxt_zcb"/>

### New Features


<table>
<tr>
<td valign="top">

**Accessibility Guide**

The accessibility guide is a newly developed application about web accessibility in OpenUI5. As an addition to the existing accessibility documentation in the Demo Kit, the accessibility guide provides practical, code-oriented guidance and samples.

For more information, see [Accessibility Guide](https://sdk.openui5.org/test-resources/sap/m/demokit/accessibilityGuide/webapp/index.html).



</td>
</tr>
<tr>
<td valign="top">

**Visualization of IANA Time Zones for Date/Time Data**

OpenUI5 now supports the visualization of IANA time zones for date/time data. The time zone can either be passed via configuration or specified via an annotation from a back-end service.

The following OpenUI5 functionality supports IANA time zones:

-   Configuration of the default time zone via:

    -   The `timezone` configuration option \(see [`sap.ui.core.Configuration`](https://sdk.openui5.org/api/sap.ui.core.Configuration)\).

    -   The API method [`sap.ui.core.Configuration.setTimezone`](https://sdk.openui5.org/api/sap.ui.core.Configuration/methods/setTimezone)

-   The time zone-specific `DateFormat` [`DateTimeWithTimezone`](https://sdk.openui5.org/api/sap.ui.core.format.DateFormat.DateTimeWithTimezone), which can be retrieved via [`sap.ui.core.format.DateFormat.getDateTimeWithTimezoneInstance`](https://sdk.openui5.org/api/api/sap.ui.core.format.DateFormat%23methods/sap.ui.core.format.DateFormat.getDateTimeWithTimezoneInstance). It allows the formatting/parsing of timestamps while visualizing the date and/or the time and/or the time zone. For more information, see [`sap.ui.core.format.DateFormat`](https://sdk.openui5.org/api/sap.ui.core.format.DateFormat) as well as [Date Format](Date_Format_91f2eba.md).
-   The new [`sap.ui.model.odata.type.DateTimeWithTimezone`](https://sdk.openui5.org/api/sap.ui.model.odata.type.DateTimeWithTimezone) composite type where the first part is the time stamp and the second part is the IANA time zone.
-   The OData V4 model supports specifying the time zone via the `com.sap.vocabularies.common.v1.Timezone` annotation. For more information, see:

    -   [Meta Model for OData V4](Meta_Model_for_OData_V4_7f29fb3.md)

    -   [AnnotationHelper](Meta_Model_for_OData_V4_7f29fb3.md#loio7f29fb3ce5964d8090038a9d3cdf5060__section_AnnoHelp)

    In OData V2, this is handled by the enhancements mentioned for `sap.ui.comp.smartfield.SmartField` and `sap.ui.comp.smarttable.SmartTable` below.

-   [`sap.m.DateTimePicker`](https://sdk.openui5.org/api/sap.m.DateTimePicker) visualizes the time zone based on the type information. In addition, it has its own properties for visualizing the time zone.



</td>
</tr>
</table>

***

<a name="loiob530db37f4db4164b5e68f20bff93a9a__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**Accessibility**

We are now using JAWS 2022 as a reference testing environment in OpenUI5. For more information, see the *Assistive technologies reference testing environment for SAPUI5* SAP Note [2564165](https://launchpad.support.sap.com/#/notes/2564165).



</td>
</tr>
<tr>
<td valign="top">

**Improved Handling of Aggregations in XML Views**

Aggregations of the XML view itself and of the controls inside the view are now handled in the same way.

If a container control has one of its aggregations marked as the default aggregation, you can now add children directly into that control. For example, if `sap.ui.core.mvc.XMLView`'s `content` aggregation is marked as default, you can define content for the aggregation directly in the XML view, without explicitly adding a `content` tag. Of course, when a container control does not have a default aggregation defined, or when adding a child control into another aggregation, you still need to use an aggregation tag, for example `dependents`.

In order to align the usage of XML views and controls even further, aggregations such as `content` and `dependents` are now also bindable. This is only supported when following the best practice not to use native HTML inside XML views. For more information, see [Aggregation Handling in XML Views](Aggregation_Handling_in_XML_Views_19eabf5.md).



</td>
</tr>
<tr>
<td valign="top">

**OpenUI5 OData V2 Model**

The `sap.ui.model.odata.OperationMode.Auto` operation mode is deprecated. If the amount of data is small enough to be loaded completely onto the client, use `sap.ui.model.odata.OperationMode.Client` instead. Otherwise, use `sap.ui.model.odata.OperationMode.Server` or `sap.ui.model.odata.OperationMode.Default`.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.OperationMode%23overview).



</td>
</tr>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   The creation of inactive rows introduced with OpenUI5 1.97 is no longer experimental. For more information, see [Creating an Entity](Creating_an_Entity_c9723f8.md)and the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding%23methods/create).
-   If metadata is already available, key predicates of message targets received from the back end are now normalized to match the key predicates calculated on the client.



</td>
</tr>
</table>

***

<a name="loiob530db37f4db4164b5e68f20bff93a9a__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.m.DatePicker`, `sap.m.TimePicker`, and `sap.m.DateTimePicker`**

We have added `afterValueHelpOpen` and `afterValueHelpClose` events, fired when value help dialog opens and closes.

 For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.DatePicker). 



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.NotificationListItem` and `sap.m.NotificationListGroup`**

We have applied the following visual changes, which improve the prioritization of the displayed information on small screen sizes:

-   The title of the `sap.m.NotificationListGroup` doesn’t truncate any more. Instead, it wraps to as many lines it needs.

-   The avatar of the `sap.m.NotificationListItem` is hidden in small \(S\) control size.

-   The action button and the close button \(if present\) are moved to a single overflow in small \(S\) control size.


For more information, see the [NotificationListItem](https://sdk.openui5.org/entity/sap.m.NotificationListItem/sample/sap.m.sample.NotificationListItem) and the [NotificationListGroup](https://sdk.openui5.org/entity/sap.m.NotificationListGroup/sample/sap.m.sample.NotificationListGroup) samples.



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.p13n*`**

We have improved the usability of the *View Settings* dialog. To do this, we have replaced the `sap.m.Select` control with a `sap.m.ComboBox` control and items of type `sap.m.StandardListItem`.

In particular, the following changes have been applied:

-   We have replaced *None* in the selection lists of the *Sort* and *Group* tabs with the *Sort by* and *Group by* placeholder texts based on the SAP Fiori design guidelines.

-   We have adapted the tooltips of the *Delete* buttons for removing entries on the tabs.

    ![](images/loio53d93b35ecc24e6cb1d69ab6ca387760_LowRes.png)

-   For a more simplified search, especially in a long selection list, users can now enter a column name.


For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.p13n.Popup/sample/sap.m.sample.p13n.Popup) for `sap.m.p13n.Popup` and the [Sample](https://sdk.openui5.org/entity/sap.ui.comp.smarttable.SmartTable/sample/sap.ui.comp.sample.smarttable.mtableCustom) for `SmartTable`. 



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.unified.FileUploader`**

We have implemented `beforeDialogOpen` and `beforeDialogClose` events, fired when the user opens and closes the file select dialog.

 For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.unified.FileUploader). 



</td>
</tr>
</table>

***

<a name="loiob530db37f4db4164b5e68f20bff93a9a__section_cps_cg5_zcb"/>

### Deprecations


<table>
<tr>
<td valign="top">

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://sdk.openui5.org/api/deprecated). 



</td>
</tr>
</table>

