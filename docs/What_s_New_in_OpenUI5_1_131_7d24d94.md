<!-- loio7d24d94d6bbe4a988265994a4a41eff6 -->

| loio |
| -----|
| 7d24d94d6bbe4a988265994a4a41eff6 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/7d24d94d6bbe4a988265994a4a41eff6) | [demo kit latest release](https://sdk.openui5.org/topic/7d24d94d6bbe4a988265994a4a41eff6)</div>

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

## What's New in OpenUI5 1.131

With this release OpenUI5 is upgraded from version 1.130 to 1.131.

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

**End of Cloud Provisioning for OpenUI5 Versions \(Q4/2024\)** 

</td>
<td valign="top">

**End of Cloud Provisioning for OpenUI5 Versions \(Q4/2024\)**

The following OpenUI5 versions will be removed from the OpenUI5 Content Delivery Network \(CDN\) after the end of Q4/2024.

**Minor Versions Reaching Their End of Cloud Provisioning**

The following versions including all patches will be removed entirely:

-   1.114
-   1.117
-   1.118
-   1.119

**Action**: Upgrade to a version that is still in maintenance.

**Patch Versions Reaching Their End of Cloud Provisioning**

The following patches will be removed:

-   Long-term maintenance versions:

    -   1.71.59 to 1.71.60
    -   1.84.39 to 1.84.40
    -   1.96.23 to 1.96.24
    -   1.108.20 to 1.108.22
    -   1.120.0 to 1.120.1

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

1.131 

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

<sub>Deprecated•Feature•Info Only•1.131</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-11-28

</td>
</tr>
<tr>
<td valign="top">

1.131 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.mdc.Table`** 

</td>
<td valign="top">

**`sap.ui.mdc.Table`**

-   To collapse/expand either an entire node or an entire tree in tables with `TreeTableType`, we have introduced a `MenuButton`. For each functionality, the related function must be implemented in the configuration object of `TableDelegate`. For OData V4, we have already implemented this as a default functionality. For more information, see the [API Reference](https://sdk.openui5.org/api/module:sap/ui/mdc/TableDelegate%23methods/sap/ui/mdc/TableDelegate.fetchExpandAndCollapseConfiguration).

-   We have enabled sticky group headers by default for tables with `ResponsiveTableType`. Group headers now remain in a fixed position at the top of the page during vertical scrolling. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.ui.mdc.Table/sample/sap.ui.mdc.demokit.sample.table.TableJson).

<sub>Changed•Control•Info Only•1.131</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-11-28

</td>
</tr>
<tr>
<td valign="top">

1.131 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.List`, `sap.m.Table`, `sap.m.Tree`, `sap.ui.mdc.Table,` `sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable` ** 

</td>
<td valign="top">

**`sap.m.List`, `sap.m.Table`, `sap.m.Tree`, `sap.ui.mdc.Table,` `sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable` **

We now also support the `Indication09` and `Indication10` color values for row highlights. Due to the accessibility contrast requirements, only values of `Indication01` to `Indication10` are supported. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.table.RowSettings%23methods/getHighlight).

<sub>Changed•Control•Info Only•1.131</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-11-28

</td>
</tr>
<tr>
<td valign="top">

1.131 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OpenUI5 Formatter** 

</td>
<td valign="top">

**OpenUI5 Formatter**

When using the currency instance of `sap.ui.core.format.NumberFormat` with the `style` format option set to `short` or `long`, the number of decimals provided with custom currencies or defined in the Unicode Common Locale Data Repository is not applied for formatting.

<sub>Changed•Feature•Info Only•1.131</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-11-28

</td>
</tr>
<tr>
<td valign="top">

1.131 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**`sap.ui.model.sorter`** 

</td>
<td valign="top">

**`sap.ui.model.sorter`**

We have provided getters for the binding path and the sorting order parameter of `sap.ui.model.sorter`.

<sub>Changed•Feature•Info Only•1.131</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-11-28

</td>
</tr>
<tr>
<td valign="top">

1.131 

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

-   You can now modify the annotations of a separate value help service using local annotation files. For more information, see [Value Lists](Value_Lists_ab267a6.md).

-   We have provided the experimental `separateReceived` event at the `sap.ui.model.odata.v4.ODataListBinding` for columns loaded separately using the experimental `$$separate` binding parameter introduced with OpenUI5 1.129.


<sub>Changed•Feature•Info Only•1.131</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-11-28

</td>
</tr>
<tr>
<td valign="top">

1.131 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Improved Focus Handling in OpenUI5** 

</td>
<td valign="top">

**Improved Focus Handling in OpenUI5**

Whenever a UI5 element loses focus due to becoming disabled, invisible, or destroyed, the focus now automatically shifts to the next logical element, ensuring improved navigation and accessibility. Control developers can customize this behavior by overriding the default `onfocusfail` handler to meet specific control requirements.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.core.Element%23methods/onfocusfail).

<sub>Changed•Feature•Info Only•1.131</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-11-28

</td>
</tr>
<tr>
<td valign="top">

1.131 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Combobox`** 

</td>
<td valign="top">

**`sap.m.Combobox`**

The down-arrow navigation has been updated to align with the specifications and the ARIA standard. Now, if there is a selection made through the type-ahead \(autocomplete\) functionality, pressing the [Down Arrow\] key moves the focus to the next available item in the dropdown menu.

<sub>Changed•Control•Info Only•1.131</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-11-28

</td>
</tr>
<tr>
<td valign="top">

1.131 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.IconTabBar`** 

</td>
<td valign="top">

**`sap.m.IconTabBar`**

We have made some visual improvements when the `headerBackgroundDesign` is set to `Transparent`. Now, the control won't show any unnecessary borders or shadows, and looks better when used in content with a transparent design. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.IconTabBar).

<sub>Changed•Control•Info Only•1.131</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-11-28

</td>
</tr>
<tr>
<td valign="top">

1.131 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.MaskInput`** 

</td>
<td valign="top">

**`sap.m.MaskInput`**

We have introduced a new `submit` event that fires when users press [Enter\] and submit a value. The event is fired only when the control is `enabled` and `editable`, regardless of whether there's a change in the submitted value. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.MaskInput).

<sub>Changed•Control•Info Only•1.131</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-11-28

</td>
</tr>
<tr>
<td valign="top">

1.131 

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

We have introduced a new `beforeClose` event, fired when the menu is closed. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Menu).

<sub>Changed•Control•Info Only•1.131</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-11-28

</td>
</tr>
<tr>
<td valign="top">

1.131 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Popover`** 

</td>
<td valign="top">

**`sap.m.Popover`**

Users can now resize the control in all directions, depending on the position of the opener. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.Popover/sample/sap.m.sample.Popover).

<sub>Changed•Control•Info Only•1.131</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-11-28

</td>
</tr>
<tr>
<td valign="top">

1.131 

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

You can now set actions in the card header to be placed as nested items in a menu. This feature allows you to group multiple actions. For more information, see the [Custom Actions](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/extension/customActions) and the [Host Actions](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/hostActions) samples.

<sub>Changed•Control•Info Only•1.131</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-11-28

</td>
</tr>
</table>

