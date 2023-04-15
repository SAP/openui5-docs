<!-- loioa9553fe29f174452ae86de7b6da4b5f6 -->

| loio |
| -----|
| a9553fe29f174452ae86de7b6da4b5f6 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/a9553fe29f174452ae86de7b6da4b5f6) | [demo kit latest release](https://sdk.openui5.org/topic/a9553fe29f174452ae86de7b6da4b5f6)</div>

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

## What's New in OpenUI5 1.113

With this release OpenUI5 is upgraded from version 1.112 to 1.113.

> ### Note:  
> Content marked as <span style="color:#666666;"><span class="SAP-icons"></span></span>** [Preview](https://help.sap.com/docs/whats-new-disclaimer)** is provided as a courtesy, without a warranty, and may be subject to change. For more information, see the [preview disclaimer](https://help.sap.com/docs/whats-new-disclaimer).

** **


<table>
<tr>
<th valign="top">

Version



</th>
<th valign="top">

Type



</th>
<th valign="top">

Category



</th>
<th valign="top">

Title



</th>
<th valign="top">

Description



</th>
<th valign="top">

Action



</th>
<th valign="top">

Available as of



</th>
</tr>
<tr>
<td valign="top">

 Upcoming 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Announcement 



</td>
<td valign="top">

 **Planned FLP Time Zone Support in OpenUI5** 



</td>
<td valign="top">

**Planned FLP Time Zone Support in OpenUI5**

With OpenUI5 1.114, we intend to enable the usage of the time zone configured in the SAP Fiori launchpad. The usage of a time zone different from the time zone of a user's computer can break existing applications.

Action: Check and, if necessary, adapt your application code if you plan to use a configured time zone different from the browser's time zone.

For more information, see [Dates, Times, Timestamps, and Time Zones](Dates_Times_Timestamps_and_Time_Zones_6c9e61d.md).

<sub><span style="color:#666666;"><span class="SAP-icons"></span></span>** [Preview](https://help.sap.com/docs/whats-new-disclaimer)**•Changed•Announcement•Required•Upcoming</sub>



</td>
<td valign="top">

 Required 



</td>
<td valign="top">

2023-05-18



</td>
</tr>
<tr>
<td valign="top">

 Upcoming 



</td>
<td valign="top">

 Deleted 



</td>
<td valign="top">

 Announcement 



</td>
<td valign="top">

 **End of Cloud Provisioning for OpenUI5 Versions \(Q2/2023\)** 



</td>
<td valign="top">

**End of Cloud Provisioning for OpenUI5 Versions \(Q2/2023\)**

The following OpenUI5 versions will be removed from the OpenUI5 Content Delivery Network \(CDN\) after the end of Q2/2023.

**Minor Versions Reaching Their End of Cloud Provisioning**

The following versions including all patches will be removed entirely:

-   1.91
-   1.99
-   1.100
-   1.101

Action: Upgrade to a version that’s still in maintenance.

**Patch Versions Reaching Their End of Cloud Provisioning**

The following patches will be removed:

-   Long-term maintenance versions:

    -   1.38.54
    -   1.71.2
    -   1.71.44-1.71.45
    -   1.84.23 to 1.84.24
    -   1.96.7 to 1.96.8

    Action: Upgrade to the latest available patch for the respective OpenUI5 version.

-   Other versions

    -   1.102.0 to 1.102.1

    Action: Upgrade to a version that’s still in maintenance.


For more information, see [UI5 Releases Ending Service in 2023](https://blogs.sap.com/2022/12/05/ui5-releases-ending-service-in-2023/) and [Version Overview](https://sdk.openui5.org/versionoverview.html).

<sub><span style="color:#666666;"><span class="SAP-icons"></span></span>** [Preview](https://help.sap.com/docs/whats-new-disclaimer)**•Deleted•Announcement•Required•Upcoming</sub>



</td>
<td valign="top">

 Required 



</td>
<td valign="top">

2023-06-30



</td>
</tr>
<tr>
<td valign="top">

 1.113 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.p13n*`** 



</td>
<td valign="top">

**`sap.m.p13n*`**

We have further improved the usability and accessibility of the *View Settings* dialog: You can now move items up and down using keyboard shortcuts. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.ui.comp.smarttable.SmartTable/sample/sap.ui.comp.sample.smarttable).

<sub>Changed•Control•Info Only•1.113</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-04-20



</td>
</tr>
<tr>
<td valign="top">

 1.113 



</td>
<td valign="top">

 Deprecated 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **Deprecations** 



</td>
<td valign="top">

**Deprecations**

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://sdk.openui5.org/api/deprecated).

<sub>Deprecated•Feature•Info Only•1.113</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-04-20



</td>
</tr>
<tr>
<td valign="top">

 1.113 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **Code Coverage Powered by `Istanbul`** 



</td>
<td valign="top">

**Code Coverage Powered by `Istanbul`**

OpenUI5 already provides a deep integration of `QUnit` and code coverage measurement. We now introduce `Istanbul` as a modern JavaScript code instrumenter, which is intended to eventually replace the former, now legacy solution based on `Blanket.js`.

To start taking advantage of the more future-proof and feature-rich `Istanbul` solution, see the updated [code coverage documentation](Code_Coverage_Measurement_7ef3242.md).

<sub>Changed•Feature•Info Only•1.113</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-04-20



</td>
</tr>
<tr>
<td valign="top">

 1.113 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **OpenUI5 Date and Time Formatting** 



</td>
<td valign="top">

**OpenUI5 Date and Time Formatting**

The new version of OpenUI5 introduces the following formatting features:

-   You can now centrally configure calendar week numbering via the new `calendarWeekNumbering` configuration parameter. Note that the `calendarWeekNumbering` format option introduced with OpenUI5 1.108 for `sap.ui.core.format.DateFormat` overrules the central configuration.

    For more information, see [Configuration Options and URL Parameters](Configuration_Options_and_URL_Parameters_91f2d03.md).

-   We provide the new `intervalDelimiter` format option for `sap.ui.core.format.DateFormat`. If an `intervalDelimiter` is set, the locale-specific rules for displaying a range as defined in the Common Locale Data Repository are overruled; the two parts of the range are formatted individually, and the given delimiter is used.


<sub>Changed•Feature•Info Only•1.113</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-04-20



</td>
</tr>
<tr>
<td valign="top">

 1.113 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **OpenUI5 OData V4 Model** 



</td>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   You can now delete nested transient records that were created using the experimental Deep Create feature provided with OpenUI5 1.112. Any initial data handed over to `sap.ui.model.odata.v4.ODataListBinding#create` can now contain nested entities.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding/methods/create).

-   In read-only scenarios, you can now combine the experimental hierarchy feature introduced with OpenUI5 1.105 with the `sap.ui.model.odata.v4.Context#setKeepAlive` and `sap.ui.model.odata.v4.ODataModel#getKeepAliveContext` data synchronization methods described in [Data Reuse](Data_Reuse_648e360.md).

    For more information, see the API Reference for [`setKeepAlive`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context/methods/setKeepAlive) and [`getKeepAliveContext`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel/methods/getKeepAliveContext).

-   The `sap.ui.model.odata.v4.Context#resetChanges` API introduced as an experimental feature with OpenUI5 1.109 is now generally available.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context/methods/resetChanges).


<sub>Changed•Feature•Info Only•1.113</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-04-20



</td>
</tr>
<tr>
<td valign="top">

 1.113 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **OpenUI5 OData V2 Model** 



</td>
<td valign="top">

**OpenUI5 OData V2 Model**

You can now prevent the activation of a new inactive entity by using `sap.ui.base.Event#preventDefault` in the handler of the `createActivate` event of an `sap.ui.model.odata.v2.ODataListBinding`. Note that user input into inactive rows is regarded as a pending change by `sap.ui.model.odata.v2.ODataModel#hasPendingChanges`; it can be reset using `sap.ui.model.odata.v2.ODataModel#resetChanges`.

For more information, see the API Reference for [`hasPendingChanges`](https://sdk.openui5.org/api/sap.ui.model.odata.v2.ODataModel/methods/hasPendingChanges), [`resetChanges`](https://sdk.openui5.org/api/sap.ui.model.odata.v2.ODataModel/methods/resetChanges), and [`Event.preventDefault`](https://sdk.openui5.org/api/sap.ui.base.Event/methods/preventDefault).

<sub>Changed•Feature•Info Only•1.113</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-04-20



</td>
</tr>
<tr>
<td valign="top">

1.112



</td>
<td valign="top">

 Deleted 



</td>
<td valign="top">

 Announcement 



</td>
<td valign="top">

 **End of Cloud Provisioning for OpenUI5 Versions \(Q1/2023\)** 



</td>
<td valign="top">

**End of Cloud Provisioning for OpenUI5 Versions \(Q1/2023\)**

> ### Note:  
> The following information concerns important upcoming changes for end users. These changes may require end users to adjust and/or test cases to be adapted, but they won't stop or disrupt software or processes.

The following OpenUI5 versions will be removed from the OpenUI5 Content Delivery Network \(CDN\) after the end of Q1/2023.

**Minor Versions Reaching Their End of Cloud Provisioning**

The following versions including all patches will be removed entirely:

-   1.90
-   1.93
-   1.97
-   1.98

Action: Upgrade to a version that’s still in maintenance.

**Patch Versions Reaching Their End of Cloud Provisioning**

The following patches will be removed:

-   Long-term maintenance versions:

    -   1.38.52 to 1.38.53
    -   1.71.40-1.71.43
    -   1.84.20 to 1.84.22
    -   1.96.3 to 1.96.6

    Action: Upgrade to the latest available patch for the respective OpenUI5 version.


For more information, see [UI5 Releases Ending Service in 2023](https://blogs.sap.com/2022/12/05/ui5-releases-ending-service-in-2023/) and [Version Overview](https://sdk.openui5.org/versionoverview.html).

<sub>Deleted•Announcement•Required•1.112</sub>



</td>
<td valign="top">

 Required 



</td>
<td valign="top">

2023-03-31



</td>
</tr>
<tr>
<td valign="top">

 1.113 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.ui.integration.widgets.Card`** 



</td>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   Using the new `customStateIcon` property, you can now set custom state-icons for the items in Table, List, and Object cards. Before this change, states like `Error`, `Warning`, `Success`, or `Information`, only had default icons. For more information, see the [Table Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/typesDeclarative/table) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/table/visibleColumns) in the Card Explorer.

-   Integration cards now support the `IllustratedMessage` control to provide more informative and consistent error messages. When the application is in debug mode \(when the URL parameter `sap-ui-debug=true` is set\), the *Show More* button opens a dialog with relevant additional \(more technical\) information.

-   We have enhanced the Table card with several new properties:

    -   You can use the new `highlight` property to show the state of each table row. Additionally, the `highlightText` property conveys the semantic of this state for better accessibility.
    -   The `additionalText` property gives you the option to display additional text in the table identifier column.

    For more information, see the [Table Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/typesDeclarative/table) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/table/highlight) in the Card Explorer. 


<sub>Changed•Control•Info Only•1.113</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-04-20



</td>
</tr>
<tr>
<td valign="top">

 1.113 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **`sap.ui.test.Opa5`** 



</td>
<td valign="top">

**`sap.ui.test.Opa5`**

We have introduced a new `fetchWaiter`, which checks for currently ongoing fetch requests.

<sub>Changed•Feature•Info Only•1.113</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-04-20



</td>
</tr>
<tr>
<td valign="top">

 1.113 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.SuggestionsPopover`** 



</td>
<td valign="top">

**`sap.m.SuggestionsPopover`**

We have restricted the width of input suggestions to a maximum of 40 rem for optimal user experience. Limiting the width of suggestions allows users to easily scan and select options. However, if the input field is wider than 40 rem, the width of the suggestions matches the input’s width.

<sub>Changed•Control•Info Only•1.113</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-04-20



</td>
</tr>
<tr>
<td valign="top">

 1.113 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.IllustratedMessage`** 



</td>
<td valign="top">

**`sap.m.IllustratedMessage`**

We have introduced a new `Survey` illustration type and four new illustrations to the default illustration set: `sapIllus-Dialog-NoColumnsSet`, `sapIllus-Dot-NoColumnsSet`, `sapIllus-Scene-NoColumnsSet`, and `sapIllus-Spot-NoColumnsSet`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.IllustratedMessage). 

<sub>Changed•Control•Info Only•1.113</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-04-20



</td>
</tr>
<tr>
<td valign="top">

 1.113 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.ui.unified.FileUploader`** 



</td>
<td valign="top">

**`sap.ui.unified.FileUploader`**

We have implemented two new methods in the control's API, a trigger to open the native file upload picker and a getter to return the file input type element from the control DOM representation.

 For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.unified.FileUploader). 

<sub>Changed•Control•Info Only•1.113</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-04-20



</td>
</tr>
<tr>
<td valign="top">

 1.113 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.f.SidePanel`** 



</td>
<td valign="top">

**`sap.f.SidePanel`**

We have implemented an **enabled** property to the Side Panel item, which disables the controls and UI elements inside it.

 For more information, see the [Sample](https://sdk.openui5.org/entity/sap.f.SidePanel/sample/sap.f.sample.SidePanel). 

<sub>Changed•Control•Info Only•1.113</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-04-20



</td>
</tr>
<tr>
<td valign="top">

 1.113 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.SinglePlanningCalendar`** 



</td>
<td valign="top">

**`sap.m.SinglePlanningCalendar`**

We have implemented a new mode to select one or more dates in **SinglePlanningCalendar**. Тhe single day option is enabled by default, the multi-date selection option is possible by using a key combination \( [Ctrl\] + [Meta key\]  and select the dates\) or by activating the new **MultiDateSelectionMode** property.

 For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendarDateSelection). 

<sub>Changed•Control•Info Only•1.113</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-04-20



</td>
</tr>
</table>

