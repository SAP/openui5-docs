<!-- loio32d4b9c2b981425dbc374d3e9d5d0c2e -->

| loio |
| -----|
| 32d4b9c2b981425dbc374d3e9d5d0c2e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/32d4b9c2b981425dbc374d3e9d5d0c2e) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/32d4b9c2b981425dbc374d3e9d5d0c2e)</div>

## Grid Controls

OpenUI5 provides several different grid layouts that are suitable for different use cases.

***

<a name="loio32d4b9c2b981425dbc374d3e9d5d0c2e__section_r2d_sdw_hhb"/>

### `sap.f.GridContainer`

The `sap.f.GridContainer` is a layout control used to align tiles, cards, or other controls in configuration, such as an overview page. It provides a regular grid system in which all rows have the same height and all columns have the same width. Each item can be configured to take different number of rows and columns inside that mesh. If rows span is unknown for an item, it is automatically calculated by the `GridContainer`, based on the height of the item.

***

<a name="loio32d4b9c2b981425dbc374d3e9d5d0c2e__section_vmk_v43_4fb"/>

### `sap.f.GridList`

The `sap.f.GridList` is a layout control that provides the flexibility to display list items in a two-dimensional grid. It extends the `sap.m.ListBase` control and therefore receives all of its features. The layout used is based on the CSS display grid and the control has a default configuration that displays the list items in a grid.

***

<a name="loio32d4b9c2b981425dbc374d3e9d5d0c2e__section_b1w_bp3_4fb"/>

### `sap.ui.layout.cssgrid.CSSGrid`

The `sap.ui.layout.cssgrid.CSSGrid` is a layout control, used to create full-page layouts or user interface elements. It is based on the browser-native CSS display grid and works by the HTML standard specification of a grid. This grid is two-dimensional, meaning that it is possible to specify both rows and columns. The dimensions and position of a single item can be configured, for example, an item can take two rows and two columns from the grid. The control can be used along with the `sap.m.FlexBox` control as a one-dimensional alternative for layouting.

***

<a name="loio32d4b9c2b981425dbc374d3e9d5d0c2e__section_xlx_bp3_4fb"/>

### `sap.ui.layout.Grid`

The `sap.ui.layout.Grid` control defines how many columns are displayed depending on the available screen size with a maximum of 12. The height of a single row is always based on the content of the highest item in that row.

***

<a name="loio32d4b9c2b981425dbc374d3e9d5d0c2e__section_csk_543_4fb"/>

### Overview of Grids and Supported Features


<table>
<tr>
<th>

 **Feature Supported?** 



</th>
<th>

 `sap.f.GridContainer` 



</th>
<th>

 `sap.f.GridList` 



</th>
<th>

 `sap.ui.layout.cssgrid.CSSGrid` 



</th>
<th>

 `sap.ui.layout.Grid` 



</th>
</tr>
<tr>
<td>

 **Complies with the grid specification according to the HTML Standard** 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 **Number of columns supported** 



</td>
<td>

Unlimited



</td>
<td>

Unlimited



</td>
<td>

Unlimited



</td>
<td>

Up to 12



</td>
</tr>
<tr>
<td>

 **Can configure row height, column width, and gap dimensions** 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 **Supports auto calculation of rows per item** 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 **Can fill empty spaces in the grid** 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 **Items flow direction** 



</td>
<td>

Horizontal only



</td>
<td>

Horizontal and vertical



</td>
<td>

Horizontal and vertical



</td>
<td>

Horizontal only



</td>
</tr>
<tr>
<td>

 **Can configure item position** 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td>

**Can configure item dimensions**

The ability to define how many rows and columns an item should take.



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 **Supports columns breathing** 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
</tr>
<tr>
<td>

**Supports templating**

The possibility to use one of the predefined layout templates or to create a custom template for specific layouts.



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>1</sup> 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>1</sup> 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 **Supports screen-size breakpoints** 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>1</sup> 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>1</sup> 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 **Supports container-size breakpoints** 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>1</sup> 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>1</sup> 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 **Supports indentation** 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 **Can control items visibility based on breakpoints** 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 **Supports keyboard handling** 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>2</sup> 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 **Supports growing** 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 **Supports sorting, filtering and grouping** 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 **Supports headers and footer**s



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td>

 **Supports selection and highlighting** 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td>

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
</table>

1\) By using the `customLayout` aggregation.  
 2\) Two-dimensional keyboard navigation is supported. Users can navigate through the contained controls using the arrow keys.

**Related Information**  


[API Reference: `sap.ui.layout.cssgrid.CSSGrid`](https://openui5.hana.ondemand.com/#/api/sap.ui.layout.cssgrid.CSSGrid)

[Samples: `sap.ui.layout.cssgrid.CSSGrid`](https://openui5.hana.ondemand.com/#/entity/sap.ui.layout.cssgrid.CSSGrid)

[API Reference: `sap.ui.layout.Grid`](https://openui5.hana.ondemand.com/#/api/sap.ui.layout.Grid)

[Samples: `sap.ui.layout.Grid`](https://openui5.hana.ondemand.com/#/entity/sap.ui.layout.Grid)

[API Reference: `sap.f.GridContainer`](https://openui5.hana.ondemand.com/#/api/sap.f.GridContainer)

[Samples: `sap.f.GridContainer`](https://openui5.hana.ondemand.com/#/entity/sap.f.GridContainer)

[API Reference: `sap.f.GridList`](https://openui5.hana.ondemand.com/#/api/sap.f.GridList)

[Samples: `sap.f.GridList`](https://openui5.hana.ondemand.com/#/entity/sap.f.GridList)

