<!-- loiobd2e61ff57714ee28efdb5abb83af2e4 -->

| loio |
| -----|
| bd2e61ff57714ee28efdb5abb83af2e4 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/bd2e61ff57714ee28efdb5abb83af2e4) | [demo kit latest release](https://sdk.openui5.org/topic/bd2e61ff57714ee28efdb5abb83af2e4)</div>

## What's New in OpenUI5 1.132

With this release OpenUI5 is upgraded from version 1.131 to 1.132.

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

1.132 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.mdc.FilterBar`** 

</td>
<td valign="top">

**`sap.ui.mdc.FilterBar`**

We have introduced the option to filter a value help using the `Empty` and `NotEmpty` operators not only in fields of type `string`, but also in fields of type `Date` and `DateTime`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.mdc.enums.OperatorName) and the [Sample](https://sdk.openui5.org/entity/sap.ui.mdc/sample/sap.ui.mdc.demokit.sample.TableFilterBarJson). 

<sub>Changed•Control•Info Only•1.132</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-01-23

</td>
</tr>
<tr>
<td valign="top">

1.132 

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

<sub>Deprecated•Feature•Info Only•1.132</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-01-23

</td>
</tr>
<tr>
<td valign="top">

1.132 

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

-   We have extended the combo box filter with an additional attribute to allow for grouping items. For more information, see the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/comboBoxFilter/dynamicFilterGrouping).
-   Cards of type WebPage are no longer experimental. The WebPage Integration Cards now support relative URLs for their `src` property.

<sub>Changed•Control•Info Only•1.132</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-01-23

</td>
</tr>
<tr>
<td valign="top">

1.132 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Button`** 

</td>
<td valign="top">

**`sap.m.Button`**

We have introduced a new `BadgeStyle` property that allows for the badge notification to be represented either as a number in default style or as a dot in attention style. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.Button/sample/sap.m.sample.ButtonWithBadge).

<sub>Changed•Control•Info Only•1.132</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-01-23

</td>
</tr>
<tr>
<td valign="top">

1.132 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.TimePicker`** 

</td>
<td valign="top">

**`sap.m.TimePicker`**

To improve accessibility, `TimePicker` now displays tooltips for hours, minutes, and seconds. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.TimePicker/sample/sap.m.sample.TimePickerHidden).

<sub>Changed•Control•Info Only•1.132</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-01-23

</td>
</tr>
<tr>
<td valign="top">

1.132 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.ViewSettingsDialog`** 

</td>
<td valign="top">

**`sap.m.ViewSettingsDialog`**

We have added a new preventable `beforeClose` event, for cases where the dialog should not close after selecting *OK*. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ViewSettingsDialog%23events/Summary).

<sub>Changed•Control•Info Only•1.132</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-01-23

</td>
</tr>
<tr>
<td valign="top">

1.132 

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

It's now possible to navigate through the elements added to the `endContent` aggregation. We've removed the experimental tag from the `endContent` aggregation. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.Menu/sample/sap.m.sample.MenuEndContent).

<sub>Changed•Control•Info Only•1.132</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-01-23

</td>
</tr>
<tr>
<td valign="top">

1.132 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Types and Formatters** 

</td>
<td valign="top">

**Types and Formatters**

The new version of OpenUI5 introduces the following features:

-   The `decimals` format option of `sap.ui.model.type.Unit` and `sap.ui.model.odata.type.Unit` now defaults to 3 decimals if none of the `decimals`, `maxFractionDigits`, or `minFractionDigits` format options is set.

-   We have provided the new `decimalPadding` format option for the currency, float, and unit instances of `sap.ui.core.format.NumberFormat`. This format option is also available for types using the respective `NumberFormat` instances. In particular, it is available for `sap.ui.model.odata.type.Currency` and `sap.ui.model.odata.type.Unit`.

    For more information, see the API Reference for [`NumberFormat`](https://sdk.openui5.org/api/sap.ui.core.format.NumberFormat), [`Currency`](https://sdk.openui5.org/api/sap.ui.model.odata.type.Currency), and [`Unit`](https://sdk.openui5.org/api/sap.ui.model.odata.type.Unit).


<sub>Changed•Feature•Info Only•1.132</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-01-23

</td>
</tr>
<tr>
<td valign="top">

1.132 

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

We have renamed the `iLevels` parameter of the `sap.ui.model.odata.v4.Context#expand` function introduced experimentally with OpenUI5 1.128 to `bAll`. Like the `bAll` parameter of `Context#collapse`, it is now available and can be used productively.For more information, see the API Reference for [`Context#expand`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/expand) and [`Context#collapse`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/collapse).

<sub>Changed•Feature•Info Only•1.132</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-01-23

</td>
</tr>
<tr>
<td valign="top">

1.132 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Avatar`** 

</td>
<td valign="top">

**`sap.m.Avatar`**

-   We have introduced a new `badgeIconColor` property that enables applications to define the color of the badge icon to indicate different statuses or categories. You can find a list of accepted values in the new `sap.m.AvatarBadgeColor` enumeration.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Avatar).

-   We have introduced handling for displaying a badge without an icon with a new custom URI. When using `sap-icon://avatar-icon-none` as the value in the `showBorder` property, the badge remains visible and can display a background color or tooltip.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Avatar).

<sub>Changed•Control•Info Only•1.132</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-01-23

</td>
</tr>
<tr>
<td valign="top">

1.132 

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

We have introduced a new `src` property that enables applications to define the illustration to be displayed as a graphical element within the control.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.IllustratedMessage) and the [Sample](https://sdk.openui5.org/entity/sap.m.IllustratedMessage/sample/sap.m.sample.IllustratedMessageInPageWithURI).

<sub>Changed•Control•Info Only•1.132</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-01-23

</td>
</tr>
</table>

