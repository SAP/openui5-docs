<!-- loioe5e13176220c4b9597c75580d363abc8 -->

| loio |
| -----|
| e5e13176220c4b9597c75580d363abc8 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/e5e13176220c4b9597c75580d363abc8) | [demo kit latest release](https://sdk.openui5.org/topic/e5e13176220c4b9597c75580d363abc8)</div>

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

## What's New in OpenUI5 1.127

With this release OpenUI5 is upgraded from version 1.126 to 1.127.

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

1.127 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.mdc.Chart` \(experimental\)** 

</td>
<td valign="top">

**`sap.ui.mdc.Chart` \(experimental\)**

To support time series for the chart, we have now implemented time dimensions. We have introduced the `timeUnitType` property for `PropertyInfo` to enable this feature. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.mdc.chart.PropertyInfo%23properties).

<sub>Changed•Control•Info Only•1.127</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-08-08

</td>
</tr>
<tr>
<td valign="top">

1.127 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.mdc.FilterBar`, `sap.ui.mdc.Table`, `sap.ui.mdc.Chart` \(experimental\)** 

</td>
<td valign="top">

**`sap.ui.mdc.FilterBar`, `sap.ui.mdc.Table`, `sap.ui.mdc.Chart` \(experimental\)**

To validate `p13n`-relevant metadata in the application, we have implemented a consistency check that compares the result returned by the `fetchProperties` property of the delegate against the `propertyInfo` property. If the provided `propertyInfo` is not a subset of the result, an error is thrown. This check is implemented in all controls with a `propertyInfo` property and a `fetchProperties` callback in the related delegate.

<sub>Changed•Control•Info Only•1.127</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-08-08

</td>
</tr>
<tr>
<td valign="top">

1.127 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**CSS Custom Properties for Theming of Custom Controls / Applications** 

</td>
<td valign="top">

**CSS Custom Properties for Theming of Custom Controls/Applications**

We have included the theming parameters from the SAP Theming Base Content as CSS custom properties in the Horizon and Quartz themes of OpenUI5. You can now use them in your CSS for your custom controls or applications. We have also extended the Theme Parameter Toolbox to display the CSS custom properties for the Horizon and Quartz themes by default. The previous experimental `xx-css-variables` configuration option is no longer available.

For more information, see [CSS Variables, Functions, and More](Enhanced_Theming_Concepts_45df6df.md#loio45df6dff504647c686ab9ba72af827f6__section_CSS), [Theming](Theming_497c27a.md), and [Theme Parameter Toolbox](https://sdk.openui5.org/test-resources/sap/m/demokit/theming/webapp/index.html).

<sub>Changed•Feature•Info Only•1.127</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-08-08

</td>
</tr>
<tr>
<td valign="top">

1.127 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**TypeScript** 

</td>
<td valign="top">

**TypeScript**

Support for controller extensions in TypeScript is now complete, comprising now also the use of extensions implemented by others in your own controller in addition to the modification of controllers implemented by others with your own extension.

For more information, see [Using Controller Extension with TypeScript](Using_Controller_Extension_21515f0.md#loio21515f09c0324218bb705b27407f5d61__section_UCETS).

<sub>Changed•Feature•Info Only•1.127</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-08-08

</td>
</tr>
<tr>
<td valign="top">

1.127 

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

-   We have improved the experimental `OneWay` binding support for property bindings for structural properties that have a complex type. Updates on the client are now properly reflected.

    For more information, see [Property Binding With an Object Value](Initialization_and_Read_Requests_fccfb2e.md#loiofccfb2eb41414f0792c165e69a878717__section_PBOV).

-   We have added the experimental `iLevels` parameter to `sap.ui.model.odata.v4.Context#expand`. Note that it must not be used in productive applications yet.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context%23methods/expand).


<sub>Changed•Feature•Info Only•1.127</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-08-08

</td>
</tr>
<tr>
<td valign="top">

1.127 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Menu` and `sap.ui.unified.Menu`** 

</td>
<td valign="top">

**`sap.m.Menu` and `sap.ui.unified.Menu`**

You can now set the menu items of these controls to be selectable. To make this possible, we have introduced the `sap.m.MenuItemGroup` and `sap.ui.unified.MenuItemGroup` controls. You have three options to define the selection mode for a group of items: `None` \(default\), `SingleSelect`, and `MultiSelect`. For more information, see the [sap.m.MenuItemGroup](https://sdk.openui5.org/api/sap.m.MenuItemGroup) and [sap.ui.unified.MenuItemGroup](https://sdk.openui5.org/api/sap.ui.unified.MenuItemGroup) API references .

<sub>Changed•Control•Info Only•1.127</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2024-08-08

</td>
</tr>
</table>

