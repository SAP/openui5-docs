<!-- loio1f762207392f46d7bf809edf71ed8704 -->

| loio |
| -----|
| 1f762207392f46d7bf809edf71ed8704 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/1f762207392f46d7bf809edf71ed8704) | [demo kit latest release](https://sdk.openui5.org/topic/1f762207392f46d7bf809edf71ed8704)</div>

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

## What's New in OpenUI5 1.128

With this release OpenUI5 is upgraded from version 1.127 to 1.128.

> ### Note:  
> Content marked as <span style="color:#666666;"><span class="SAP-icons-V5"></span></span>**[Preview](https://help.sap.com/docs/whats-new-disclaimer)** is provided as a courtesy, without a warranty, and may be subject to change. For more information, see the [preview disclaimer](https://help.sap.com/docs/whats-new-disclaimer).

****


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

Deleted 

</td>
<td valign="top">

Announcement 

</td>
<td valign="top">

**End of Cloud Provisioning for OpenUI5 Versions \(Q3/2024\)** 

</td>
<td valign="top">

**End of Cloud Provisioning for OpenUI5 Versions \(Q3/2024\)**

The following OpenUI5 versions will be removed from the OpenUI5 Content Delivery Network \(CDN\) after the end of Q3/2024.

**Minor Versions Reaching Their End of Cloud Provisioning**

The following versions including all patches will be removed entirely:

-   1.114
-   1.115
-   1.116
-   1.117

**Action**: Upgrade to a version that is still in maintenance.

**Patch Versions Reaching Their End of Cloud Provisioning**

The following patches will be removed:

-   Long-term maintenance versions:

    -   1.71.57
    -   1.84.36 to 1.84.38
    -   1.96.21 to 1.96.22
    -   1.108.16 to 1.108.19

    **Action**: Upgrade to the latest available patch for the respective OpenUI5 version.


For more information, see [Version Overview](https://sdk.openui5.org/versionoverview.html).

<sub><span style="color:#666666;"><span class="SAP-icons-V5"></span></span>**[Preview](https://help.sap.com/docs/whats-new-disclaimer)**•Deleted•Announcement•Info Only•Upcoming</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

9999-01-01

</td>
</tr>
<tr>
<td valign="top">

1.128 

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

<sub>Deprecated•Feature•Info Only•1.128</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-09-05

</td>
</tr>
<tr>
<td valign="top">

1.128 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable`** 

</td>
<td valign="top">

**`sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable`**

Cell selection now works in combination with the `Row`/`RowOnly` behavior determined by the `sap.ui.table.SelectionBehavior` enumeration. If a cell selection already exists and the focus is on the cell, users can now extend the selection by pressing [Shift\] + [Up Arrow\]  and [Shift\] + [Down Arrow\]  or [Shift\] and clicking on a cell. To select a cell, users can now press [Spacebar\] if the `CellSelector` plugin is active. To select a row, users have to press [Shift\] + [Spacebar\]  or [Enter\]/ [Return\] instead of [Spacebar\]. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.plugins.CellSelector).

<sub>Changed•Control•Info Only•1.128</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-09-05

</td>
</tr>
<tr>
<td valign="top">

1.128 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Link`** 

</td>
<td valign="top">

**`sap.m.Link`**

You can now add an icon before or after the link text. The icon is interactive, just like the link. You can also add two icons, one on each side, although we don't recommend this. To add an icon, set an icon URI to either of the newly introduced `icon` or `endIcon` properties. These properties only accept icons, not images. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Link) and the [Sample](https://sdk.openui5.org/entity/sap.m.Link/sample/sap.m.sample.Link).

<sub>Changed•Control•Info Only•1.128</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-09-05

</td>
</tr>
<tr>
<td valign="top">

1.128 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.PlanningCalendar`** 

</td>
<td valign="top">

**`sap.m.PlanningCalendar`**

We have improved the drag-and-drop functionality of the control to allow more precise appointment placement. Now, the length of the snapping interval is 15 minutes, reduced from the previous 30-minute interval. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.PlanningCalendar/sample/sap.m.sample.PlanningCalendarDnD).

<sub>Changed•Control•Info Only•1.128</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-09-05

</td>
</tr>
<tr>
<td valign="top">

1.128 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.PlanningCalendar` and `sap.m.SinglePlanningCalendar`** 

</td>
<td valign="top">

**`sap.m.PlanningCalendar` and `sap.m.SinglePlanningCalendar`**

We have improved the flexibility when defining non-working time periods. You can now set these time periods with greater precision, specifying not just full hours but also minutes. For more information, see the [Planning Calendar](https://sdk.openui5.org/entity/sap.m.PlanningCalendar/sample/sap.m.sample.PlanningCalendarRecurringItem) and [Single Planning Calendar](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendarRecurringItem) samples.

<sub>Changed•Control•Info Only•1.128</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-09-05

</td>
</tr>
<tr>
<td valign="top">

1.128 

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

-   We have introduced the `sap.f.cards.CardBadgeCustomData` element, which extends `sap.ui.core.CustomData`. It enables developers to add multiple badges on one card. Additionally, the new API allows them to add icons, state color, announcement text, and to control the visibility of the badge with the visibility mode. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.cards.CardBadgeCustomData) and the [Badge Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/badge)..

-   We have added a new `fallbackSrc` property available for images in Object cards. You can use it to set a fallback image source, in case the main `src` source fails to load. For more information, see the [Object Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/typesDeclarative/object) section and [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object/objectCardWithFallbackImage) in the Card Explorer.


<sub>Changed•Control•Info Only•1.128</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-09-05

</td>
</tr>
<tr>
<td valign="top">

1.128 

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

We have added the experimental `bAll` parameter to `sap.ui.model.odata.v4.Context#collapse`, which allows you to collapse a node and all its descendants. Note that it must not be used in productive applications yet.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/collapse).

<sub>Changed•Feature•Info Only•1.128</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-09-05

</td>
</tr>
<tr>
<td valign="top">

1.128 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.FlexibleColumnLayout`** 

</td>
<td valign="top">

**`sap.f.FlexibleColumnLayout`**

-   We now support the `aria-valuenow` attribute for column separators. It holds the position of the separator in the range of \[0, 100\]. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.FlexibleColumnLayout). 


-   We have introduced the new `layoutData` API to be used by applications to define the custom width of columns, depending on the user interactions/resizing with separators.

    The new `columnsDistributionChange` event is fired when the user manually resizes the `sap.f.FlexibleColumnLayout`. This event helps app developers to save user preferences and use them later. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.FlexibleColumnLayout).


<sub>Changed•Control•Info Only•1.128</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-09-05

</td>
</tr>
<tr>
<td valign="top">

1.128 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.DynamicPageHeader`** 

</td>
<td valign="top">

**`sap.f.DynamicPageHeader`**

The `ObjectPageAccessibleLandmarkInfo` and the `DynamicPageAccessibleLandmarkInfo` now include the `headerSectionLabel` API. It enables customization of the aria-label for the header section of the `sap.f.DynamicPageHeader`. For more information, see the [sap.f.DynamicPageAccessibleLandmarkInfo](https://sdk.openui5.org/api/sap.f.DynamicPageAccessibleLandmarkInfo) and [sap.uxap.ObjectPageAccessibleLandmarkInfo](https://sdk.openui5.org/api/sap.uxap.ObjectPageAccessibleLandmarkInfo) API Reference.

<sub>Changed•Control•Info Only•1.128</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-09-05

</td>
</tr>
<tr>
<td valign="top">

1.128 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Toolbar`** 

</td>
<td valign="top">

**`sap.m.Toolbar`**

We have introduced keyboard arrow navigation to the control. Users can navigate through the interactive items within the control using the [Up\], [Down\], [Left\], and [Right\] arrow keys.

<sub>Changed•Control•Info Only•1.128</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-09-05

</td>
</tr>
<tr>
<td valign="top">

1.128 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Demo Kit: Highlight searched term** 

</td>
<td valign="top">

**Demo Kit: Highlight searched term**

We have added a new feature that highlights the searched term, making it easier for users to find its position in a large body of text when they reach the searched page.

<sub>New•Feature•Info Only•1.128</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-09-05

</td>
</tr>
</table>

