<!-- loio8f6a92b4a9c246f0bbe11cbd1aae1876 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

## What's New in OpenUI5 1.137

With this release OpenUI5 is upgraded from version 1.136 to 1.137.

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

**End of Cloud Provisioning for OpenUI5 Versions \(Q2/2025\)** 

</td>
<td valign="top">

**End of Cloud Provisioning for OpenUI5 Versions \(Q2/2025\)**

The following OpenUI5 versions will be removed from the OpenUI5 Content Delivery Network \(CDN\) after the end of Q2/2025.

**Minor Versions Reaching Their End of Cloud Provisioning**

The following versions including all patches will be removed entirely:

-   1.121
-   1.122
-   1.123
-   1.124

**Action**: Upgrade to a version that is still in maintenance.

**Patch Versions Reaching Their End of Cloud Provisioning**

The following patches will be removed:

-   Long-term maintenance versions:

    -   1.71.63 to 1.71.65
    -   1.84.44 to 1.84.45
    -   1.96.28 to 1.96.30
    -   1.108.27 to 1.108.29
    -   1.120.11 to 1.120.15

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

1.137 

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

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://ui5.sap.com/#/api/deprecated).

<sub>Deprecated•Feature•Info Only•1.137</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-06-12

</td>
</tr>
<tr>
<td valign="top">

1.137 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.List`, `sap.m.Table`, `sap.m.Tree`** 

</td>
<td valign="top">

**`sap.m.List`, `sap.m.Table`, `sap.m.Tree`**

To define row actions for list items, you can now use the `sap.m.ListItemAction` control. `ListItemBase` contains the `actions` aggregation that provides an icon, a text, and the type, for example, editable or deletable, for the action, and whether it is visible in the row. The `getItemActionCount` method of `ListBase` defines how many actions can be added to an item. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.ListItemAction%23overview) and the [Sample](https://ui5.sap.com/#/entity/sap.m.List/sample/sap.m.sample.ListActions).

<sub>Changed•Control•Info Only•1.137</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-06-12

</td>
</tr>
<tr>
<td valign="top">

1.137 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Table`, `sap.ui.mdc.Table`, `sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable`** 

</td>
<td valign="top">

**`sap.m.Table`, `sap.ui.mdc.Table`, `sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable`**

We have provided a built-in, quick resizing of columns in addition to the existing resizing options using drag and drop or keyboard shortcuts. This accessible column resizing is available in the column menu \(*Resize column width \(pixel\)*\). For responsive tables, use the `QuickResize` class to define quick actions for the column resizing. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.table.columnmenu.QuickResize), the [Sample](https://ui5.sap.com/#/entity/sap.ui.table.Table/sample/sap.ui.table.sample.Menus) for `sap.ui.table.Table` \(standalone\), the [Sample](https://ui5.sap.com/#/entity/sap.m.Table/sample/sap.m.sample.TableViewSettingsDialog) for `sap.m.Table` \(standalone\), and the [Sample](https://ui5.sap.com/#/entity/sap.ui.mdc.Table/sample/sap.ui.mdc.demokit.sample.table.TableJson) for `sap.ui.mdc.Table` with responsive tables.

<sub>Changed•Control•Info Only•1.137</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-06-12

</td>
</tr>
<tr>
<td valign="top">

1.137 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.tnt.NavigationListItem`** 

</td>
<td valign="top">

**`sap.tnt.NavigationListItem`**

-   When a child item from a collapsed parent item is selected, the parent item now also appears as selected. This is only a visual indication at the level of the parent item.
-   The `press` event is now preventable and new parameters \(`ctrlKey`, `shiftKey`, `altKey`, and `metaKey`\) have been added to enable the handling of specific user interactions, such as control-click, shift-click, and other modified clicks.

<sub>Changed•Control•Info Only•1.137</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-06-12

</td>
</tr>
<tr>
<td valign="top">

1.137 

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

-   The experimental *Header Info Section* feature in an extended card header now includes an `Interactive Status` property that permits supported `ObjectStatus` components to become interactive. This feature is now supported in Card Headers of type Default and Numeric. For more information, see the [Sample](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/headerInfoSection) and the updated [Info Section](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/headers/infoSection) in the Card Explorer.
-   UI Integration Cards of declarative card types List, Object, and Table, now support interactive `ObjectStatus` components.
-   The different types of card interactions are now finalized, are extensively documented in Card Explorer, and include samples. In addition to the existing types of card interactions and the already available interactive elements inside the card, card developers can now choose the new whole card interaction \(experimental\) pattern. For more information and samples, see the new section [Interaction Types](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/interactionTypes).
-   Card interaction of type whole card interaction \(experimental\) sets `actions` at the card level within the card's manifest, enabling the entire card area to respond interactively to click or tap events. To achieve whole card interaction, the host environment can either use the `sap.f.GridContainer`, which is already enabled for this scenario, or use a custom layout with specific configuration. For more information, see the new section [Card Interactions](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/integrate/interactions) in Card Explorer.

<sub>Changed•Control•Info Only•1.137</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-06-12

</td>
</tr>
<tr>
<td valign="top">

1.137 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Menu`** 

</td>
<td valign="top">

**`sap.m.Menu`**

We have introduced a new implementation of the `sap.m.Menu` that simplifies its structure, enhances its functionality across device types, and overcomes the previous limitations associated with the complex and challenging-to-maintain former structure of the control. Key improvements include:

-   The `sap.m.Menu` now exclusively uses the `sap.m.ResponsivePopover`, which supports seamless display across desktop, tablet, and mobile devices.
-   The refactored design simplifies the control's maintenance and facilitates the addition of new features, while supporting the control's existing functionality and API capabilities.
-   The `sap.m.Menu` now includes a modular `MenuItem` renderer that allows easy customization of menu items with various appearances and functionality.
-   The inner DOM structure is now consistent across devices. The only difference is that now the `ResponsiveRenderer` renders as `sap.m.Popover` on desktop and tablet devices, whereas on mobile devices, it renders as `sap.m.Dialog`.

For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.Menu) and the [Samples](https://ui5.sap.com/#/entity/sap.m.Menu).

<sub>Changed•Control•Info Only•1.137</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-06-12

</td>
</tr>
<tr>
<td valign="top">

1.137 

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

-   The `$$separate` binding parameter, introduced experimentally with OpenUI5 1.129, is now available and can be used productively. For more information, see [Expensive Navigation Properties in Lists](../04_Essentials/initialization-and-read-requests-fccfb2e.md#loiofccfb2eb41414f0792c165e69a878717__section_ENPL).

-   The binding of properties of open types is now supported.


<sub>Changed•Feature•Info Only•1.137</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-06-12

</td>
</tr>
</table>

